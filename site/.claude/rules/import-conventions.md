# Import Conventions

## Path Alias
- Use `@/*` for root imports as configured in `tsconfig.json`.

## Import Order
1. React and Next.js
2. Third-party packages
3. Internal `@/` imports
4. Relative imports
5. Styles

## Rules
- Use named imports and named exports by default.
- Default exports are allowed only for Next special files such as `page.tsx` and `layout.tsx`.
- Prefer `@/` imports over deep relative paths.
- Remove unused imports before finishing a change.
