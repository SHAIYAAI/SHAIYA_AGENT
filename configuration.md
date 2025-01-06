# Configuration Guide

## Environment Variables

Create a `.env` file in the root directory:

```env
# Core Configuration
NEURAL_CORE_VERSION=2.1
RESPONSE_TIMEOUT=5000
MAX_TOKENS=2048

# API Configuration
API_PORT=3000
API_URL=http://localhost:3000
WS_URL=ws://localhost:3000

# Security
JWT_SECRET=your-secret-key
RATE_LIMIT=100
```

## Neural Core Settings

```typescript
// config/neural.ts
export default {
  version: '2.1',
  models: {
    default: 'gpt-4',
    fallback: 'gpt-3.5-turbo'
  },
  processing: {
    temperature: 0.7,
    maxTokens: 2048,
    topP: 1
  }
};
```

## UI Configuration

```typescript
// config/ui.ts
export default {
  theme: {
    primary: '#6366f1',
    secondary: '#312e81',
    accent: '#818cf8'
  },
  terminal: {
    maxHistory: 100,
    promptChar: '>'
  }
};
```

## Performance Tuning

```typescript
// config/performance.ts
export default {
  cache: {
    maxSize: 1000,
    ttl: 3600
  },
  rateLimit: {
    window: 60000,
    max: 100
  }
};
```