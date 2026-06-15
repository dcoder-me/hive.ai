# Styling Rules

## Current Styling System
- Tailwind CSS v4
- Global CSS variables in `app/globals.css`
- Fonts loaded with `next/font`

## Rules
- Prefer Tailwind utilities for component styling.
- Keep shared tokens and high-level variables in `app/globals.css`.
- Reuse the existing font variables instead of hardcoding fallback-heavy font stacks.
- Preserve the site’s visual direction and avoid generic UI-kit aesthetics.
- Use plain CSS only when Tailwind is not a clean fit, such as for keyframes or global primitives.
