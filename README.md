# IATA Airport Globe 🌍✈️

An interactive 3D globe visualization displaying all IATA airport codes worldwide using Mapbox GL JS.

## ✨ Features

- **Interactive 3D Globe**: Explore airports on a beautiful 3D globe projection
- **Airport Clustering**: Smart clustering at lower zoom levels for better performance
- **Search Functionality**: Search by IATA (3-letter) or ICAO (4-letter) codes
- **Multiple Map Styles**: Switch between Light, Dark, and Satellite views
- **Real-time Data**: Fetches current airport data from OurAirports.com
- **Responsive Design**: Works on desktop and mobile devices

## 🚀 Quick Deploy

Deploy this project to the cloud in minutes! Click one of the buttons below:

### Deploy to Vercel (Recommended)
[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/hishamalasker-rgb/IATA-airport-globe)

### Deploy to Netlify
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/hishamalasker-rgb/IATA-airport-globe)

### Other Options
- **GitHub Pages**: See [DEPLOYMENT.md](DEPLOYMENT.md#option-3-github-pages-free)
- **Cloudflare Pages**: See [DEPLOYMENT.md](DEPLOYMENT.md#option-4-cloudflare-pages)
- **AWS S3**: See [DEPLOYMENT.md](DEPLOYMENT.md#option-5-aws-s3--cloudfront)

### 📚 Documentation
- 📖 **Full Deployment Guide**: [DEPLOYMENT.md](DEPLOYMENT.md)
- ⚡ **Quick Commands**: [QUICK-DEPLOY.md](QUICK-DEPLOY.md)
- 📊 **Platform Comparison**: [PLATFORM-COMPARISON.md](PLATFORM-COMPARISON.md)
- 🤝 **Contributing**: [CONTRIBUTING.md](CONTRIBUTING.md)

## 📂 Files

- **`index.html`** - Simple version of the 3D airport globe
- **`advanced.html`** - Enhanced version with search and style switching
- **`DEPLOYMENT.md`** - Comprehensive deployment guide for all platforms

## 🏃 Run Locally

Test the application on your local machine:

```bash
# Clone the repository
git clone https://github.com/hishamalasker-rgb/IATA-airport-globe.git
cd IATA-airport-globe

# Serve using Node.js (requires Node.js installed)
npx serve .

# Or using Python 3
python3 -m http.server 8000

# Or using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

## 🔑 Mapbox Token

This project uses Mapbox GL JS. The included token is for demonstration purposes.

**For production use:**
1. Create a free account at [mapbox.com](https://mapbox.com)
2. Generate your own access token
3. Replace the token in `index.html` and `advanced.html`:
   ```javascript
   mapboxgl.accessToken = "YOUR_MAPBOX_TOKEN_HERE";
   ```

## 🛠️ Technology Stack

- **Mapbox GL JS v3.6.0** - 3D map rendering and globe projection
- **OurAirports.com API** - Real-time airport data
- **Vanilla JavaScript** - No frameworks, just clean JS
- **HTML5 & CSS3** - Modern web standards

## 📊 Data Source

Airport data is fetched in real-time from [OurAirports.com](https://ourairports.com/), which provides:
- Large, medium, and small airports worldwide
- IATA and ICAO codes
- Geographic coordinates
- Regular updates

## 🌐 Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

Requires WebGL support for 3D rendering.

## 📄 License

MIT License - Feel free to use this project for any purpose.

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## 📞 Support

If you encounter any issues:
1. Check the [DEPLOYMENT.md](DEPLOYMENT.md) troubleshooting section
2. Open an issue on GitHub
3. Review Mapbox documentation for API-related questions

---

**Made with ❤️ for aviation enthusiasts and developers**
