# Habits PWA — Deployment Guide

## Files in this package

```
habits-pwa/
├── index.html       ← The full app
├── manifest.json    ← PWA config (name, icons, display mode)
├── sw.js            ← Service worker (offline support + caching)
├── icons/           ← You need to add these (see below)
│   ├── icon-192.png
│   └── icon-512.png
└── README.md        ← This file
```

---

## Step 1 — Create your app icon

1. Design a 1024×1024px PNG icon (square, no rounded corners — the OS handles that)
2. Go to **appicon.co** (free)
3. Upload your 1024px PNG
4. Download the generated pack
5. Grab the `192x192` and `512x512` PNGs
6. Place them in an `icons/` folder alongside `index.html`

---

## Step 2 — Deploy (pick one)

### Option A: Netlify (easiest — 2 minutes)
1. Go to **netlify.com** and sign up free
2. Drag your entire `habits-pwa/` folder onto the Netlify dashboard
3. Done — you get a live HTTPS URL instantly
4. Optional: connect a custom domain in Netlify settings

### Option B: GitHub Pages (free, reliable)
1. Create a new GitHub repo called `habits`
2. Upload all files to the repo root
3. Go to Settings → Pages → Source: main branch / root
4. Your app is live at `https://yourusername.github.io/habits`

### Option C: Vercel
1. Go to **vercel.com**, connect your GitHub
2. Import the repo — Vercel auto-detects it as a static site
3. Live in under a minute with a `.vercel.app` URL

---

## Step 3 — Test it

Once live, open the URL on your iPhone in **Safari** and check:

- [ ] App loads correctly
- [ ] Habits can be added, checked off, and viewed in detail
- [ ] Data persists after closing and reopening Safari
- [ ] "Add to Home Screen" prompt or toast appears

---

## Step 4 — Install on iPhone

In Safari on iPhone:
1. Tap the **Share** button (box with arrow)
2. Scroll down and tap **Add to Home Screen**
3. Tap **Add**

The app will appear on your home screen and launch fullscreen with no browser chrome — just like a native app.

---

## Updating the app

Any time you change `index.html`:
1. Re-upload to Netlify / push to GitHub
2. Bump the cache version in `sw.js` from `habits-v1` to `habits-v2`
3. Users will automatically get the update on next load

---

## Notes

- All data is stored in `localStorage` on the device — completely private, no server needed
- Works fully offline after the first load (service worker caches everything)
- Respects iOS light/dark mode automatically
- The install banner shows on Android; on iOS it shows a toast hint directing users to the Share menu
