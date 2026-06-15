---
paths:
  - "app/**/*.tsx"
  - "components/**/*.tsx"
  - "hooks/**/*.ts"
  - "hooks/**/*.tsx"
---
# Hooks Rules

## Naming
- Hook files stay kebab-case.
- Hook names start with `use`.

## Rules
- Add JSDoc with `@param` and `@returns` to exported hooks.
- Keep hooks focused on UI behavior or local client state.
- Do not create hooks for server-rendering concerns that can stay in server components.
- Do not call hooks conditionally.
- Avoid `useMemo` and `useCallback` by default unless there is a clear benefit.
