# 10k Tracker — Firebase Real-Time Sync

## What you get
- Both phones see each other's sessions instantly (live sync)
- Works offline — sessions queue and sync when back online
- Installs as a home screen app on iPhone and Android

---

## Step 1 — Set up Firebase (free, ~5 min)

1. Go to https://console.firebase.google.com and sign in with Google
2. Click **Add project** → name it `10k-tracker` → disable Analytics → Create
3. In the left sidebar: **Build → Realtime Database → Create database**
   - Choose your nearest region
   - Select **Start in test mode** → Enable
4. Go to **Project settings** (gear icon, top-left)
5. Scroll to **Your apps** → click the web icon `</>`
6. Register app as `10k-tracker` (no hosting needed)
7. Copy the `firebaseConfig` object shown — it looks like:

```js
const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "10k-tracker-xxxx.firebaseapp.com",
  databaseURL: "https://10k-tracker-xxxx-default-rtdb.firebaseio.com",
  projectId: "10k-tracker-xxxx",
  storageBucket: "10k-tracker-xxxx.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abcdef"
};
```

---

## Step 2 — Add your config to the app

Open `index.html` in any text editor and find this block near the top:

```js
const firebaseConfig = {
  apiKey:            "PASTE_API_KEY",
  authDomain:        "PASTE_AUTH_DOMAIN",
  ...
};
```

Replace each `"PASTE_..."` value with the real values from Firebase. Save the file.

---

## Step 3 — Deploy to Netlify (free, 2 min)

1. Go to https://netlify.com → sign up / log in
2. Click **Add new site → Deploy manually**
3. Drag the entire `10k-tracker-firebase` folder onto the upload area
4. You get a live URL like `https://yourname.netlify.app`

---

## Step 4 — Install on phones

**iPhone (Safari):**
Open the URL → Share button → Add to Home Screen → Add

**Android (Chrome):**
Open the URL → three-dot menu → Add to Home Screen

Send Rickie the same URL. Both of you pick your name on first open.
Sessions appear on both phones within seconds of being saved.

---

## Security note
The app uses Firebase "test mode" which allows anyone with the URL to
read/write data. This is fine for a private two-person app — just don't
share the URL publicly. After your race you can delete the Firebase project.
