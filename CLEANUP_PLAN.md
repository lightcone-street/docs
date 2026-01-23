# Lightcone Docs - Production Cleanup Plan

## Overview
This document outlines the steps needed to clean up the repository and prepare it for production deployment where it will be viewed by coworkers and potentially external users.

**Important**: This plan focuses on backend cleanup, code quality, and removing unnecessary files. All visible content and navigation structure will remain as-is.

---

## 1. Remove Unused Asset Files

### Files to Delete
- [ ] `/videos/original.mp4` - Backup video file (7.6MB duplicate)
  - Keep only: `/videos/enter-the-lightcone.mp4` (production version)
- [ ] `/OJ.svg` - Appears unused in the codebase

**Note**: All content pages remain unchanged. Only removing duplicate/unused asset files.

---

## 2. Configuration File Review

### docs.json Updates

#### Blog Anchor (Line 18-22)
- [ ] **Decision needed**: Blog anchor currently points to `https://mintlify.com/blog`
  - Option A: Update to `https://lightcone.xyz/blog` (if blog exists)
  - Option B: Remove the blog anchor entirely
  - Option C: Leave as-is if intentional

#### Verify All Links Work
- [ ] Test "App" anchor → `https://lightcone.xyz`
- [ ] Test "Blog" anchor → Current destination
- [ ] Test "Support" link → `mailto:support@lightcone.xyz`
- [ ] Test "Launch App" button → `https://lightcone.xyz`
- [ ] Test footer social links (X, GitHub)

---

## 3. Code Quality & Consistency

### Review Custom Page: enter-the-lightcone.mdx

#### CSS/Styling Audit
- [ ] Verify all inline styles are necessary and optimized
- [ ] Check for any unused style blocks in the `<style>` tag
- [ ] Ensure consistent color values (#9FBFC4, rgba(159, 191, 196, 0.3), etc.)

#### Icon Implementation
Current state: Using Mintlify's `Icon` component
- [ ] **Test in production**: Verify icons render correctly (`lightbulb`, `code`)
- [ ] **Fallback plan**: If icons don't work, document alternative approach (SVG or Font Awesome)
- [ ] Confirm icon library compatibility with Mintlify's deployment

#### Video Element
- [ ] Verify video loads and plays correctly in production
- [ ] Check video file size is acceptable (currently 7.6MB)
- [ ] Test video loop behavior
- [ ] Confirm blur effect renders properly across browsers

---

## 4. Code Comments & Documentation

### Add Code Comments Where Helpful
- [ ] Add comment explaining the custom `<style>` block purpose in enter-the-lightcone.mdx
- [ ] Document why navigation is hidden on this page
- [ ] Add inline comments for complex styling (grain overlay, backdrop blur)

### Internal Documentation
- [ ] Update README.md with:
  - [ ] How to run docs locally (`mint dev`)
  - [ ] Project structure overview
  - [ ] How to add new pages
  - [ ] Deployment process
  - [ ] Contact for docs maintainers

---

## 5. Git Hygiene

### Repository Cleanup
- [ ] Review commit history - no need to squash, but verify nothing sensitive
- [ ] Ensure `.gitignore` is comprehensive:
  - [ ] Node modules
  - [ ] Environment files
  - [ ] OS files (.DS_Store, etc.)
  - [ ] Editor files (.vscode/, .idea/)
- [ ] Check for any TODO comments in code that should be addressed

### Pre-Production Commit
- [ ] Create clean commit message for production-ready state
- [ ] Tag release with version number (e.g., `v1.0.0`)
- [ ] Update any version references in documentation

---

## 6. Testing Checklist

### Functionality Testing
- [ ] **Navigation**: All tabs and links work
- [ ] **Enter the Lightcone page**:
  - [ ] Video plays and loops
  - [ ] Cards display correctly
  - [ ] Icons render properly
  - [ ] Hover effects work
  - [ ] Links navigate to correct pages
  - [ ] No navigation bar visible (as intended)
- [ ] **API Reference**: All endpoint pages load
- [ ] **WebSocket docs**: All pages accessible
- [ ] **Guides section**: All pages load correctly

### Cross-Browser Testing
- [ ] Chrome/Edge (Chromium)
- [ ] Firefox
- [ ] Safari (if accessible)

### Responsive Design Testing
- [ ] Desktop (1920px+)
- [ ] Laptop (1366px)
- [ ] Tablet (768px)
- [ ] Mobile (375px)
- [ ] **Specific**: Cards wrap properly on mobile on "Enter the Lightcone" page

### Performance Testing
- [ ] Page load times acceptable
- [ ] Video doesn't cause lag
- [ ] No console errors in browser DevTools
- [ ] No Mintlify warnings when running `mint dev`

---

## 7. Content Quality Check (Light Touch)

### Quick Content Review
- [ ] Spell check across pages (use browser spell checker)
- [ ] Check for obvious placeholder text ("Lorem ipsum", "TODO", etc.)
- [ ] Verify no broken links (internal or external)
- [ ] Ensure code examples are formatted correctly

**Note**: Not making content changes, just verifying quality.

---

## 8. Configuration Validation

### docs.json Final Checks
- [ ] Verify all file paths in navigation exist
- [ ] Check that colors match brand guidelines:
  - Primary: `#6366F1`
  - Light: `#818CF8`
  - Dark: `#4F46E5`
  - Background light: `#DDE8E8`
- [ ] Confirm theme is set to "willow" (intentional choice)
- [ ] Verify OpenAPI file path: `api-reference/openapi.json`
- [ ] Check favicon path: `/favicon.svg`

### Logo Files
- [ ] Verify `/logo/dark.svg` exists and displays "Lightcone" text
- [ ] Verify `/logo/light.svg` exists and displays "Lightcone" text
- [ ] Test logo appearance in both light and dark modes

---

## 9. Deployment Preparation

### Pre-Deploy Checklist
- [ ] Run `mint dev` and test thoroughly locally
- [ ] Fix any Mintlify warnings or errors
- [ ] Verify Mintlify GitHub integration is configured
- [ ] Confirm deployment domain/subdomain
- [ ] Check if SSL certificate is needed/configured

### Deployment Environment
- [ ] Confirm environment variables (if any)
- [ ] Verify build settings in Mintlify dashboard
- [ ] Check deployment branch configuration

---

## 10. Post-Deployment Monitoring

### Immediate Post-Deploy Checks
- [ ] Verify production site loads correctly
- [ ] Test "Enter the Lightcone" page specifically
- [ ] Click through all navigation to verify links
- [ ] Test video playback on production
- [ ] Check mobile responsiveness on real devices
- [ ] Monitor for any errors in first 24 hours

### Share with Team
- [ ] Send production URL to coworkers for review
- [ ] Gather feedback
- [ ] Create process for reporting issues
- [ ] Document known issues (if any)

---

## Priority Order for Execution

### Phase 1: File Cleanup (15 minutes)
1. Delete `/videos/original.mp4`
2. Delete `/OJ.svg`
3. Verify git status is clean

### Phase 2: Configuration & Testing (1-2 hours)
4. Review and update docs.json (blog anchor decision)
5. Test all functionality locally
6. Cross-browser testing
7. Responsive design testing

### Phase 3: Documentation & Git (30 minutes)
8. Update README.md
9. Add code comments where helpful
10. Review .gitignore
11. Create production commit

### Phase 4: Deployment (1 hour)
12. Final testing
13. Deploy to production
14. Post-deployment verification
15. Team review

---

## Estimated Time
- **Phase 1**: 15 minutes
- **Phase 2**: 1-2 hours
- **Phase 3**: 30 minutes
- **Phase 4**: 1 hour
- **Total**: ~3 hours

---

## Files Modified During This Session

### Key Changes Made
- `/guides/getting-started/enter-the-lightcone.mdx`:
  - Full custom video background page
  - Two interactive cards ("Learn" and "API")
  - Custom styling with grain overlay and blur effects
  - Icons using Mintlify's Icon component
  - Navigation hidden on this page only

- `/docs.json`:
  - Light mode background color: `#DDE8E8`
  - Logo changed to text "Lightcone"

- `/logo/dark.svg` & `/logo/light.svg`:
  - Replaced with simple text SVGs displaying "Lightcone"

- `/videos/enter-the-lightcone.mp4`:
  - Production video (12.1 seconds)

---

## Known Considerations

### Icon Implementation
The "Enter the Lightcone" page uses:
```jsx
<Icon icon="lightbulb" size={24} color="#9FBFC4" />
<Icon icon="code" size={24} color="#9FBFC4" />
```

**Potential Issue**: If Mintlify's `Icon` component doesn't work in custom mode, icons may not display.

**Fallback Options**:
1. Use Font Awesome icons (Mintlify-supported)
2. Use SVG icons directly (confirmed working approach)
3. Use emoji icons (simple but less professional)

**Action**: Test in production. If icons don't render, implement fallback.

---

## Success Criteria

✅ No duplicate or unnecessary asset files
✅ All navigation links work correctly
✅ "Enter the Lightcone" page displays perfectly
✅ Video plays smoothly with proper looping
✅ Cards and icons render correctly
✅ No console errors or warnings
✅ Responsive design works on all screen sizes
✅ Clean git history with production commit
✅ Team has reviewed and approved
✅ Successfully deployed to production
✅ No broken links anywhere in the docs

---

## Emergency Rollback Plan

If issues arise post-deployment:
1. Keep current git commit hash documented
2. Have previous stable commit ready for rollback
3. Know how to quickly revert in Mintlify dashboard
4. Have team contact list for quick communication

---

## Notes

- **All visible content preserved**: No pages deleted, no content changed
- **Backend cleanup only**: Removing duplicates and unused files
- **Quality focus**: Testing, documentation, and polish
- **Team-ready**: Professional appearance for coworker review

---

*Last Updated: January 23, 2026*
*Created by: Claude & Team*
