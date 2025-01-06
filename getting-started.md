# Getting Started with SHAIYA

## Prerequisites

- Node.js 16+
- npm or yarn
- Basic knowledge of React and TypeScript

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/shaiya-ai.git
   ```

2. Install dependencies:
   ```bash
   cd shaiya-ai
   npm install
   ```

3. Create environment variables:
   ```bash
   cp .env.example .env
   ```

4. Start development server:
   ```bash
   npm run dev
   ```

## Project Structure

```
shaiya-ai/
├── src/
│   ├── components/     # React components
│   ├── hooks/         # Custom React hooks
│   ├── pages/         # Page components
│   ├── types/         # TypeScript types
│   ├── constants/     # Constants and configurations
│   └── styles/        # Global styles
├── public/           # Static assets
└── github/          # Documentation
```

## Core Components

- **NetworkGrid**: Background visualization
- **Terminal**: Interactive AI interface
- **AgentProfile**: AI agent status display
- **Hero**: Main landing section

## Basic Usage

```typescript
import { Agent } from '@neural/core';

const agent = new Agent({
  id: "unique_agent_id",
  model: "neural-core-v2.1",
  temperature: 0.7
});

await agent.initialize();
```

See [API Reference](api-reference.md) for more details.