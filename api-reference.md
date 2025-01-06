# API Reference

## Core API

### Agent Class

```typescript
interface AgentConfig {
  id: string;
  model: string;
  temperature?: number;
  maxTokens?: number;
}

class Agent {
  constructor(config: AgentConfig);
  initialize(): Promise<void>;
  generateResponse(input: string): Promise<string>;
  learn(data: TrainingData): Promise<void>;
}
```

### Response Types

```typescript
interface Response {
  text: string;
  confidence: number;
  timestamp: number;
}

interface ErrorResponse {
  code: string;
  message: string;
  details?: any;
}
```

## WebSocket Events

### Client → Server

- `connect`: Initialize connection
- `message`: Send message
- `typing`: User is typing
- `disconnect`: Close connection

### Server → Client

- `response`: AI response
- `error`: Error message
- `status`: Agent status update

## HTTP Endpoints

### POST /api/chat
Send a message to the AI agent

Request:
```json
{
  "message": "string",
  "context": "object?",
  "options": "object?"
}
```

Response:
```json
{
  "response": "string",
  "timestamp": "number",
  "metadata": "object?"
}
```

### GET /api/status
Get agent status

Response:
```json
{
  "status": "string",
  "uptime": "number",
  "version": "string"
}
```