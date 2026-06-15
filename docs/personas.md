# Hive — Personas, Brand & Design DNA

> **Chat. Track. Settle.**
> This document defines _who_ Hive is for, _what kind of brand_ it is, and the _design language_ that flows from both. Every UI decision — color, type, motion, microcopy, button shape — should trace back to a persona and a brand value defined here. When in doubt, ask: "Which persona does this serve, and does it sound like Hive?"
>
> **Locked product decisions** (drive everything below):
>
> 1.  **India-first.** ₹ default, **Google Sign-In** (one tap), Hinglish-friendly AI.
> 2.  **Tracking only — no payment gateway.** Saying "paid Sneha 500" just updates the ledger. Hive never holds, moves, or routes money.
> 3.  **Text only.** No scanner, no photos, no receipts, no voice — you type, like an SMS.
> 4.  **Radical simplicity.** Must be usable by a CS student _and_ their grandfather. If it's harder than WhatsApp, it has failed.
> 5.  **Admin website = internal operator console first** (founder tooling), user-facing web later.

---

## 1\. Positioning — what Hive actually is

Hive is a **standalone group chat that is also a shared ledger**. You chat normally; AI quietly turns plain-text messages into expenses, balances, and a running who-owes-whom. Built for **small, trusting groups of ~3–5 people** (the hidden brand idea: **V = 5**).

### The wedge — why Hive, not the others

The market splits into two camps, and both leave a gap:

- **Form-first splitters** (Splitwise, Tricount, Settle Up) — users hate the dated UI, transaction caps, paywalls, ads, "fill a form for every coffee", and the lack of a big-picture view.
- **WhatsApp AI bots** (Moneko, Centimo, Dora, HisabAI, ChatExpense) — they live inside someone else's app, feel like a bot you're "talking at", and have no shared space that _belongs_ to the group.

**Hive's gap to own:** the _only_ app where the group's own chat **is** the source of truth — a warm, private space that belongs to the five of you, where tracking is a byproduct of talking. Capture is **text only** (type it, like an SMS). Settling is just **telling Hive you paid** ("paid Sneha 500"), which updates the ledger — no payment gateway, no forms, no receipts. Not a bot in WhatsApp. A home.

**The deepest wedge — radical simplicity.** Hive targets the _entire_ tech-literacy spectrum: a CS student _and_ their grandfather. Every other app assumes the user will learn it; Hive assumes they won't, and shouldn't have to. If it isn't exactly as easy as sending a WhatsApp message, it has failed.

### One-line positioning

> _"A group chat that does the math. Hive turns the way your house already talks about money into a clean, settled ledger — automatically."_

---

## 2\. Who we target

### Primary segment

**Indian small groups, all ages, across the tech-literacy spectrum** — students in shared flats, and households where parents and grandparents are members too. They already coordinate money over WhatsApp and tolerate (or quietly hate) Splitwise. ₹- and SMS-native; allergic to spreadsheets and to "finance app" coldness.

### The personas

Hive's magic is that **one person sets it up and everyone else barely has to learn anything**. So we design for a _spectrum of effort and literacy_, not one ideal user. Two personas drive the product (the Organizer and the Member); three are usage-contexts the same people move between (Flat, Family, Trip).

#### 🐝 P1 — Aarav, "The Organizer" _(primary — power user)_

- **24, student / early-career, shares a flat with two others.** Created the group; everyone pays him back; currently maintains a guilt-inducing Splitwise or a Google Sheet.
- **Goal:** Stop being the group's unpaid accountant. Truth without effort — "I shouldn't have to chase people or do math at month-end."
- **Frustrations:** Splitwise's caps and upsells; people forget to log; reconciliation is a monthly chore.
- **What wins him:** Zero-friction text capture (type "rent 30k"), a balance he trusts at a glance, and an easy "mark settled" so chasing ends.
- **Designs for him:** speed, keyboard-first capture, an always-visible who-owes-whom truth, big-picture/export views.
- _Hive lives or dies on Aarav loving it enough to drag everyone else in._

#### 🐝 P2 — Sneha, "The Member" _(primary — passive majority)_

- **The flatmate / sibling / friend who was added.** Will **never** open a "finance app" on her own. Engages only inside chat. May be tech-shy (this persona also stands in for the less-techy member of any group).
- **Goal:** Know what she owes, pay it, move on. Zero learning curve.
- **Frustrations:** Apps that demand she categorize, confirm, and maintain things. Feeling surveilled. Math homework.
- **What wins her:** It feels exactly like WhatsApp. She types "I paid for dinner 1200" and it just works. A gentle line tells her she owes ₹400.
- **Designs for her:** chat-native everything, near-zero required taps, large readable text, warm non-judgmental tone, inform-don't-nag notifications.
- _The Snehas are why Hive must be chat-first and forgiving. If it ever feels like "doing accounting," they churn and the group dies._

#### 👴 P2b — Dada, "The Elder" _(primary constraint — sets the simplicity floor)_

- **A parent or grandparent in a family group.** Comfortable with WhatsApp and little else. Big fonts, voice-reading, doesn't trust anything that looks like "a banking app."
- **Goal:** Add what he spent and see what's owed, without help.
- **What wins him:** It looks and types like WhatsApp. Nothing to set up. No jargon. Plain, large, obvious.
- **Designs for him:** the **accessibility and clarity floor** for the whole product — large tap targets, high contrast, no hidden gestures, no feature he has to discover. If Dada can't do it unaided, it's too complex.
- _Dada is the reason the locked decisions (text-only, tracking-only, no scanner) exist. He is the simplicity conscience of the product._

#### 🏠 P3 — The Flat _(context: roommates / steady-state)_

- 3–5 flatmates, recurring rent + bills + groceries, indefinite timeline. Money flows both directions every month.
- **Needs:** recurring expenses, monthly summaries, running balances, a "settle up at month-end" rhythm.
- **Tone:** calm, ongoing, low-drama. The ledger should feel like a tidy shared kitchen, not a bank statement.

#### 👨‍👩‍👧 P4 — The Family _(context: household, includes P2b)_

- Parents + adult kids + grandparents. Groceries, school, utilities, one or two "treasurers." Trust is high; privacy from _outsiders_ matters more than from each other.
- **Needs:** dead-simple capture, a sense of "where did the month go," dignified tone (no sass about Dad's spending), large readable UI.
- **Tone:** warm, respectful, soft. This persona — with Dada — pulls the brand _away_ from anything too gen-Z-flippant.

#### ✈️ P5 — The Trip _(context: episodic, high-intensity)_

- 4–6 friends on a short trip. Burst of activity, then settle and (mostly) disband.
- **Needs:** fast one-handed text capture in chaotic moments, a clear end-of-trip "here's who owes what," then archive.
- **Tone:** fun, fast, a little celebratory at settle-time. This persona licenses the brand's lighter, delightful side.

> **The brand tension to hold:** P4 Family + Dada keep Hive **trustworthy, dignified, and dead-simple**; P5 Trip keeps it **warm and delightful**. Hive lives in the middle — _friendly precision_. Never cold like a bank, never flippant like a meme-bot, never complex like accounting software.

---

## 3\. What we are NOT (anti-targets)

Saying no sharpens the brand. Hive is **not**:

- A solo personal-finance / net-worth tracker (that's Cashew, Monarch, MonAi).
- A WhatsApp bot or browser extension — Hive owns its own space.
- A large-org / accounting / SaaS expense tool (no big teams, no approval workflows).
- **A bank, wallet, payment app, or money-mover** — Hive only _tracks_ what people tell it; it never holds or routes funds. No payment gateway, ever (by design).
- A feature-stuffed app — **no scanner, no receipt photos, no voice, no OCR.** Text in, ledger out.
- A gamified, points-and-mascot fintech toy — lightly playful, never gimmicky.

---

## 4\. Brand

### Name & meaning

**Hive** — a small group working together; industrious, warm, collective. Hidden idea: **V = 5**, the ideal group size. The honeycomb is the brand's natural geometry.

### Brand personality (5 traits)

1.  **Warm** — feels like your group, not a bank.
2.  **Effortless** — the work happens invisibly; the user just talks.
3.  **Trustworthy** — money is involved; never sloppy, never sketchy.
4.  **Quietly clever** — the AI is a calm helper, not a show-off chatbot.
5.  **Lightly delightful** — small moments of joy (a clean settle, a satisfying "all square").

### Voice & tone

- **Human, short, confident.** "₹450 — settled. All square." not "Your transaction has been successfully recorded."
- **Warm, never flippant about money.** Charming about the _experience_; respectful about the _amounts_. (Monobank/Cleo warmth — minus the sass that would alienate Family and Dada.)
- **Plain language only.** No "ledger", "reconcile", "settle-up algorithm" in the UI — say "who owes what", "mark as paid". Dada must understand every word.
- **Never:** jargon, guilt-tripping nudges, fake urgency, corporate passive voice.

### Brand metaphors to mine

Honey · honeycomb cells · "all square" · the hive working together · gathering / pooling · the comb filling up as the month progresses.

---

## 5\. Design DNA — how personas become pixels

> The bridge to implementation. These are **proposed defaults** — lock them before building the design system. Everything is justified by a persona.

### 5.1 Color — _warm, not corporate-blue_

The whole category defaults to cold blue. Hive deliberately goes **warm honey/amber** to feel like a home, not a bank. (Research: warm amber reads as optimism + approachability while staying trustworthy.)

- **Primary — Honey/Amber:** a refined gold (≈ `#F2A900`, tune for contrast) — the hero color, for primary actions, settle moments, the logo comb.
- **Ink — Warm near-black:** `#1A1714` (warm charcoal-brown, never pure `#000`) for text. Cozy, not sterile.
- **Surfaces — Cream / off-white:** `#FAF7F2` light; warm charcoal (≈ `#16130F`, _not_ pure black) for dark mode.
- **Semantic money colors (critical):** owed-to-you / positive → warm green (≈ `#1FA971`); you-owe / negative → warm coral (≈ `#E5533C`, _not_ alarming red). Must be readable **at a glance and color-blind-safe** — always pair with sign + label, never color alone (serves P1's "trust the balance instantly" and Dada's readability).
- **Accent geometry:** subtle honeycomb/hex texture — never skeuomorphic clutter.

### 5.2 Typography — _money is the hero, legibility is the law_

- **Numerals matter most.** Use **tabular, slightly geometric** numerals so columns of money align and never jitter. Big, confident amounts.
- **Generous base size + scalable.** Respect OS font-scaling so Dada can crank it up without breaking layout.
- **Display/brand:** a friendly-but-precise geometric sans (_General Sans_, _Satoshi_, or _Hanken Grotesk_) — rounded for warmth, sharp enough for trust.
- **Body:** clean, high-legibility sans; system font on mobile is fine for performance.
- **Hierarchy:** amounts XL + tabular; labels small + muted; chat text at WhatsApp-comfortable size (P2/Dada must feel at home).

### 5.3 Motion — _subtle, reassuring, a small celebration at settle_

- Chat message → gently **becomes** an expense card (shows the AI "understood" you — reassures P2/Dada the typing worked).
- **Settle** is the signature moment: a satisfying honey-fill / "all square" animation + light haptic.
- Everything else: restrained, fast, never blocking, never a gesture Dada has to discover. Spring physics over linear. (Reanimated on app; Framer Motion on web.)

### 5.4 Components & interaction — _WhatsApp-simple, thumb-first_

- **Chat is the home screen.** Capture happens in the message bar. There is **no "+ Add Expense" form as the primary path** — that's the splitter trap P2 hates and Dada can't navigate.
- **It should look like a messaging app**, not a finance app: a familiar chat list, bubbles, a text input with a send button. Familiarity _is_ the onboarding.
- **Expense = a card that grows from a message**, tappable to fix the AI's guess (who paid, the split) — fixing is _optional_, never required.
- **Always-visible balance bar** — a plain "You owe ₹X · You're owed ₹Y", the thing P1 opens Hive for and Dada can read without thinking.
- Large rounded buttons (radius ≈ 16–20), generous tap targets, no hidden gestures. Bottom sheets for secondary actions (thumb reach).
- **Dark mode first-class and warm** (charcoal, not black).

### 5.5 Persona → design mapping (cheat sheet)

- **Chat-first capture, near-zero required taps** → serves **P2 Sneha** (she'll never use a form-based finance app).
- **Looks like WhatsApp, no jargon, large readable UI** → serves **Dada** (familiarity is the onboarding; he's the simplicity floor).
- **Always-visible trusted balance + big-picture/export** → serves **P1 Aarav** (he opens Hive to _know the truth_ and end chasing).
- **"Mark as paid" updates the ledger, no payment gateway** → serves **all** (tracking-only keeps it simple and trustworthy; no money custody).
- **Warm honey palette, dignified plain tone** → serves **P4 Family** (keeps Hive from feeling cold _or_ flippant).
- **Fast one-handed capture, end-of-trip summary** → serves **P5 Trip** (capture in chaos; settle once).
- **Non-judgmental, inform-don't-nag notifications** → serves **P2 + P4** (a surveillance feeling = churn for the passive majority).

---

## 6\. Locked decisions (don't re-litigate)

1.  **Geography & auth:** India-first (₹, Hinglish AI); **Google Sign-In** as the primary login (one tap, no OTP — serves the elder/simplicity thesis).
2.  **Settlement:** tracking only — "mark as paid" records a payment and updates balances. **No payment gateway, no UPI routing, no custody.**
3.  **Scope:** text only — no scanner, no photos, no voice, no OCR. Type it.
4.  **Simplicity floor:** Dada (the elder) must use it unaided. If a feature fails that test, cut it.
5.  **Admin website:** internal operator console first; user-facing web companion later.
6.  **Tone:** friendly precision — warm and plain, never flippant, never corporate.

---

## 7\. Success metric (persona-framed)

> A Flat or Family can **completely retire Splitwise / Excel / the WhatsApp-and-mental-math routine** — the passive members (P2) and the elders (Dada) never feel like they "use a finance app," and the Organizer (P1) never has to chase a payment again.
