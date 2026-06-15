# Architecture

## Folder Structure

```text
app/
├── layout.tsx           # Root shell, fonts, metadata
├── page.tsx             # Home page
└── globals.css          # Tailwind import and global variables

public/                  # Static assets
```

## Placement Rules
- Keep route entry files in `app/`.
- Promote reusable UI into new top-level folders only when the site grows enough to need them.
- Treat `app/page.tsx` as composition and page structure, not a dumping ground for all future UI.
- Keep global design tokens in `app/globals.css` until the site needs a more formal design system.
- Favor operator-console simplicity over speculative marketing-site sprawl.
