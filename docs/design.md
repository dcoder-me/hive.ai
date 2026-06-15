---
version: alpha
name: Hive
description: >
  Chat-first shared-finance design system. WhatsApp warmth meets quiet
  financial precision — warm honey palette, tabular money, dead-simple for
  every literacy level. Single source of truth for the Expo app (React Native
  Reusables + NativeWind) and the Next.js operator site (shadcn/ui + Tailwind).
colors:
  primary: "#F2A900"
  on-primary: "#1A1714"
  ink: "#1A1714"
  ink-muted: "#6B635A"
  surface: "#FAF7F2"
  surface-elevated: "#FFFFFF"
  surface-dark: "#16130F"
  surface-dark-elevated: "#211C16"
  border: "#E7E1D8"
  positive: "#1FA971"
  on-positive: "#FFFFFF"
  negative: "#E5533C"
  on-negative: "#FFFFFF"
  bubble-me: "#FCEFC7"
  bubble-other: "#FFFFFF"
typography:
  display:
    fontFamily: General Sans
    fontSize: 2rem
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  h1:
    fontFamily: General Sans
    fontSize: 1.5rem
    fontWeight: 600
    lineHeight: 1.3
  title:
    fontFamily: General Sans
    fontSize: 1.125rem
    fontWeight: 600
    lineHeight: 1.4
  body:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: 400
    lineHeight: 1.5
  body-strong:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: 600
    lineHeight: 1.5
  label:
    fontFamily: Inter
    fontSize: 0.8125rem
    fontWeight: 500
    lineHeight: 1.4
  caption:
    fontFamily: Inter
    fontSize: 0.75rem
    fontWeight: 400
    lineHeight: 1.4
  amount:
    fontFamily: Inter
    fontSize: 1.75rem
    fontWeight: 700
    lineHeight: 1.2
    letterSpacing: "-0.01em"
    fontFeature: "tnum"
  amount-sm:
    fontFamily: Inter
    fontSize: 1rem
    fontWeight: 600
    lineHeight: 1.3
    fontFeature: "tnum"
rounded:
  sm: 8px
  md: 12px
  lg: 16px
  xl: 20px
  pill: 999px
spacing:
  xs: 4px
  sm: 8px
  md: 12px
  lg: 16px
  xl: 24px
  2xl: 32px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    typography: "{typography.body-strong}"
    rounded: "{rounded.lg}"
    padding: 14px
    height: 52px
  button-secondary:
    backgroundColor: "{colors.surface-elevated}"
    textColor: "{colors.ink}"
    typography: "{typography.body-strong}"
    rounded: "{rounded.lg}"
    padding: 14px
    height: 52px
  chat-bubble-me:
    backgroundColor: "{colors.bubble-me}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 12px
  chat-bubble-other:
    backgroundColor: "{colors.bubble-other}"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: 12px
  expense-card:
    backgroundColor: "{colors.surface-elevated}"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
    padding: 16px
  balance-pill:
    backgroundColor: "{colors.surface-elevated}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    padding: 12px
  amount-positive:
    textColor: "{colors.positive}"
    typography: "{typography.amount}"
  amount-negative:
    textColor: "{colors.negative}"
    typography: "{typography.amount}"
  input-bar:
    backgroundColor: "{colors.surface-elevated}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
    height: 48px
    padding: 12px
---

## Overview

Hive should feel like **a warm group chat that quietly does the math** — never like a bank app. The design language pairs the familiarity of a messaging app (so an elder can use it unaided) with the precision money demands (so the balance is always trustworthy at a glance).

Two words govern every decision: **warm** and **precise**. Warmth comes from honey tones, soft shapes, plain language, and a chat-native layout. Precision comes from tabular numerals, unambiguous money colors, and a single trustworthy balance. When warmth and precision conflict, warmth wins for chrome and tone; precision wins for anything showing an amount.

This file is the source of truth for both surfaces: the **Expo app** (React Native Reusables + NativeWind) and the **Next.js operator site** (shadcn/ui + Tailwind). Both consume these tokens so the brand reads as one. See the Implementation appendix for how tokens flow into code.

## Colors

The category defaults to cold corporate blue. Hive deliberately goes **warm honey/amber** to feel like a home, not a bank.

- **Primary `#F2A900` (Honey):** the hero. Primary actions, the logo comb, the "all square" moment. Amber is light, so text/icons on it use **on-primary `#1A1714`**, never white.
- **Ink `#1A1714`:** warm near-black for text — never pure `#000`, which reads cold.
- **Ink-muted `#6B635A`:** captions, metadata, timestamps.
- **Surface `#FAF7F2` (Cream):** the app background — softer than white. **Surface-elevated `#FFFFFF`** for cards and the input bar.
- **Dark mode** uses warm charcoal (**surface-dark `#16130F`**, **surface-dark-elevated `#211C16`**) — never pure black.
- **Money is semantic and sacred:**
  - **Positive `#1FA971`** — owed to you / settled.
  - **Negative `#E5533C`** — you owe. A warm coral, *not* an alarming red (we never shame the user about money).
- **Accessibility rule (non-negotiable):** money direction must be legible without color — always pair the color with a **sign (`+`/`−`) and a label** ("you owe" / "owed to you"). Never communicate balance by color alone. All text/background pairs must meet WCAG AA.

## Typography

**Money is the hero glyph.** Everything else supports it.

- **Amounts** use **Inter with tabular figures (`tnum`)** so columns of money align and never jitter as digits change. Amounts are large and confident (`amount` / `amount-sm` tokens).
- **Display & headings** use **General Sans** — a friendly-but-precise geometric sans (rounded enough for warmth, sharp enough for trust). Both General Sans and Inter are free and load via `expo-font`.
- **Body & chat** use **Inter** at a comfortable, WhatsApp-like reading size.
- **Respect OS font scaling.** Layouts must survive a user cranking system text size up (elder persona). Never lock font sizes against `allowFontScaling`.
- Hierarchy: `amount` (XL, tabular) > `title` > `body` > `label` > `caption` (muted).

## Layout

- **Chat is the home screen.** The message bar is the primary capture path; there is no "+ Add Expense" form as the front door.
- **Thumb-first.** Primary actions live in the lower third; secondary actions live in bottom sheets within reach. Top bars are for context, not for must-tap controls.
- **One column, generous spacing.** Use the `spacing` scale (`xs`–`2xl`); never hardcode gaps. Comfortable line length for chat; cards are full-width with `lg` insets.
- **An always-visible balance bar** sits above the input or just under the header — the one number P1 opens Hive for. It must be readable in under a second.
- **Touch targets ≥ 48×48 px** everywhere (elder persona).

## Elevation & Depth

Hive is **mostly flat and calm**. Depth is used sparingly to separate the few things that matter.

- **Level 0** — the cream surface (chat background).
- **Level 1** — cards, the input bar, the balance pill: a *warm, soft* shadow (low opacity, brown-tinted, never harsh black) or a 1px `border` in light mode.
- **Level 2** — bottom sheets and the active "all square" celebration: a slightly stronger lift.
- Dark mode conveys elevation with **lighter warm surfaces** (`surface-dark-elevated`), not shadows.
- No glassmorphism, no neumorphism, no heavy drop shadows — they read as "trying too hard" and hurt legibility for the elder persona.

## Shapes

- **Soft, friendly radii.** Buttons and cards use `lg` (16px); the input bar, balance pill, and avatars use `pill`. Nothing sharp-cornered — sharpness reads as corporate/cold.
- **The honeycomb is the brand geometry.** Use hex motifs sparingly as texture, empty-state art, or the logo — never as functional containers (a hexagonal button is cute but bad for tap accuracy and the elder persona).
- **V = 5** can surface as a quiet five-cell comb in brand moments, never as required UI.

## Components

Built on **React Native Reusables** (shadcn/ui for RN) in the app and **shadcn/ui** on the site. Core set:

- **Button** — `button-primary` (honey, the single most prominent action per screen) and `button-secondary` (quiet, outlined/elevated). One primary per screen.
- **ChatBubble** — `chat-bubble-me` (honey tint) vs `chat-bubble-other` (white). The home of the product.
- **ExpenseCard** — grows from a chat message; shows item, amount, who paid, the split. Tap to fix the AI's guess (optional, never required).
- **AmountText** — the most important component. Renders a money value with tabular figures, sign, semantic color, and a label. *No raw amount is ever rendered without going through it.*
- **BalancePill / BalanceBar** — the glanceable "You owe ₹X · You're owed ₹Y".
- **InputBar** — pill-shaped text input + send. Text only (no camera, no mic, no attachment).
- **BottomSheet** — secondary actions (mark as paid, edit split, member options).
- **EmptyState** — every list has one; warm, inviting, honeycomb art.

## Do's and Don'ts

**Do**
- Route every amount through `AmountText` (sign + color + label + tabular figures).
- Keep one primary (honey) action per screen.
- Default to chat; make typing the fastest path to everything.
- Write plain words ("who owes what", "mark as paid") — never "ledger", "reconcile", "settlement algorithm".
- Honor OS font scaling and 48px touch targets.
- Use tokens (`{colors.*}`, `{spacing.*}`) — never hardcode hex or px.

**Don't**
- Don't use cold blue, pure black, or alarming red.
- Don't communicate balance by color alone.
- Don't put a finance-app form between the user and capturing an expense.
- Don't add scanner/photo/voice affordances — text only, by design.
- Don't imply Hive moves money — it *records* what users say they paid; there is no payment UI.
- Don't ship a screen an elder couldn't navigate unaided.

---

## Implementation appendix (Hive-specific — beyond the Google format)

> The eight sections above are the portable DESIGN.md spec (lintable/exportable via the `@google/design.md` CLI). This appendix is Hive's engineering contract for turning those tokens into code.

### Component library — decision

- **App (Expo):** **React Native Reusables (RNR)** — shadcn/ui for React Native, on **NativeWind v4**. *Recommended and chosen.*
- **Site (Next.js):** **shadcn/ui** + Tailwind.

**Why RNR over the alternatives**
- It *is* shadcn — **copy-paste, you own the component source.** That ownership is what makes SOLID achievable (you refactor the primitive instead of fighting a vendor API).
- **One mental model across app and web** — both are shadcn + Tailwind tokens, so this DESIGN.md maps cleanly to both via `tailwind.config` / NativeWind theme.
- **Lean and Expo-native** — built on RN primitives + NativeWind, works with Expo's new architecture; no heavy compiler step.
- Runner-up: **Gluestack UI v2** (great, but you depend on their lib). **Tamagui** is the most performant universal kit but has a steep learning curve and is overkill for a text-first chat app.

**Token flow:** DESIGN.md front-matter → `npx @google/design.md export --tailwind` → Tailwind/NativeWind theme → RNR & shadcn components read CSS-variable tokens. Tokens live in *one* place; both apps inherit them.

### SOLID for components

Owning the source (shadcn/RNR) is precisely what lets us hold these. Applied to RN/React:

- **S — Single Responsibility:** one component, one job. Split presentational from container; e.g. `AmountText` only *formats* money, it never *fetches* a balance. Keep components under ~150 lines (per the repo react-component rules).
- **O — Open/Closed:** extend via **variant props (`cva`) and composition**, never by editing a primitive in place or copy-forking it. New look = new variant, not a new component.
- **L — Liskov Substitution:** every variant honors the same prop contract — any `<Button variant=…>` is droppable wherever a Button is expected without breaking layout or behavior.
- **I — Interface Segregation:** small, focused prop types. Don't force a component to accept props it ignores; split a fat prop bag (e.g. separate `ExpenseCardView` data props from `onEdit` event props).
- **D — Dependency Inversion:** components depend on **abstractions — design tokens and hooks — not concrete values or deep prop chains.** Leaf components that need shared state call the hook directly (`useBalance()`, `useGroup()`) rather than receiving it drilled through parents. This is the same **no-prop-drilling** rule the project already enforces, expressed as DIP.

### Stack notes
- **TypeScript** throughout (app + site).
- Fonts via `expo-font`: General Sans (display) + Inter (body/amounts, `tnum` enabled).
- Auth: **Google Sign-In** (one tap — also serves the simplicity/elder thesis: no OTP to type).
