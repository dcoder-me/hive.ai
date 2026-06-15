# Hive App

Expo Router app for Hive, a chat-first shared-finance product for small groups. This is the primary product surface.

## What Matters
- Keep the experience chat-first, simple, and mobile-native.
- Prefer Expo and React Native patterns over web or Next.js patterns.
- Use TypeScript only.
- Keep cross-platform behavior aligned and isolate web-specific behavior with `.web.ts` or `.web.tsx` files when needed.
- Reuse tokens from `src/constants/theme.ts` instead of inventing new styling values.

## Stack
- Expo SDK 56
- Expo Router
- React 19
- React Native 0.85
- TypeScript with `strict: true`
- `expo-image`
- `react-native-reanimated`
- `expo-router/unstable-native-tabs`

## Commands
- `npm run start` — start Expo dev server
- `npm run ios` — open iOS simulator flow
- `npm run android` — open Android emulator flow
- `npm run web` — run the app in the browser
- `npm run lint` — run Expo linting

## Verification
Run after changes:
1. `npm run lint`
2. `npm run web` for routing or UI changes when a browser check is useful

## Architecture
- `src/app/` — Expo Router file-based routes and layouts
- `src/components/` — shared UI and platform-specific component implementations
- `src/components/*.web.tsx` — web-only variants
- `src/hooks/` — reusable hooks such as theme/color-scheme helpers
- `src/constants/` — design tokens and shared constants
- `src/global.css` — global web styles imported by theme setup
- `assets/` — app images, icons, and tab assets

## Reference Files
- Claude path-scoped rules live in `.claude/rules/`
- App-specific rules currently live in:
  - `.claude/rules/architecture.md`
  - `.claude/rules/dependencies.md`
  - `.claude/rules/environment-setup.md`
  - `.claude/rules/hooks.md`
  - `.claude/rules/import-conventions.md`
  - `.claude/rules/navigation-platform.md`
  - `.claude/rules/project-overview.md`
  - `.claude/rules/react-components.md`
  - `.claude/rules/state-management.md`
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
- The app is still close to the Expo starter.
- Navigation is defined in `src/app/`.
- Shared UI lives in `src/components/`.
- Root navigation lives in `src/app/_layout.tsx`.
- The main tabs are rendered from `src/components/app-tabs.tsx`.
- The home screen is `src/app/index.tsx`.
- Animated branding lives in `src/components/animated-icon.tsx`.
- Product docs describe a future Firebase and AI-backed system, but those backend pieces are not implemented in this repo yet.
- There is no local backend, database, schema, or validation layer in this project yet.

## Key Conventions
- TypeScript only. Never add `.js` or `.jsx` files.
- Functional React only. No classes or OOP patterns.
- Named exports everywhere except framework-required route/layout exports inside `src/app/`.
- Use `async/await` instead of `.then()`.
- Files and folders stay kebab-case.
- Exported functions should include JSDoc with `@param` and `@returns`.
- Use the `@/*` and `@/assets/*` path aliases from `tsconfig.json`.
- Prefer `expo-image` for image rendering.
- Keep cross-platform behavior aligned. If web needs a different implementation, use `.web.ts` or `.web.tsx`.
- Reuse theme tokens from `src/constants/theme.ts` instead of scattering magic numbers and colors.
- Treat planning docs as product direction, not proof that Firebase, AI parsing, or other future systems already exist in this repo.
- Follow the no-prop-drilling rule strictly. Components should read shared state from hooks/context/store directly when they are the consumer.

## Avoid
- Do not introduce Next.js concepts such as server components, server actions, or route handlers.
- Do not assume Firebase, Gemini, NativeWind, or another future stack is already wired just because it appears in planning docs.
- Do not add Pages Router style patterns or web-only app structure.
- Do not introduce browser APIs without platform guards.
- Do not bypass platform-specific files when web/native behavior diverges.
- Do not switch styling to a different system unless the project is intentionally being migrated.
- Do not thread state or callbacks through intermediate components that do not use them.
