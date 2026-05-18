# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

@AGENTS.md

## Commands

```bash
npx expo start          # Start dev server (scan QR with Expo Go)
npx expo start --android
npx expo start --ios
npx expo start --web
npx expo lint           # ESLint via eslint-config-expo
```

No test runner is configured yet.

## Stack

- **Expo SDK 55** / **React Native 0.83.6** / **React 19**
- Entry: `index.js` → `App.js` → `src/components/Main.jsx`
- Styling: React Native `StyleSheet` (no external UI library)
- Linting: `eslint-config-expo` (flat config, ESLint 9)

## Architecture

The app is in early development. Current structure:

- `Main` — top-level layout; applies `Constants.statusBarHeight` margin and wraps `RepositoryList`
- `RepositoryList` — `FlatList` rendering hardcoded repository data with a separator component
- `RepositoryItem` — renders a single repository's fields as `Text` nodes

Data is currently static (hardcoded array in `RepositoryList`). The expected next steps are connecting to a GraphQL API and introducing navigation (Expo Router or React Navigation).
