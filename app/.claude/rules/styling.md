# Styling Rules

## Current Styling System
- React Native `StyleSheet.create` for component styles
- Shared tokens from `src/constants/theme.ts`
- `src/global.css` only for web-specific global styles

## Rules
- Reuse `Colors`, `Spacing`, and other exported tokens before introducing new raw values.
- Keep styling close to the component unless it is a reusable token.
- Prefer native layout and spacing primitives over one-off wrappers.
- Use platform-specific styling files when web requires different behavior.
- Do not introduce Tailwind, CSS Modules, or styled-components into the app project without an intentional migration.
