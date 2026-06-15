# React Component Rules

## Structure
- Functional components only.
- Use `function ComponentName()` declarations.
- Keep file names kebab-case and component names PascalCase.
- Use named exports unless a Next special file requires a default export.

## Patterns
- Prefer server-rendered components when interactivity is unnecessary.
- Keep components small and purposeful.
- Pass only data the component actually uses.
- Avoid prop drilling shared state through intermediate components.
- Split reusable UI into separate files when a page starts getting crowded.
