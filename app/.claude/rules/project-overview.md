# Project Overview

## About
Hive app is the primary product surface for Hive: a chat-first shared-finance experience for small groups such as families, roommates, students, and trips. The current codebase is still close to the starter app, with custom theme tokens, animated branding, and native tab navigation already in place.

## Tech Stack
- Expo SDK 56
- Expo Router
- React 19
- React Native 0.85
- TypeScript with `strict: true`
- `expo-image`
- `react-native-reanimated`

## Key Domain Notes
- `src/app/_layout.tsx` owns the root router setup.
- `src/components/app-tabs.tsx` defines the tab navigation.
- `src/components/animated-icon.tsx` contains the animated brand treatment.
- Product docs describe a future Firebase and AI-backed system, but those backend pieces are not implemented in this repo yet.

## Critical Rules
- TypeScript only.
- Functional components only.
- Named exports by default.
- No prop drilling through components that do not consume the prop.
