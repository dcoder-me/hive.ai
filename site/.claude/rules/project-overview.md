# Project Overview

## About
Hive site is a Next.js App Router project for Hive’s website surface. Based on the product docs, it should be treated as an internal operator/admin console first, with broader public-site concerns coming later. The current codebase is still a minimal starter, so changes should establish clean patterns without assuming a larger app architecture that does not exist yet.

## Tech Stack
- Next.js 16
- React 19
- TypeScript with `strict: true`
- Tailwind CSS v4
- `next/font`
- `next/image`

## Key Domain Notes
- `app/layout.tsx` owns the root HTML shell and font variables.
- `app/page.tsx` is the current homepage entry.
- `app/globals.css` defines the base CSS variables and Tailwind import.

## Critical Rules
- TypeScript only.
- Functional React only.
- Named exports by default.
- Server components by default.
