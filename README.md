# Shared Calendar — Setup Guide

A mobile-first shared calendar that works offline and can be added to your phone's home screen.

---

## Quick start

1. Put all these files on any web host (see options below)
2. Open the URL on your phone
3. Tap "Install" when prompted (or use your browser's "Add to Home Screen")

---

## Hosting options (free)

### Option A — GitHub Pages (recommended, free forever)
1. Create a free account at github.com
2. Create a new repository called `shared-calendar`
3. Upload all the files from this folder (index.html, manifest.json, sw.js, and the icons/ folder)
4. Go to Settings → Pages → Source: "Deploy from branch" → main
5. Your URL: `https://YOUR-USERNAME.github.io/shared-calendar`

### Option B — Netlify Drop (easiest, free)
1. Go to app.netlify.com/drop
2. Drag the entire `calendar-app` folder onto the page
3. Done — you get a free URL instantly like `https://random-name.netlify.app`

### Option C — Any web server / NAS
Just copy the files to any folder served over HTTPS.

---

## Adding to home screen

### iPhone / iPad (Safari)
1. Open your calendar URL in **Safari** (must be Safari, not Chrome)
2. Tap the **Share** button (box with arrow pointing up) at the bottom
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **Add** — the calendar icon appears on your home screen
5. Open it — it now runs like a full app, no browser bar

### Android (Chrome)
1. Open your calendar URL in **Chrome**
2. Tap the **⋮ menu** (three dots) at the top right
3. Tap **"Add to Home screen"** or **"Install app"**
4. Tap **Add/Install** — it appears on your home screen
5. Opens full-screen just like a native app

---

## Home screen widget (shows upcoming events)

### iPhone — using Scriptable
1. Install **Scriptable** (free) from the App Store
2. Open Scriptable → tap **+** to create a new script
3. Copy the entire contents of `widget-ios.js` and paste it into Scriptable
4. Name the script **"Shared Calendar"**
5. To export your events from the main app: open the app → tap ⇅ (share icon) → Copy
6. In Scriptable, import the data (the widget reads from iCloud)
7. Long-press your home screen → tap **+** → search **Scriptable**
8. Choose Small, Medium, or Large → Add Widget
9. Tap the widget → set Script to **"Shared Calendar"**

### Android — using KWGT or Widgetsmith
Android widgets require third-party widget apps. The simplest approach:
- Use **Widgetsmith** or **KWGT** to create a web-based widget pointing to your calendar URL
- Or use **Tasker + HTTP Request** to fetch and display events

---

## Sharing events with others

Since this app stores events locally on each device, sharing works via export/import:

1. Open the app → tap the **⇅** icon in the header
2. Tap **Copy** to copy your event data
3. Paste it into a message/email and send to your contact
4. They open the app → tap **⇅** → paste in the Import box → tap **Import & merge**
5. Their new events merge with yours without duplicates

> **Tip:** Share again periodically to stay in sync.

---

## Files included

| File | Purpose |
|---|---|
| `index.html` | Main app — open this in a browser |
| `manifest.json` | Makes it installable as a PWA |
| `sw.js` | Service worker for offline support |
| `icons/` | App icons for home screen |
| `widget-ios.js` | iOS Scriptable home screen widget |
| `README.md` | This file |

---

## Features

- 📅 Monthly calendar view with color-coded events
- ➕ Add events with title, time, end time, notes, and color
- 👤 Events tagged with your name so others know who added them
- 🔄 Export/import to share events with anyone
- 📴 Works fully offline after first load
- 🌙 Automatic dark mode support
- 📲 Installable on iPhone and Android home screens
- ⌨️ Keyboard shortcuts (Escape to close, Enter to save)
