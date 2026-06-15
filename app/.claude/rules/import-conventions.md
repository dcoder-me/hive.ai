# Import Conventions

## Path Aliases
- Use `@/*` for `src/*`.
- Use `@/assets/*` for `assets/*`.

## Import Order
1. React and React Native
2. Expo libraries
3. Third-party packages
4. Internal `@/` imports
5. Relative imports

## Rules
- Named exports only unless the framework requires a default export for a route or layout file.
- Prefer `@/` imports over long relative climbs.
- Keep imports grouped and remove unused imports.
- Do not import web-only modules into native files unless guarded by a platform-specific file.
