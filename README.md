# LangGraph — music assistant prototype

Experimental TypeScript base for exploring language-model conversations and structured outputs with Zod.

## Implemented components

- Conversation graph with conditional routing.
- Model integration through OpenRouter.
- Response and music-preference extraction schemas.
- Graph registration in langgraph.json.

## Project status

Preference persistence and summarization nodes are placeholders: they currently return state without performing those operations. Memory exposed by the factory is also simulated. This is a prototype, not a complete assistant with persistent memory.

## Run locally

```bash
npm ci
cp .env.example .env
# Set OPENROUTER_API_KEY and review the model in src/config.ts.
npm run langgraph:server
```

Check that the chosen model supports the client's structured output. langgraph.json exports the song_highlights graph from src/graph/factory.ts.

## Structure

- `src/graph/`: graph definition, factory and nodes.
- `src/prompts/`: prompts and schemas.
- `src/services/`: provider client.

## Limitations

No test suite is implemented. Execution depends on credentials and a compatible model; documentation does not complete the unfinished nodes.
