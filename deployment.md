# Deployment Guide

## Production Build

1. Create production build:
   ```bash
   npm run build
   ```

2. Preview build:
   ```bash
   npm run preview
   ```

## Deployment Options

### 1. Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/yourusername/shaiya-ai)

Configuration:
```toml
# netlify.toml
[build]
  command = "npm run build"
  publish = "dist"

[context.production.environment]
  NODE_VERSION = "16"
```

### 2. Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/shaiya-ai)

### 3. Docker

```dockerfile
# Dockerfile
FROM node:16-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

Build and run:
```bash
docker build -t shaiya-ai .
docker run -p 3000:3000 shaiya-ai
```

## Environment Setup

1. Configure environment variables
2. Set up SSL certificates
3. Configure domain and DNS
4. Set up monitoring

## Performance Optimization

- Enable compression
- Configure caching
- Set up CDN
- Implement rate limiting