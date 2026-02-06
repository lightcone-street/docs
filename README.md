# Lightcone Documentation

Official documentation for Lightcone - Trade the Impact of World Events.

## 🚀 Quick Start

### Local Development

1. **Install Mintlify CLI**
   ```bash
   npm i -g mint
   ```

2. **Run development server**
   ```bash
   mint dev
   ```

3. **View locally**
   Open `http://localhost:3000` in your browser

### Troubleshooting

- **Dev environment not running?** Run `mint update` to get the latest CLI version
- **404 errors?** Make sure you're in the directory with `docs.json`

## 📁 Project Structure

```
lightcone-docs/
├── api-reference/          # REST API documentation
│   ├── endpoint/          # API endpoint docs
│   └── openapi.json       # OpenAPI spec
├── guides/                # User guides
│   ├── getting-started/   # Getting started guides
│   ├── about-lightcone/   # About Lightcone
│   └── the-trading-*.mdx  # Trading guides
├── websocket/             # WebSocket API docs
├── videos/                # Video assets
├── logo/                  # Logo files
├── docs.json              # Mintlify configuration
└── README.md              # This file
```

## 🎨 Custom Pages

### Enter the Lightcone Page
The `/guides/getting-started/enter-the-lightcone.mdx` page features:
- Full-screen video background with custom loop
- Grain overlay effect for visual appeal
- Two interactive cards (Learn & API)
- Hidden navigation for immersive experience
- Responsive design that adapts to mobile

**Technical Details:**
- Video: 7.6MB, 12.1 seconds, auto-plays with blur effect
- Icons: Mintlify Icon component (lightbulb, code)
- Colors: #9FBFC4 (titles), rgba(0,0,0,0.4) (card background)
- Border: 1px solid rgba(159, 191, 196, 0.3)

## ⚙️ Configuration

### Key Settings in `docs.json`
- **Theme:** willow
- **Primary Color:** #6366F1
- **Background (Light Mode):** #DDE8E8
- **Logo:** Text-based "Lightcone" (light.svg, dark.svg)

### Navigation Structure
- **Guides Tab:** Getting started, Trading, About Lightcone
- **API Reference Tab:** REST API, WebSocket API

## 📝 Adding New Pages

1. Create `.mdx` file in appropriate directory
2. Add frontmatter with title and description
3. Update `docs.json` navigation to include new page
4. Test locally with `mint dev`

## 🚢 Deployment

Changes are automatically deployed when pushed to the default branch via Mintlify's GitHub integration.

### Pre-Deploy Checklist
- [ ] Run `mint dev` and test all pages
- [ ] Check for console errors
- [ ] Verify all links work
- [ ] Test on mobile/tablet viewports
- [ ] Review video playback on "Enter the Lightcone" page

## 📚 Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [Lightcone Website](https://lightcone.xyz)
- [API Reference](https://docs.lightcone.xyz/api-reference/rest-introduction)

## 🤝 Contributing

For documentation updates or fixes, please follow these guidelines:
1. Test changes locally before committing
2. Ensure all links work
3. Follow existing formatting conventions
4. Update navigation in `docs.json` if adding/removing pages

## 📧 Support

Questions or issues? Contact [support@lightcone.xyz](mailto:support@lightcone.xyz)

---

Built with [Mintlify](https://mintlify.com)
