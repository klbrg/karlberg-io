# Deployment Guide

## Azure Static Web Apps Deployment

This site is configured for Azure Static Web Apps with automatic deployment from GitHub.

### Prerequisites

- Azure account
- GitHub repository connected to Azure Static Web Apps
- Azure Static Web Apps GitHub Action configured

### Configuration Files

The repository includes two configuration files:

1. **`staticwebapp.config.json`** (root) - Main configuration
2. **`src/staticwebapp.config.json`** - Source directory configuration

### Deployment Steps

1. **Automatic Deployment**
   - Push changes to the `main` branch
   - GitHub Actions automatically builds and deploys
   - Changes go live within minutes

2. **Manual Deployment** (if needed)
   ```bash
   # Install Azure Static Web Apps CLI
   npm install -g @azure/static-web-apps-cli
   
   # Deploy from local
   swa deploy ./src --deployment-token <YOUR_DEPLOYMENT_TOKEN>
   ```

### Environment Configuration

The site uses the following structure:
- **Output location**: `src/`
- **App artifact location**: `src/`
- **No build required** - Pure static HTML/CSS/JS

### Custom Domain Setup

1. Navigate to Azure Portal → Static Web App
2. Go to "Custom domains"
3. Add your domain (e.g., karlberg.io)
4. Configure DNS records:
   - CNAME: `www` → `<your-app>.azurestaticapps.net`
   - ALIAS/ANAME: `@` → `<your-app>.azurestaticapps.net`

### Monitoring & Analytics

Consider adding:
- **Application Insights** for performance monitoring
- **Google Analytics** for visitor tracking
- **Azure Monitor** for uptime monitoring

### Performance Optimization

The site is already optimized with:
- ✅ Minimal external dependencies
- ✅ Optimized CSS (no bloated frameworks)
- ✅ Vanilla JavaScript (no heavy libraries)
- ✅ Lazy-loaded animations
- ✅ Mobile-first responsive design

### SEO Checklist

- ✅ Meta descriptions
- ✅ Open Graph tags
- ✅ Semantic HTML
- ✅ Alt text for icons/images
- ✅ Sitemap (consider adding sitemap.xml)
- ✅ robots.txt (consider adding)

### Future Enhancements

Consider adding:
- Blog section for technical articles
- Contact form with Azure Functions backend
- Dark mode toggle
- Certifications section with badges
- Resume/CV download option
- Case studies for major projects
