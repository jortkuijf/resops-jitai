# ResOps — Deploy to GitHub Pages (iPhone)

## What you need
- A free GitHub account (github.com)
- These 5 files in this folder:
  - `index.html`
  - `manifest.json`
  - `sw.js`
  - `icon-192.png`
  - `icon-512.png`

---

## Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** button (top right) → **New repository**
3. Name it: `resops-jitai`
4. Set to **Public**
5. Click **Create repository**

---

## Step 2 — Upload the files

1. On the new repo page, click **Add file** → **Upload files**
2. Drag all 5 files into the upload area
3. Scroll down, click **Commit changes**

---

## Step 3 — Enable GitHub Pages

1. Go to **Settings** (in your repo) → **Pages** (left sidebar)
2. Under **Source**, select **Deploy from a branch**
3. Branch: `main` | Folder: `/ (root)` → click **Save**
4. Wait ~60 seconds, then refresh — your URL will appear:
   `https://YOUR-USERNAME.github.io/resops-jitai/`

---

## Step 4 — Install on iPhone as a PWA

1. Open the URL in **Safari** on your iPhone (must be Safari, not Chrome)
2. Tap the **Share** button (rectangle with arrow at the bottom)
3. Scroll down → tap **Add to Home Screen**
4. Name it `ResOps` → tap **Add**
5. Open it from your home screen — it launches fullscreen, like a native app

---

## Using the prototype on iPhone

Since iOS does not support Web Bluetooth, use **Simulation mode**:

1. Tap **Start Simulation**
2. The app runs a realistic incident scenario (resting → incident → elevated → recovery)
3. After ~90 seconds the baseline calibrates and the HR rises above threshold
4. The **bottom sheet alert fires** automatically with the box breathing exercise
5. Try the breathing exercise, then tap **Complete** to log the reset

The simulation demonstrates the complete JITAI flow as officers would experience it.

---

## Updating the app

To push updates:
1. Edit the files locally
2. Go to your GitHub repo → the file → click the **pencil icon** to edit, or re-upload
3. Changes go live within ~30 seconds

---

## iOS limitations (relevant for your thesis)

| Feature | iPhone (this prototype) | Android / Desktop |
|---|---|---|
| Heart rate monitor (BLE) | ❌ iOS blocks Web Bluetooth | ✅ Works in Chrome |
| Simulation mode | ✅ Full flow | ✅ Full flow |
| Vibration on alert | ❌ iOS blocks Vibration API | ✅ Works |
| Audio chime | ✅ Works after first tap | ✅ Works |
| Home screen install | ✅ Add to Home Screen | ✅ Install prompt |
| Works offline | ✅ Service worker cached | ✅ |

A production iOS build would require a native Swift app using HealthKit + CoreBluetooth.
