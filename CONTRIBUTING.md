# Contributing to IATA Airport Globe

Thank you for your interest in contributing to the IATA Airport Globe project! This guide will help you get started.

## 🚀 Quick Start for Development

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, or Edge)
- A text editor or IDE
- Basic knowledge of HTML, CSS, and JavaScript
- (Optional) Node.js for local testing

### Setting Up Your Development Environment

1. **Fork the repository**
   - Click the "Fork" button on GitHub
   - Clone your fork locally:
     ```bash
     git clone https://github.com/YOUR_USERNAME/IATA-airport-globe.git
     cd IATA-airport-globe
     ```

2. **Run locally**
   ```bash
   # Using Node.js
   npx serve .
   
   # Or using Python
   python3 -m http.server 8000
   ```

3. **Open in browser**
   - Navigate to `http://localhost:8000`
   - Test both `index.html` and `advanced.html`

## 📝 Project Structure

```
IATA-airport-globe/
├── index.html          # Simple version of the globe
├── advanced.html       # Enhanced version with search
├── README.md           # Project overview
├── DEPLOYMENT.md       # Deployment instructions
├── CONTRIBUTING.md     # This file
├── package.json        # Project metadata
├── vercel.json         # Vercel deployment config
├── netlify.toml        # Netlify deployment config
└── .github/
    └── workflows/
        └── deploy.yml  # GitHub Pages deployment
```

## 🔧 Making Changes

### Code Style Guidelines

1. **HTML**
   - Use HTML5 standards
   - Maintain proper indentation (2 spaces)
   - Keep inline styles minimal (use CSS classes)

2. **CSS**
   - Use modern CSS features
   - Keep styles organized and commented
   - Maintain responsive design principles

3. **JavaScript**
   - Use ES6+ features (const, let, arrow functions)
   - Write clear, self-documenting code
   - Add comments for complex logic
   - Use async/await for asynchronous operations

### Testing Your Changes

Before submitting a pull request:

1. **Visual Testing**
   - Test on multiple browsers (Chrome, Firefox, Safari)
   - Test on mobile devices (or use browser dev tools)
   - Verify the 3D globe renders correctly
   - Check that airport markers appear

2. **Functional Testing**
   - Test airport search functionality (advanced.html)
   - Test map style switching
   - Test zoom and pan interactions
   - Verify clustering works at different zoom levels

3. **Performance Testing**
   - Check loading times
   - Monitor browser console for errors
   - Verify smooth interactions

## 🐛 Reporting Bugs

Found a bug? Please open an issue with:

- **Title**: Brief description of the issue
- **Description**: Detailed explanation
- **Steps to reproduce**: How to trigger the bug
- **Expected behavior**: What should happen
- **Actual behavior**: What actually happens
- **Browser/OS**: Your environment details
- **Screenshots**: If applicable

## 💡 Suggesting Features

Have an idea? Open an issue with:

- **Title**: Feature name
- **Description**: What the feature does
- **Use case**: Why it's useful
- **Implementation ideas**: (Optional) How it could work

## 🔀 Pull Request Process

1. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Follow the code style guidelines
   - Test thoroughly
   - Keep changes focused and minimal

3. **Commit your changes**
   ```bash
   git add .
   git commit -m "Add: brief description of changes"
   ```
   
   Commit message prefixes:
   - `Add:` - New features
   - `Fix:` - Bug fixes
   - `Update:` - Updates to existing features
   - `Docs:` - Documentation changes
   - `Style:` - Code style changes (no logic changes)

4. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open a Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your branch
   - Fill out the PR template
   - Link any related issues

## 🎯 Good First Issues

New to contributing? Look for issues labeled:
- `good first issue`
- `beginner-friendly`
- `documentation`

## 📚 Resources

- [Mapbox GL JS Documentation](https://docs.mapbox.com/mapbox-gl-js/)
- [OurAirports API](https://ourairports.com/help/data-dictionary.html)
- [MDN Web Docs](https://developer.mozilla.org/)

## 🏆 Recognition

All contributors will be recognized! Your contributions help make this project better for everyone.

## 📧 Questions?

- Open an issue for project-related questions
- Check existing issues and pull requests first

## 📜 Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Provide constructive feedback
- Focus on what's best for the community

## 🔐 Security

Found a security vulnerability? Please email the repository owner directly instead of opening a public issue.

---

Thank you for contributing to IATA Airport Globe! 🌍✈️
