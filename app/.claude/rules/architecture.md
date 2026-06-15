# Architecture

## Folder Structure

```text
src/
├── app/                  # Expo Router routes and layouts
├── components/           # Shared UI and platform-specific components
├── constants/            # Theme tokens and shared constants
├── hooks/                # Shared hooks
└── global.css            # Web-only global styles imported by the theme layer

assets/
└── images/               # App images, branding, icons, tab assets
```

## Placement Rules
- Route files live in `src/app/`.
- Shared UI belongs in `src/components/`.
- Platform-specific implementations use `.web.ts` or `.web.tsx` beside the native file.
- Shared design tokens belong in `src/constants/theme.ts`.
- Keep route files thin. Move reusable presentation into components.
- If logic is shared by multiple screens, promote it into `components/`, `hooks/`, or `constants/`.
