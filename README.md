# study-tracker
This is a app for study-tracker
# Study Tracker PWA — Setup Guide

## What this is
A Progressive Web App that installs on your iPhone and Android like a native app.
Data is stored in YOUR Google Sheet — works anywhere, no Mac needed.

---

## Step 1 — Host on GitHub Pages (free, 5 minutes)

1. Go to https://github.com and create a free account if you don't have one
2. Click **"New repository"**
3. Name it: `study-tracker`
4. Set it to **Public**
5. Click **"Create repository"**
6. Click **"uploading an existing file"**
7. Drag ALL 5 files into the upload area:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
8. Click **"Commit changes"**
9. Go to **Settings → Pages → Source → Deploy from branch → main → / (root)**
10. Click **Save**
11. Wait 2 minutes — your app URL will be:
    `https://YOUR-USERNAME.github.io/study-tracker`

---

## Step 2 — Google Cloud Setup

1. Go to https://console.cloud.google.com
2. Create a new project named `StudyTracker`
3. Go to **APIs & Services → Library**
4. Enable **Google Sheets API**
5. Enable **Google Drive API**

### Create API Key
1. Go to **APIs & Services → Credentials**
2. Click **+ Create Credentials → API Key**
3. Copy the key (starts with `AIzaSy...`)
4. Click **Edit** on the key → Restrict to **Google Sheets API**

### Create OAuth Client ID
1. Click **+ Create Credentials → OAuth Client ID**
2. If prompted, configure consent screen:
   - Choose External → fill in app name `StudyTracker` + your email → Save
3. Application type: **Web application**
4. Name: `StudyTracker`
5. Under **Authorised JavaScript origins** add:
   `https://YOUR-USERNAME.github.io`
6. Click **Create**
7. Copy the **Client ID** (ends with `.apps.googleusercontent.com`)

---

## Step 3 — Connect the App

1. Open your app URL on your phone:
   `https://YOUR-USERNAME.github.io/study-tracker`
2. The setup screen appears — enter:
   - **API Key**: from Step 2
   - **OAuth Client ID**: from Step 2
   - **Sheet ID**: leave blank (auto-creates a new sheet)
3. Tap **Connect to Google →**
4. A Google login popup appears — sign in and tap **Allow**
5. Your app loads — a Google Sheet called "Study Tracker Data" is created in your Drive

---

## Step 4 — Install on Home Screen

### iPhone (Safari only — Chrome won't work for PWA install on iOS)
1. Open the app URL in **Safari**
2. Tap the **Share** button (box with arrow)
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **"Add"**
5. The app icon appears on your home screen

### Android (Chrome)
1. Open the app URL in **Chrome**
2. Tap the **three dots menu** (top right)
3. Tap **"Add to Home screen"** or **"Install app"**
4. Tap **"Install"**
5. The app icon appears on your home screen

---

## Using the App

| Feature | How |
|---|---|
| Add subject | Tap the **+** button |
| Edit subject | Tap **Edit** on a card |
| Update progress | Drag the slider on a card |
| Filter subjects | Use the chips (All / In progress / etc.) |
| Calendar view | Tap 📅 in the bottom nav |
| Gantt chart | Tap 📊 in the bottom nav |
| Settings | Tap ⚙️ top right |

The green dot in the top right shows sync status:
- 🟢 Green = synced with Google Sheets
- 🟡 Yellow = syncing
- 🔴 Red = error

---

## Sharing with others

Since data is in Google Sheets:
1. Open https://drive.google.com
2. Find **"Study Tracker Data"**
3. Click **Share** → add your friend's email
4. They can view/edit your data directly in the sheet

---

## Troubleshooting

| Problem | Fix |
|---|---|
| "App not verified" warning | Click Advanced → Go to StudyTracker (safe for personal use) |
| Login popup blocked | Allow popups for your GitHub Pages URL in browser settings |
| Data not saving | Check the sync dot — if red, tap ⚙️ and tap Re-authenticate |
| Can't install on iPhone | Must use Safari, not Chrome |
| Sheet not found | Go to ⚙️ Settings and clear the Sheet ID to auto-create a new one |

---

*Study Tracker PWA v1 — works on iPhone + Android, no App Store needed*
