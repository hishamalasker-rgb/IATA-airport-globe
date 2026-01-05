# Cloud Deployment Guide

This guide provides step-by-step instructions for deploying the IATA Airport Globe application to various cloud platforms.

## Prerequisites

- A GitHub account
- The repository forked or cloned to your GitHub account

## Deployment Options

### Option 1: Vercel (Recommended - Fastest & Easiest)

Vercel is a serverless platform perfect for static sites with automatic deployments.

#### Steps:

1. **Sign up for Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Sign up with your GitHub account (free tier available)

2. **Import Your Repository**
   - Click "Add New Project"
   - Select "Import Git Repository"
   - Choose your `IATA-airport-globe` repository
   - Click "Import"

3. **Configure Project**
   - Project Name: `iata-airport-globe` (or your preferred name)
   - Framework Preset: Other
   - Root Directory: `./`
   - Build Command: Leave empty (static site)
   - Output Directory: Leave empty
   - Click "Deploy"

4. **Access Your Site**
   - Your site will be live at `https://your-project-name.vercel.app`
   - Vercel automatically deploys on every push to your main branch

#### Custom Domain (Optional)
- Go to Project Settings → Domains
- Add your custom domain and follow DNS configuration instructions

---

### Option 2: Netlify

Netlify is another excellent platform for static site hosting with continuous deployment.

#### Steps:

1. **Sign up for Netlify**
   - Go to [netlify.com](https://netlify.com)
   - Sign up with your GitHub account (free tier available)

2. **Import Your Repository**
   - Click "Add new site" → "Import an existing project"
   - Choose "Deploy with GitHub"
   - Authorize Netlify to access your repositories
   - Select your `IATA-airport-globe` repository

3. **Configure Build Settings**
   - Site name: `iata-airport-globe` (or your preferred name)
   - Build command: Leave empty
   - Publish directory: `.`
   - Click "Deploy site"

4. **Access Your Site**
   - Your site will be live at `https://your-site-name.netlify.app`
   - Automatic deployments on every push

#### Custom Domain (Optional)
- Go to Site settings → Domain management
- Add your custom domain

---

### Option 3: GitHub Pages (Free)

GitHub Pages is a free hosting service directly integrated with GitHub.

#### Steps:

1. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click "Settings"
   - Scroll down to "Pages" section (left sidebar)

2. **Configure Source**
   - Source: Select "Deploy from a branch"
   - Branch: Select `main` (or your default branch)
   - Folder: Select `/ (root)`
   - Click "Save"

3. **Wait for Deployment**
   - GitHub will build and deploy your site (takes 1-2 minutes)
   - A green checkmark will appear when deployment is complete

4. **Access Your Site**
   - Your site will be live at:
     - `https://[username].github.io/IATA-airport-globe/`
   - The URL is shown in the Pages settings section

#### Custom Domain (Optional)
- In the Pages settings, add your custom domain
- Configure DNS with your domain provider

---

### Option 4: Cloudflare Pages

#### Steps:

1. **Sign up for Cloudflare Pages**
   - Go to [pages.cloudflare.com](https://pages.cloudflare.com)
   - Sign up (free tier available)

2. **Connect Repository**
   - Click "Create a project"
   - Connect your GitHub account
   - Select your `IATA-airport-globe` repository

3. **Configure Build**
   - Project name: `iata-airport-globe`
   - Production branch: `main`
   - Build command: Leave empty
   - Build output directory: `/`
   - Click "Save and Deploy"

4. **Access Your Site**
   - Your site will be live at `https://iata-airport-globe.pages.dev`

---

### Option 5: AWS S3 + CloudFront

For AWS users, you can host the site on S3 with CloudFront CDN.

#### Steps:

1. **Create S3 Bucket**
   ```bash
   aws s3 mb s3://iata-airport-globe --region us-east-1
   ```

2. **Configure Bucket for Static Website Hosting**
   ```bash
   aws s3 website s3://iata-airport-globe --index-document index.html
   ```

3. **Upload Files**
   ```bash
   aws s3 sync . s3://iata-airport-globe --exclude ".git/*" --exclude "README.md"
   ```

4. **Set Bucket Policy** (make public)
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::iata-airport-globe/*"
       }
     ]
   }
   ```

5. **Optional: Add CloudFront CDN**
   - Create CloudFront distribution
   - Set S3 bucket as origin
   - Configure SSL certificate

---

## Testing Locally

Before deploying, you can test the site locally:

```bash
# Using Node.js serve package
npx serve .

# Or using Python
python3 -m http.server 8000

# Or using PHP
php -S localhost:8000
```

Then open `http://localhost:8000` in your browser.

---

## Important Notes

### Mapbox Token
The current code includes a Mapbox access token. For production deployments:

1. **Create your own Mapbox account** at [mapbox.com](https://mapbox.com)
2. **Generate a new access token** in your Mapbox account dashboard
3. **Replace the token** in both `index.html` and `advanced.html`:
   ```javascript
   mapboxgl.accessToken = "YOUR_NEW_MAPBOX_TOKEN_HERE";
   ```
4. **Recommended**: Use environment variables or URL restrictions to protect your token

### File Structure
- `index.html` - Simple version of the globe
- `advanced.html` - Enhanced version with search and style switching
- `vercel.json` - Vercel deployment configuration
- `netlify.toml` - Netlify deployment configuration
- `package.json` - Project metadata and scripts

### Security Best Practices
- Never commit API keys or secrets to the repository
- Use environment variables for sensitive data
- Set up URL restrictions on your Mapbox token
- Enable HTTPS (automatic on all recommended platforms)

---

## Troubleshooting

### Site Not Loading
- Check browser console for errors
- Verify Mapbox token is valid
- Ensure all files are uploaded correctly

### CORS Errors
- The app fetches data from `ourairports.com` - ensure CORS is allowed
- Most modern browsers support this; check console for specific errors

### Deployment Failed
- Check build logs in your deployment platform
- Ensure all required files are in the repository
- Verify configuration files are correct

---

## Continuous Deployment

All recommended platforms (Vercel, Netlify, GitHub Pages, Cloudflare Pages) support automatic deployments:

- **Automatic**: Every push to main branch triggers a new deployment
- **Preview**: Pull requests get preview URLs
- **Rollback**: Easy rollback to previous versions

---

## Cost Comparison

| Platform | Free Tier | Bandwidth | Custom Domain | SSL |
|----------|-----------|-----------|---------------|-----|
| **Vercel** | ✅ 100GB/month | Generous | ✅ Yes | ✅ Auto |
| **Netlify** | ✅ 100GB/month | Generous | ✅ Yes | ✅ Auto |
| **GitHub Pages** | ✅ 100GB/month | Soft limits | ✅ Yes | ✅ Auto |
| **Cloudflare Pages** | ✅ Unlimited | Unlimited | ✅ Yes | ✅ Auto |
| **AWS S3** | 💰 Pay-as-you-go | Pay per GB | ✅ Yes | 💰 Via CloudFront |

---

## Getting Help

- **Repository Issues**: Open an issue on GitHub
- **Platform Support**: Check documentation for each platform
- **Mapbox Issues**: See [Mapbox documentation](https://docs.mapbox.com)

---

## Next Steps

1. Choose a deployment platform from the options above
2. Follow the step-by-step instructions
3. Share your live URL!
4. Consider adding a custom domain
5. Monitor usage and performance

Happy deploying! 🚀
