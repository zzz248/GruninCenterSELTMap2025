# SELT Map - Social Enterprise Legislative Tracker

An interactive map visualization tracking corporate social enterprise legislation across US states from 2009-2024.

## 🏗️ File Structure

```
selt-map/
├── index.html              # Main interactive map page
├── js/
│   ├── map-data.js         # Legislative data and processing functions
│   └── map-app.js          # Main application logic and map functionality
├── data/                   # Your CSV files will go here
│   ├── spc-data.csv        # Social Purpose Corporation data
│   ├── l3c-data.csv        # L3C data
│   ├── bllc-data.csv       # Benefit LLC data
│   ├── spblp-data.csv      # Social Purpose Benefit LP data
│   └── bcorp-data.csv      # Benefit Corporation data
├── states/                 # Individual state pages
│   ├── ca.html             # California example (template for others)
│   ├── ny.html             # New York page
│   ├── tx.html             # Texas page
│   └── ... (48 more state pages)
└── README.md               # This file
```

## 🚀 Quick Start

1. **Save the files**: Copy each code artifact into its respective file:
   - Save `index.html` in your main `selt-map` folder
   - Save `map-data.js` in the `js/` folder  
   - Save `map-app.js` in the `js/` folder
   - Save `ca.html` in the `states/` folder
   - Save this README as `README.md`

2. **Test locally**: Open `index.html` in your browser to see the map

3. **Deploy to GitHub Pages**:
   - Commit and push all files to your repository
   - Go to Settings > Pages in your GitHub repo
   - Select "Deploy from a branch" and choose "main"
   - Your map will be live at `https://yourusername.github.io/selt-map`

## 📊 Data Integration

### Current Status
The map currently uses **sample data** in `map-data.js`. To integrate your real CSV data:

### Option 1: Replace Sample Data (Recommended)
1. Edit `js/map-data.js`
2. Replace the `legislativeData` object with your processed CSV data
3. Maintain the same structure:
```javascript
const legislativeData = {
  2009: {
    'CA': { forms: ['L3C'], failed: [], rescinded: [] },
    'VT': { forms: ['L3C'], failed: [], rescinded: [] }
  },
  // ... more years
};
```

### Option 2: Dynamic CSV Loading
Add CSV processing to load your data files dynamically:
```javascript
// In map-app.js, add CSV loading functionality
async loadCSVData() {
  // Load and process your CSV files from /data folder
  // Use Papa Parse or similar library
}
```

## 🎯 Corporate Forms Tracked

- **SPC** - Social Purpose Corporation
- **L3C** - Low-profit Limited Liability Company  
- **BLLC** - Benefit Limited Liability Company
- **SPBLP** - Social Purpose Benefit Limited Partnership
- **BCORP** - Benefit Corporation

## 🏛️ State Pages

### Current Status
- ✅ `ca.html` - Complete California template
- ⏳ 49 remaining state pages needed

### Creating State Pages
1. Copy `states/ca.html` as a template
2. Replace California-specific content:
   - State name in title and headers
   - Statistics and timeline data
   - Legislative history details
3. Update the `form-item` sections based on each state's enacted forms
4. Customize the timeline with actual legislative events

### Automated Generation
For efficiency, consider creating a script to generate all 50 state pages from your data.

## 🎨 Customization

### Colors and Styling
- **Main gradient**: Edit the CSS `background: linear-gradient()` values
- **State colors**: Modify `fillColor` in `getStateStyle()` function
- **Emoji system**: Already implemented as requested:
  - ⚪ No activity
  - ✅ One form enacted
  - ✅✅ Two forms enacted  
  - ✅✅✅ Three+ forms enacted
  - ❌ Failed legislation
  - ⛔ One form rescinded
  - ⛔⛔ Two forms rescinded

### Map Features
- **Zoom levels**: Adjust `minZoom` and `maxZoom` in map initialization
- **Center point**: Modify coordinates in `initializeMap()`
- **Popup content**: Customize `createPopupContent()` function

## 🔧 Technical Details

### Dependencies
- **Leaflet.js** - Interactive mapping (loaded from CDN)
- **OpenStreetMap** - Base map tiles
- **Vanilla JavaScript** - No additional frameworks required

### Browser Support
- Modern browsers with ES6+ support
- Mobile responsive design included
- GitHub Pages compatible (static files only)

## 📱 Mobile Optimization

The map includes responsive design:
- Touch-friendly controls
- Optimized popup sizing
- Responsive grid layouts
- Mobile-first CSS approach

## 🐛 Troubleshooting

### Map Not Loading
1. Check browser console for errors
2. Ensure all file paths are correct
3. Verify internet connection (map tiles load from external CDN)

### Data Not Displaying
1. Check `legislativeData` structure in `map-data.js`
2. Verify state codes match exactly (e.g., 'CA', 'NY', 'TX')
3. Ensure year format is correct (numbers, not strings)

### State Pages Not Found
1. Create the missing state HTML files
2. Check file naming convention: `states/[state-code].html`
3. Verify links in popup content match file names

## 🚀 Next Steps

1. **Replace sample data** with your actual CSV data
2. **Create remaining 49 state pages** using the California template
3. **Test thoroughly** before deploying to GitHub Pages
4. **Optimize performance** if needed for large datasets
5. **Add additional features** as requirements evolve

## 📞 Support

This system is designed to be self-contained and easy to modify. Key areas for customization:
- Data in `map-data.js`
- Styling in `index.html` CSS
- Functionality in `map-app.js`
- Individual state content in `states/` folder

---

**Ready to deploy!** 🎉 Your interactive SELT map is configured for immediate use with GitHub Pages.