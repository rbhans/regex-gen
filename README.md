# Reflow Point Name Regex Generator PWA

A Progressive Web Application for generating regex patterns for Tridium Niagara Reflow point mapping.

## 🚀 Features

- **Generate Regex Patterns** - Create optimized regex for Reflow point identifiers
- **Real-time Testing** - Test your patterns against actual point names
- **PWA Support** - Install as a native app on any device
- **Offline Capable** - Works without internet connection after first load
- **Responsive Design** - Works on desktop, tablet, and mobile
- **Copy to Clipboard** - Easy copying of generated patterns

## 📱 Installation

### GitHub Pages Deployment

1. **Create a new GitHub repository**
2. **Upload these files to your repository:**
   ```
   /
   ├── index.html
   ├── manifest.json
   ├── service-worker.js
   ├── README.md
   └── icons/
       ├── icon-72x72.png
       ├── icon-96x96.png
       ├── icon-128x128.png
       ├── icon-144x144.png
       ├── icon-152x152.png
       ├── icon-192x192.png
       ├── icon-384x384.png
       └── icon-512x512.png
   ```

3. **Enable GitHub Pages:**
   - Go to repository Settings
   - Scroll to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Click "Save"

4. **Access your app:**
   - Your app will be available at: `https://yourusername.github.io/repository-name`
   - Wait a few minutes for deployment

### PWA Installation

Once deployed, users can install the app:

**Desktop (Chrome/Edge):**
- Visit the GitHub Pages URL
- Click the install icon in the address bar
- Or click the three dots menu → "Install [App Name]"

**Mobile (Android/iOS):**
- Visit the GitHub Pages URL in browser
- Android: Tap "Add to Home Screen" notification or browser menu
- iOS: Tap Share button → "Add to Home Screen"

## 🛠️ Development

### Local Development
```bash
# Serve locally (Python)
python -m http.server 8000

# Or using Node.js
npx serve .

# Then visit http://localhost:8000
```

### Icon Generation
You'll need to create app icons in these sizes:
- 72x72, 96x96, 128x128, 144x144, 152x152, 192x192, 384x384, 512x512

**Quick Icon Generation:**
1. Create a 512x512 base icon
2. Use online tools like [RealFaviconGenerator](https://realfavicongenerator.net/)
3. Or use ImageMagick:
```bash
convert icon-512x512.png -resize 192x192 icon-192x192.png
convert icon-512x512.png -resize 72x72 icon-72x72.png
# etc...
```

## 🔧 Customization

### Update App Info
Edit `manifest.json`:
```json
{
  "name": "Your App Name",
  "short_name": "Short Name",
  "description": "Your description"
}
```

### Change Colors
Update theme colors in:
- `manifest.json` - `theme_color` and `background_color`
- `index.html` - `meta name="theme-color"`

### Cache Management
Update `service-worker.js`:
- Change `CACHE_NAME` version when updating
- Add/remove URLs in `urlsToCache`

## 📋 File Structure

```
reflow-regex-generator/
├── index.html          # Main application file
├── manifest.json       # PWA manifest
├── service-worker.js   # Service worker for offline support
├── README.md          # This file
└── icons/             # App icons (you need to create these)
    ├── icon-72x72.png
    ├── icon-96x96.png
    ├── icon-128x128.png
    ├── icon-144x144.png
    ├── icon-152x152.png
    ├── icon-192x192.png
    ├── icon-384x384.png
    └── icon-512x512.png
```

## 🎯 Usage

1. **Add Point Names** - Enter variations of your point names
2. **Generate Regex** - Pattern is automatically created
3. **Test Pattern** - Verify against actual point names
4. **Copy to Reflow** - Use in Reflow's point identifier field

### Reflow Integration
1. In Reflow Equipment Type configuration
2. Set Point Identifier type to "Regular Expression"
3. Paste the generated pattern (including `/` slashes)
4. Save and test with your devices

## 🐛 Troubleshooting

**PWA won't install:**
- Ensure HTTPS (GitHub Pages provides this)
- Check browser console for manifest errors
- Verify all icon files exist

**Offline not working:**
- Check service worker registration in browser DevTools
- Clear cache and reload
- Verify service-worker.js is accessible

**Icons not showing:**
- Create all required icon sizes
- Check file paths in manifest.json
- Ensure icons are in `/icons/` folder

## 📄 License

MIT License - Feel free to use and modify as needed.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

---

**Note:** Remember to create the icon files in the `/icons/` directory. The app will work without them, but won't look professional or install properly as a PWA.
