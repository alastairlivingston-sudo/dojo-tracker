# Dojo Tracker

A family reward points & swimming badges tracker. Built as a PWA for mobile-first use.

**Live app:** https://alastairlivingston-sudo.github.io/dojo-tracker/ *(if GitHub Pages enabled)*

## Features

- **Dojo points** — tap a child's avatar to award a point; animated celebration per animal
- **Undo** — accidental tap? An undo bar appears for 5 seconds after every point awarded
- **Swimming badges** — track progress across 4 categories (Beginner, Strokes, Distance, Safety)
- **Session history** — save snapshots of scores; view and delete past sessions
- **Real-time sync** — Firebase Realtime Database keeps all devices in sync instantly
- **Offline support** — Service Worker caches the app for use without internet

## Stack

- Vanilla HTML/CSS/JS — single file (`index.html`)
- Firebase Realtime Database
- PWA (Web App Manifest + Service Worker)

## Setup

1. Create a Firebase project and enable Realtime Database
2. Replace the `firebaseConfig` values in `index.html` with your own
3. Apply the security rules in `database.rules.json` via the Firebase Console:
   - Go to **Realtime Database → Rules** and paste the contents of `database.rules.json`
4. Host on GitHub Pages, Firebase Hosting, or any static host

## Firebase Security Rules

The file `database.rules.json` contains the rules for the database. Apply them in the Firebase Console under **Realtime Database → Rules** to prevent your access from expiring (the default test-mode rules expire after 30 days).

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

> **Note:** These rules leave the database publicly readable and writable. This is fine for a private family app, but do not store sensitive data.

## Children

The app supports 2 children. Names, avatars, and points are set on first launch and editable via the ✏️ Edit button.

## Avatars & Animations

20 animal avatars, each with 2 unique animations (dragon fire, wolf moonbeam, unicorn magic, etc.).
