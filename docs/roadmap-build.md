# Hive — Build Roadmap

> **Two tracks:** **A) Mobile App** (Expo / React Native — Android + iOS) and **B) Admin Website** (Next.js — Vercel).
> The mobile app is the product; the website is the companion/console. Build the app track first; the website track follows once there's real data to show.
> Persona shorthand (see [personas.md](personas.md)): **P1 Aarav** = Organizer/power user · **P2 Sneha** = passive Member · **P3 Flat / P4 Family / P5 Trip** = usage contexts.
>
> **How to read this:** each item is a checkbox with a one-line _why_. `[ ]` = open, `[~]` = needs founder's hands (signing, keys, store), `[x]` = done. Don't build ahead of a dependency.
>
> **Locked decisions** (from [personas.md](personas.md) §6 — don't re-litigate): **India-first** · **tracking only, no payment gateway** ("mark as paid" just updates the ledger) · **text only** (no scanner / photo / voice / OCR) · **radical simplicity** (must work for an elder, unaided) · **TypeScript** · **admin website = internal operator console first**.
>
> ⚠️ **Doc cleanup:** the old `docs/roadmap-builder.md` is a misplaced skill file from another project (UnifyLeads) — unrelated to Hive. It should be deleted; this file replaces it.

---

## Guiding build principles

- **Chat-first or it's not Hive.** The message bar is the primary capture path; forms are the fallback, never the front door (serves P2).
- **Must feel like WhatsApp.** Text only. If an elder (Dada) can't do it unaided, it's too complex — cut the feature.
- **AI is a quiet helper, not a gate.** Its guess is editable, never required. A wrong guess must be one tap to fix, never a blocker (P2 trust).
- **The balance must always be trustworthy and instant.** P1 opens Hive to know the truth; if the number is ever wrong or slow, the product is dead.
- **Settling = recording a payment, not moving money.** "Paid Sneha 500" updates the ledger. No payment gateway, no UPI routing, no custody — ever.
- **Free-tier economics.** Stay inside Firebase/Gemini/Vercel free tiers through MVP; design AI calls to be cheap (batch, debounce, cache).
- **Stack: TypeScript.** The in-repo `.claude` rules still say JavaScript (and describe a Next+Prisma+Supabase stack that doesn't match the Expo+Firebase app) — those need a separate cleanup pass before writing code.

---

# TRACK A — Mobile App (Expo · Android + iOS)

### Phase A0 — Foundation & design system

_Why: get the warm, chat-first shell right before features pile on._

- Confirm Expo SDK, router (expo-router); baseline project hygiene in **TypeScript** (lint, format, env).
- Wire up **React Native Reusables (shadcn for RN) + NativeWind v4** as the component layer; export tokens from [design.md](design.md) into the NativeWind/Tailwind theme (`npx @google/design.md export --tailwind`).
- Build the **Hive design system** from [design.md](design.md): honey/amber palette, warm-charcoal dark mode, tabular numerals (Inter `tnum`) + General Sans display via `expo-font`, radii, spacing tokens.
- Core primitives (own the source, SOLID per [design.md](design.md) appendix): Button, BottomSheet, Card, Avatar, **AmountText** (every amount routes through it — tabular, sign + color + label), BalancePill, ChatBubble, InputBar.
- Motion baseline (Reanimated): spring config, the "message → expense card" morph, the "settle / all-square" celebration.
- \[~\] Firebase project + config (founder: create project, add iOS/Android apps, drop in config).

### Phase A1 — Auth & onboarding _(MVP Phase 1)_

_Why: P1 must get from install → group created → 4 people invited in under 2 minutes._

- Firebase Auth — **Google Sign-In** (primary; one tap — no OTP to type, serves the elder/simplicity thesis). `@react-native-google-signin/google-signin` + Firebase credential.
- First-run onboarding that explains Hive in one warm screen ("just chat — Hive does the math").
- Create workspace/group; pick context (Flat / Family / Trip) to set sensible defaults (P3/P4/P5).
- **Invite flow** — shareable link / WhatsApp invite (the 4 Snehas join in one tap, no account friction).
- Member list, roles (organizer vs member), leave/remove.
- \[~\] iOS: add **Sign in with Apple** alongside Google (App Store guideline 4.8 requires it when offering third-party login); Apple Developer account + capability.

### Phase A2 — Realtime group chat _(MVP Phase 2)_

_Why: this is the home screen and the source of truth; it must feel like WhatsApp (P2)._

- Firestore-backed realtime message stream (listeners), optimistic send, delivery states.
- Chat UI: comfortable bubbles, day separators, infinite history, typing affordances.
- System messages for "X joined", "marked paid", "settled" (text only — no images).
- Offline queue + retry (capture happens in restaurants/trips with bad signal — P5).
- Empty state that invites the first message warmly.

### Phase A3 — AI expense extraction _(MVP Phase 3)_

_Why: the core magic — turn "grocery 800, jio 239" into structured expenses._

- Cloud Function on message create → **Gemini** structured-output call (amount, item, category, payer, split).
- Prompt + schema design; handle multi-expense messages, shorthand, mixed languages (Hinglish), currency.
- Cost controls: debounce/batch, skip obvious non-expense chatter, cache, cap per-group calls.
- **Message → expense card morph**: show Hive "understood" you (reassures P2 the typing worked).
- One-tap **edit/confirm** of the AI guess (payer, split, category) — optional, never required.
- Graceful failure: if AI is unsure, ask one inline clarifying question, never silently drop money.

### Phase A4 — Ledger, balances & summaries _(MVP Phase 4)_

_Why: P1's whole reason to open the app — the trustworthy big picture._

- Expense ledger view (list + filters + search) — fixes the Tricount "no big-picture view" complaint.
- **Balance engine**: who-owes-whom, net positions, debt simplification ("settle in fewest transfers").
- Always-glanceable **balance bar** ("You owe ₹X / You're owed ₹Y").
- Recurring expenses (rent, bills) for P3 Flat; categories tuned per context.
- Monthly summary ("where the month went") — calm for P4, useful for P1.
- Per-trip summary + archive for P5.

### Phase A5 — Settlement = "mark as paid" (the signature moment)

_Why: closing the loop is the chore everyone hates; make it one line of text. **Tracking only — Hive never moves money.**_

- **Record-a-payment via chat:** "paid Sneha 500" → AI logs a payment, updates balances. Same text-first path as expenses.
- Manual fallback: a simple "mark as paid" action (pick person + amount) for anyone who'd rather tap than type.
- System message + the **"all square" celebration** (motion + haptic) when a balance hits zero.
- Settlement/payment history; gentle "you still owe ₹X" reminder that informs without nagging (P2/P4/Dada tone).
- Explicitly **no payment gateway / UPI / wallet** — Hive records what users say they paid, nothing more.

### Phase A6 — Push notifications _(MVP Phase 5)_

_Why: bring passive members back at the right moments — new expense, you owe, settle reminder._

- FCM integration; token management; per-event notification types.
- Notification preferences (no-nag defaults; respect P4's dignity).
- \[~\] iOS: APNs key + push entitlement; Android: FCM setup (founder hands).

### Phase A7 — Polish & store readiness

- Full empty/loading/error states everywhere; accessibility (money color + sign + label, tap targets).
- Dark mode parity (warm charcoal).
- Performance pass (list virtualization, AI-call cost audit, cold-start).
- \[~\] **Android:** signing key, Play Console listing, screenshots, privacy policy, internal testing track.
- \[~\] **iOS:** certificates/provisioning, App Store Connect listing, TestFlight, App Privacy questionnaire.
- \[~\] EAS Build / submit pipeline for both platforms.

### App — Future (post-MVP)

_Kept deliberately small — features must survive the "can Dada use it?" test before they ship._

- Budget tracking · smarter settlement suggestions (fewest transfers) · CSV/PDF export · multi-workspace · multi-currency (P5 international trips) · advanced analytics.
- **Out of scope by design:** receipt OCR / scanner, photo capture, voice entry, payment gateway / UPI / wallet. (Revisit only if the simplicity-first thesis changes.)

---

# TRACK B — Admin Website (Next.js · Vercel)

> **Decided:** the website is an **internal operator console first** (founder tooling). A user-facing web companion comes later, only if P1s ask for a desktop view. Both share auth + the same Firestore data layer. This is _not_ an end-user surface at launch — it's how the founder runs Hive.

### Phase B0 — Foundation

- Next.js (App Router) + Vercel; shared design tokens with the app (honey palette, type, money formatting) for one brand.
- Firebase Admin SDK / auth bridge; role-gating (operator vs end-user).
- Shared money/format/balance utilities (single source of truth with the app where possible).

### Phase B-OPS — Internal operator console _(first — decided)_

_Why: the moment real groups exist, the founder needs to see health, AI quality, and cost._

- Auth + admin-only access (operator allowlist).
- **Overview dashboard**: active groups, members, expenses/day, settle volume, retention.
- **Users & groups** browser: inspect a workspace, members, ledger (read-only, privacy-respecting).
- **AI health**: extraction accuracy spot-checks, failure/clarification rate, **Gemini cost/usage** (stay in free tier).
- **Support tools**: find a user, view their groups, resolve "my balance is wrong" tickets.
- Basic moderation / abuse handling; audit log of admin actions.

### Phase B-USER — User-facing web companion _(after P1 demand)_

_Why: P1 Aarav, the power user, wants the big picture and export on a real screen._

- Email/phone auth shared with app; land on the user's groups.
- **Ledger + balances on desktop** — sortable, filterable, the "big-picture view" Tricount users beg for.
- **Reports**: monthly/trip summaries, charts, category breakdowns.
- **Export**: CSV / PDF (a recurring competitor gap).
- Manage group: members, recurring expenses, settle history.
- (Optional) Marketing landing page + invite-link resolver lives here too.

### Website — Future

- Real-time sync parity with app · multi-workspace management · advanced analytics for power users · webhook/API for export integrations.

---

## Build order (recommended sequence)

1.  **A0 → A4** — get the chat-first capture + trustworthy ledger working end-to-end (this is the demoable core).
2.  **A5 (mark-as-paid)** — close the loop before notifications.
3.  **B-OPS-lite** — minimal ops dashboard the moment you onboard real test groups.
4.  **A6 (push) → A7 (store)** — bring users back, then ship.
5.  **B-USER** — once P1s ask for desktop/export.

## Cross-cutting (every phase)

- Privacy & security: members see only their groups; least-privilege Firestore rules; never expose another group's data.
- Cost discipline: audit Gemini/Firestore reads each phase; stay free-tier through MVP.
- One brand: app and website share palette, type, and money formatting from [personas.md](personas.md) §5.
- Founder-hands items (`[~]`) are listed per phase — batch them so signing/keys/store work isn't a surprise at the end.
