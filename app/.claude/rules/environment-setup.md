# Environment Setup

## Scripts
- `npm run start` — start Expo dev server
- `npm run ios` — run iOS flow
- `npm run android` — run Android flow
- `npm run web` — run web build
- `npm run lint` — run Expo lint

## Current State
- No required environment variables are defined in the current app project files.

## Rules
- Do not invent environment variables unless a feature actually needs them.
- If a new env var is added, document it and use Expo-compatible naming and access patterns.
- Treat secrets as backend concerns unless the app explicitly requires a client-safe public value.
