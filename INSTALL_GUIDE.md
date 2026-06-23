# JavaQuest — Install Guide

JavaQuest is a Progressive Web App (PWA). It is **not** an .apk/.exe binary —
browsers and app stores require official build/signing toolchains for that —
but installed this way it behaves exactly like a native app: own icon, own
window, works offline, saves your data on-device. This is the same method
real companies (Twitter/X, Starbucks, Spotify lite) use for their lite apps.

## 1. Run it locally first (any device)
You can't just double-click `index.html` for full functionality (notifications
and offline caching need a real server). Easiest free option:

1. Install **Python** (most PCs already have it) or use any static file server.
2. Open a terminal in the `javaquest` folder.
3. Run: `python3 -m http.server 8080`
4. Open `http://localhost:8080` in Chrome/Edge (on PC) or
   `http://<your-PC-IP>:8080` from your phone (same WiFi).

(Alternative: upload the folder to any free static host like Netlify Drop,
GitHub Pages, or Vercel — takes 2 minutes, gives you a private link you and
your loved ones can open from anywhere.)

## 2. Install on Android (gives you a home-screen icon, like an app)
1. Open the link in Chrome.
2. Tap the **⋮ menu → "Add to Home screen" / "Install app"**.
3. It now opens full-screen with its own icon — no browser bar.

## 3. Install on Windows / Mac (gives you a desktop app + taskbar icon)
1. Open the link in Chrome or Edge.
2. Click the **install icon (⊕) in the address bar**, or
   menu → "Install JavaQuest".
3. It opens in its own window from the Start Menu / Applications folder from then on.

## 4. Want an actual signed .apk or .exe file instead?
If you specifically want a real installable binary (e.g. to share without
anyone needing a link), the standard no-cost path is:
- **APK**: feed this same folder into **PWABuilder.com** (free, made by Microsoft) →
  it packages your PWA into a real signed .apk in a few clicks.
- **EXE**: use **Electron** or PWABuilder's Windows packager the same way.
Both are free tools you run yourself — I can't generate signed binaries
directly in this chat, but the app itself (this folder) is 100% ready to feed
into either of them with zero code changes.

## What's inside
- `index.html` — the whole app (setup wizard, roadmap, daily tracker, reviews, alarms, quotes)
- `manifest.json` — makes it installable
- `sw.js` — offline support
- `icons/` — app icons

## Notes on alarms
Real OS-level alarms can't be set by a website/PWA for security reasons (no
browser can reach into your phone's Clock app). JavaQuest's "Set All Alarms"
fires in-app notifications at the right times **while the app is open** —
the honest workaround. For wake-up-critical alarms, keep using your phone's
native Clock app alongside JavaQuest's daily time list.
