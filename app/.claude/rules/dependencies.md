# Dependencies

## Current Core Stack
- `expo`
- `expo-router`
- `react`
- `react-native`
- `expo-image`
- `react-native-reanimated`
- `react-native-safe-area-context`
- `expo-router/unstable-native-tabs`

## Preferred Direction
- Prefer Expo-first packages before generic React Native alternatives.
- Prefer built-in React Native and Expo APIs before adding new libraries.
- Reuse existing packages already in `package.json` where possible.

## Avoid
- Do not add web-only UI libraries to the native app.
- Do not add heavy state libraries unless simple hooks are no longer enough.
- Do not add database, auth, or form libraries based on assumptions from other projects.
- Do not add `.js`-only tooling patterns; this project is TypeScript-first.

## Rules
- Check whether Expo already provides the capability before adding a dependency.
- Keep new dependencies compatible with Expo SDK 56.
- Prefer small, well-maintained libraries with React Native and Expo support.
