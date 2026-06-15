---
paths:
  - "src/app/**/*.ts"
  - "src/app/**/*.tsx"
  - "src/components/**/*.ts"
  - "src/components/**/*.tsx"
---
# Navigation And Platform Rules

## Navigation
- Expo Router route files live in `src/app/`.
- Keep route files focused on screen structure and navigation setup.
- Shared UI and reusable screen sections belong in `src/components/`.

## Platform Handling
- Use `.web.ts` or `.web.tsx` files when web behavior genuinely needs a separate implementation.
- Use `Platform.OS` guards only for small differences that do not justify splitting files.
- Do not import browser-only APIs into shared native files without protection.

## Rules
- Prefer one clear cross-platform implementation when possible.
- When behavior diverges, isolate the divergence instead of scattering platform branches through many files.
