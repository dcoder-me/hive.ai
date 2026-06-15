# Environment Setup

## Scripts
- `npm run dev`
- `npm run build`
- `npm run start`
- `npm run lint`

## Current State
- No required environment variables are defined by the current site code.

## Rules
- Do not invent env vars without a real feature need.
- If a public env var is added, use the `NEXT_PUBLIC_` prefix.
- If a server-only env var is added, access it directly from `process.env.<name>` in server code only.
