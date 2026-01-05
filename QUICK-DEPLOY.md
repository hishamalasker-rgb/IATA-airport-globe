# Quick Deployment Reference

## One-Click Deploy

### Vercel
```bash
# Install Vercel CLI (one-time)
npm i -g vercel

# Deploy
vercel

# Deploy to production
vercel --prod
```

### Netlify
```bash
# Install Netlify CLI (one-time)
npm i -g netlify-cli

# Deploy
netlify deploy

# Deploy to production
netlify deploy --prod
```

## Manual Deploy Commands

### GitHub Pages
Already configured! Just push to main branch:
```bash
git push origin main
```
The GitHub Action will automatically deploy.

### AWS S3
```bash
# Create bucket
aws s3 mb s3://your-bucket-name

# Upload files
aws s3 sync . s3://your-bucket-name --exclude ".git/*"

# Enable static website hosting
aws s3 website s3://your-bucket-name --index-document index.html
```

### Cloudflare Pages
```bash
# Install Wrangler (one-time)
npm i -g wrangler

# Login
wrangler login

# Deploy
wrangler pages deploy . --project-name=iata-airport-globe
```

## Local Testing

```bash
# Using npx (no installation needed)
npx serve .

# Using package.json scripts
npm start           # Port 8080
npm run dev         # Port 3000

# Using Python
python3 -m http.server 8000

# Using PHP
php -S localhost:8000
```

## Environment Variables

If using your own Mapbox token:

### Vercel
```bash
vercel env add MAPBOX_TOKEN
```

### Netlify
```bash
netlify env:set MAPBOX_TOKEN your_token_here
```

## Status Check

### Vercel
```bash
vercel ls
```

### Netlify
```bash
netlify status
```

## View Logs

### Vercel
```bash
vercel logs
```

### Netlify
```bash
netlify logs
```

## Domain Setup

### Vercel
```bash
vercel domains add your-domain.com
```

### Netlify
```bash
netlify domains:add your-domain.com
```

---

For detailed instructions, see [DEPLOYMENT.md](DEPLOYMENT.md)
