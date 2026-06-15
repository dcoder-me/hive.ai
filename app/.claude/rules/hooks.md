---
paths:
  - "src/hooks/**/*.ts"
  - "src/hooks/**/*.tsx"
---
# Hooks Rules

## Naming
- Hook files stay kebab-case: `use-theme.ts`
- Exported hook names stay camelCase with `use` prefix: `useTheme`

## Rules
- Keep hooks focused on one concern.
- Add JSDoc with `@param` and `@returns` to exported hooks.
- Prefer composition of small hooks over one large hook.
- Do not call hooks conditionally.
- Avoid `useMemo` and `useCallback` by default unless there is a real need or existing local pattern.
- Platform-specific hooks may use `.web.ts` variants when needed.
