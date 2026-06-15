# Hive

**Tagline:** Chat. Track. Settle.

## Vision

Hive is a chat-first shared finance application for small groups (3–5 members), including families, students, roommates, and travel groups.

Instead of manually maintaining Airtable, Excel, or WhatsApp records, users simply chat in a group and Hive automatically converts messages into structured financial records.

---

# Problem

Current workflow:

- WhatsApp messages
- Airtable tracking
- Manual calculations
- Manual categorization
- Monthly reconciliation

Pain points:

- Expenses get lost
- Duplicate entries
- Manual effort
- No realtime visibility
- Difficult balance tracking

---

# Solution

Users send normal messages:

```
grocery
fish
rent
jio

```

Hive automatically:

1.  Stores the message
2.  Uses AI to understand intent
3.  Creates structured expense records
4.  Updates balances
5.  Updates reports
6.  Sends summaries

---

# Target Users

Primary:

- Families
- Students
- Roommates
- Travel groups

Typical workspace size:

- 3–5 members

---

# Core Principle

Chat is the source of truth.

Everything starts from a message.

Messages generate:

- Expenses
- Balances
- Reports
- Notifications

---

# Tech Stack

## Mobile App

- Expo
- React Native

## Backend

- Firebase

## Authentication

- Firebase Auth

## Database

- Firestore

## Realtime

- Firestore Realtime Listeners

## AI

- Gemini API

## Push Notifications

- Firebase Cloud Messaging (FCM)

## Dashboard

- Next.js

## Hosting

- Vercel

---

# Architecture

```
Expo App
    ↓
Firebase Auth
    ↓
Firestore
    ↓
Cloud Function
    ↓
Gemini AI
    ↓
Structured Output
    ↓
Expense Records
    ↓
Realtime Updates

```

---

# Core Collections

users

workspaces

groups

members

messages

expenses

balances

notifications

monthly_summaries

---

# MVP Features

## Phase 1

- Authentication
- Workspace creation
- Member invitation

## Phase 2

- Realtime group chat
- Message history

## Phase 3

- AI expense extraction
- Expense ledger

## Phase 4

- Balance calculation
- Monthly summaries

## Phase 5

- Push notifications
- Dashboard

---

# Future Features

- Receipt OCR
- Voice expense entry
- Budget tracking
- Settlement suggestions
- CSV export
- PDF reports
- Multi-workspace support
- Advanced analytics

---

# Development Approach

AI builds:

- Screens
- Database models
- Cloud functions
- API integrations
- Dashboard
- Reports

Manual work:

- Firebase setup
- Gemini API key
- Android signing
- iOS certificates
- Testing
- Store publishing

---

# Cost

Initial MVP:

- Expo → Free
- Firebase → Free Tier
- Gemini → Free Tier
- Vercel → Free Tier

Expected cost:

₹0/month initially.

---

# Brand Direction

Name: Hive

Meaning:

A small group working together.

Hidden brand concept:

V = 5

Hive is designed primarily for small groups of around five people sharing expenses and responsibilities.

---

# Success Metric

A family or small group should be able to completely replace Airtable, Excel, and manual expense tracking using only Hive chat.
