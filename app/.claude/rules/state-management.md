---
paths:
  - "src/**/*.ts"
  - "src/**/*.tsx"
---
# State Management Rules

## Preferred Order
1. Component-local state with `useState`
2. Shared logic through custom hooks or context when truly needed
3. External state library only when the app has a clear cross-screen need

## Rules
- Do not introduce Zustand or another store by default; the current app does not use one.
- Keep navigation state in the router, not in duplicate component state.
- Do not lift state higher than necessary.
- Avoid prop drilling shared state through intermediate components.
- When a leaf component needs shared state later, prefer a hook or context at the point of use over pass-through props.
