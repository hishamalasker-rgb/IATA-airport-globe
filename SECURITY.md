# Security Policy

## Reporting Security Issues

If you discover a security vulnerability in this project, please report it by emailing the repository owner directly. Please do not open a public issue.

## Security Best Practices

### API Keys and Tokens

1. **Mapbox Access Token**
   - Replace `YOUR_MAPBOX_TOKEN_HERE` in `index.html` and `advanced.html` with your own token
   - Never commit API keys to the repository
   - Use URL restrictions on your Mapbox token to limit usage to your domain
   - Rotate tokens regularly
   - Monitor token usage in your Mapbox dashboard

2. **Token Configuration**
   - Go to [Mapbox Account](https://account.mapbox.com/access-tokens/)
   - Create a new token with URL restrictions
   - Add your deployment domain (e.g., `https://your-site.vercel.app/*`)
   - Use separate tokens for development and production

### Deployment Security

1. **HTTPS Only**
   - All recommended platforms (Vercel, Netlify, GitHub Pages, Cloudflare) provide automatic HTTPS
   - Never deploy without SSL/TLS encryption

2. **Environment Variables**
   - Use environment variables for sensitive data when possible
   - For static sites, consider using a backend proxy for API keys
   - Never expose tokens in client-side code in production

3. **Content Security Policy**
   - Consider adding CSP headers to prevent XSS attacks
   - Example for Vercel (`vercel.json`):
     ```json
     {
       "headers": [
         {
           "source": "/(.*)",
           "headers": [
             {
               "key": "Content-Security-Policy",
               "value": "default-src 'self'; script-src 'self' 'unsafe-inline' https://api.mapbox.com; style-src 'self' 'unsafe-inline' https://api.mapbox.com; connect-src 'self' https://api.mapbox.com https://ourairports.com"
             }
           ]
         }
       ]
     }
     ```

4. **Dependency Security**
   - Regularly check for updates to Mapbox GL JS
   - Monitor security advisories for dependencies
   - Use Dependabot or similar tools for automated updates

### Data Security

1. **User Data**
   - This application does not collect or store user data
   - No cookies are used
   - No analytics by default

2. **External APIs**
   - Airport data is fetched from OurAirports.com (public API)
   - Mapbox GL JS is loaded from CDN
   - Both use HTTPS

### Common Vulnerabilities

1. **Cross-Site Scripting (XSS)**
   - Minimal risk: No user input is rendered without sanitization
   - Airport data is from trusted source (OurAirports.com)

2. **Cross-Site Request Forgery (CSRF)**
   - Not applicable: This is a read-only static application

3. **API Token Exposure**
   - ⚠️ **HIGH PRIORITY**: Replace default Mapbox token
   - Use URL restrictions on production tokens
   - Monitor usage for suspicious activity

### Deployment Security Checklist

Before deploying to production:

- [ ] Replace `YOUR_MAPBOX_TOKEN_HERE` with your own token
- [ ] Configure URL restrictions on your Mapbox token
- [ ] Verify HTTPS is enabled
- [ ] Review and test the deployed site
- [ ] Monitor token usage in Mapbox dashboard
- [ ] Set up alerts for unusual traffic patterns
- [ ] Review platform security settings (Vercel/Netlify/etc.)
- [ ] Consider adding rate limiting if needed
- [ ] Keep documentation updated with security practices

### Security Updates

This section will be updated as security recommendations evolve. Last updated: 2026-01-05

### Third-Party Security

1. **Mapbox GL JS**
   - Current version: 3.6.0
   - Check for updates: https://github.com/mapbox/mapbox-gl-js/releases
   - Security advisories: https://github.com/mapbox/mapbox-gl-js/security

2. **OurAirports.com**
   - Public data source
   - No authentication required
   - Data is parsed client-side

### Incident Response

If a security incident occurs:

1. Immediately rotate any exposed API keys
2. Review access logs for suspicious activity
3. Update the repository with fixes
4. Notify users if necessary
5. Document the incident and response

### Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Mapbox Security Best Practices](https://docs.mapbox.com/help/troubleshooting/how-to-use-mapbox-securely/)
- [GitHub Security Features](https://docs.github.com/en/code-security)

---

For general questions, see [CONTRIBUTING.md](CONTRIBUTING.md).
