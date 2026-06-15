---
paths:
  - "app/**/page.tsx"
  - "app/**/layout.tsx"
  - "app/**/loading.tsx"
  - "app/**/error.tsx"
---
# Server Component Rules

## Default
- Components in `app/` are server components by default.
- Keep pages and layouts server-rendered unless there is a concrete client-only need.

## Rules
- Use async server components for server-side data loading when data is introduced.
- Do not add `'use client'` to a page or layout unless unavoidable.
- Keep route files thin and move reusable UI into components as the site grows.
- Export `metadata` or `generateMetadata` when page-specific metadata is needed.
