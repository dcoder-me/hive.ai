<!-- BEGIN:nextjs-agent-rules -->
# This is NOT the Next.js you know

This version has breaking changes. Read the relevant guide in `node_modules/next/dist/docs/` before writing code, and respect deprecations.
<!-- END:nextjs-agent-rules -->

# Hive Site

Next.js App Router project for Hive. Based on the product docs, this should be treated as an internal operator/admin surface first, with broader marketing or user-facing website work coming later.

## What Matters
- Keep the site lean and intentional.
- Use TypeScript only.
- Use App Router patterns only.
- Prefer server components by default and add client components only where interactivity is truly needed.
- Keep styling aligned with `app/globals.css` and the existing font setup.

## Stack
- Next.js 16 App Router
- React 19
- TypeScript with `strict: true`
- Tailwind CSS v4
- ESLint 9 with `eslint-config-next`
- `next/font` and `next/image`

## Commands
- `npm run dev` — start the local Next dev server
- `npm run build` — create a production build
- `npm run start` — run the production server
- `npm run lint` — run ESLint

## Verification
Run after changes:
1. `npm run lint`
2. `npm run build`

## Architecture
- `app/` — App Router pages, layout, metadata, and global styling
- `app/layout.tsx` — root HTML shell and font setup
- `app/page.tsx` — current home page entry
- `app/globals.css` — Tailwind import and global CSS variables
- `public/` — static assets
- `next.config.ts`, `tsconfig.json`, `eslint.config.mjs` — project configuration

## Reference Files
- Claude path-scoped rules live in `.claude/rules/`
- Site-specific rules currently live in:
  - `.claude/rules/architecture.md`
  - `.claude/rules/client-components.md`
  - `.claude/rules/dependencies.md`
  - `.claude/rules/environment-setup.md`
  - `.claude/rules/hooks.md`
  - `.claude/rules/import-conventions.md`
  - `.claude/rules/project-overview.md`
  - `.claude/rules/react-components.md`
  - `.claude/rules/server-components.md`
  - `.claude/rules/styling.md`
- Product and design context shared across the repo lives in:
  - `../docs/project-overview.md`
  - `../docs/design.md`
  - `../docs/personas.md`
  - `../docs/roadmap-build.md`

## Instruction Priority
- Strictly follow the relevant instructions in this `CLAUDE.md`, the matching files in `.claude/rules/`, and the shared product docs in `../docs/`.
- Treat `.claude/rules/` as the source of truth for path-specific guidance.
- Treat the shared docs as product-direction guidance that must shape decisions, language, UX, and architecture choices.
- If code and docs disagree, prefer the current implemented code for factual repo state, but do not ignore documented product constraints.

## Current Reality
- The codebase is still a minimal starter.
- Primary files are `app/layout.tsx`, `app/page.tsx`, and `app/globals.css`.
- Product docs point toward an operator-first website, so avoid inventing a larger product-web architecture that is not in the repo yet.
- There is no current API layer, schema layer, state library, or database integration in this project.

## Key Conventions
- TypeScript only. Never generate `.js` or `.jsx`.
- Functional React only. No classes or OOP patterns.
- Named exports by default. `page.tsx` and `layout.tsx` may use framework-required default exports.
- Use server components by default. Add `'use client'` only when interactivity or browser APIs require it.
- Use `async/await` for async code.
- Keep files and folders in kebab-case.
- Exported functions should include JSDoc with `@param` and `@returns`.
- Use the `@/*` alias from `tsconfig.json` for root imports.
- Prefer `next/image` for images and `next/font` for fonts.
- Keep Tailwind usage aligned with the tokens and variables defined in `app/globals.css`.
- Follow the no-prop-drilling rule strictly. Shared state should be read where it is consumed.

## Avoid
- Do not assume Prisma, Supabase, or a larger SaaS app architecture exists here yet.
- Do not add Pages Router patterns.
- Do not use Pages Router APIs like `getServerSideProps` or `getStaticProps`.
- Do not add client components unless they are actually needed.
- Do not turn whole pages into client components just because one child needs interactivity.
- Do not introduce default exports outside Next special files.
- Do not hardcode styles that should live in shared CSS variables or layout structure.
- Do not thread callbacks or shared state through components that do not directly use them.
