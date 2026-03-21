# Cloudflare Pages Deployment Guide

This website is configured for deployment on Cloudflare Pages.

## Deployment Settings

When setting up your Cloudflare Pages project, use these settings:

### Build Configuration
- **Framework preset**: None (Static HTML)
- **Build command**: `npm run build`
- **Build output directory**: `.` (root directory)
- **Node version**: 20 (specified in `.node-version`)

### Environment Variables
No environment variables required for basic deployment.

## Deploy via Wrangler CLI

### Prerequisites
```bash
npm install -g wrangler
wrangler login
```

### Deploy
```bash
# Build the CSS
npm run build

# Deploy to Cloudflare Pages
wrangler pages deploy . --project-name=novaa-cabs
```

## Deploy via GitHub Integration

1. Push your code to GitHub
2. Go to Cloudflare Dashboard > Pages
3. Click "Create a project" > "Connect to Git"
4. Select your repository
5. Configure build settings as above
6. Click "Save and Deploy"

## Files

- `.node-version` - Specifies Node.js version
- `_headers` - Custom HTTP headers for security and caching
- `_redirects` - 404 error handling
- `wrangler.toml` - Wrangler CLI configuration
- `package.json` - Build scripts and dependencies

## Development

```bash
# Install dependencies
npm install

# Watch mode for development
npm run dev

# Build for production
npm run build
```

## Custom Domain

After deployment, you can add a custom domain in Cloudflare Pages dashboard:
1. Go to your Pages project
2. Click "Custom domains"
3. Add your domain
4. Update DNS records as instructed
