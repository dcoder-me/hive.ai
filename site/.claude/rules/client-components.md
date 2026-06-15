---
paths:
  - "app/**/*.tsx"
  - "components/**/*.tsx"
---
# Client Component Rules

## When To Use `use client`
- Only when the component needs interactivity, state, effects, refs, browser APIs, or client-only libraries.
- Push the client boundary down as far as possible.
- Keep pages and layouts server components unless they truly need client behavior.

## Rules
- Do not fetch data in `useEffect` by default if server rendering can do it cleanly.
- Do not turn an entire page into a client component because one child needs interactivity.
- Keep client-only logic isolated in the smallest reasonable component.
- If the site grows operator tooling, keep tables, filters, and local interactions in focused client islands.
