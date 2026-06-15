# React Component Rules

## Structure
- Functional components only.
- Use `function ComponentName()` declarations for components.
- Keep filenames kebab-case and component names PascalCase.
- Use named exports unless the route/layout file requires a default export.

## Patterns
- Keep components focused and split files before they become large.
- Accept props only when the component actually renders or directly uses them.
- Pull shared state from hooks/context/store at the leaf instead of forwarding handlers through intermediate components.
- Prefer `StyleSheet.create` for React Native styles and keep shared theme values in `src/constants/theme.ts`.
- Prefer `function ComponentName()` plus local helpers over wrapper-heavy abstractions in this early-stage app.

## Platform Rules
- If web needs a different implementation, create `.web.tsx` instead of cluttering one file with platform branches.
- Guard platform-specific APIs with `Platform.OS` when a separate file is not warranted.
