# Rugby & Run Tracker

Personal training tracker with AI Coach, offline support, and PWA install.

---

## Deploy in ~15 minutes (free)

### Step 1 — GitHub
1. Go to [github.com](https://github.com) → sign up or log in
2. Click **+** → **New repository**
3. Name it `rugby-run-tracker`, keep it Public, click **Create**
4. On the next screen click **uploading an existing file**
5. Drag in ALL the files from this zip (keep the folder structure)
6. Click **Commit changes**

### Step 2 — Anthropic API Key
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up → add $5 credit (covers ~6 months of personal use)
3. Go to **API Keys** → **Create Key**
4. Copy the key — you'll need it in Step 3

### Step 3 — Vercel (hosting + AI proxy)
1. Go to [vercel.com](https://vercel.com) → **Sign up with GitHub**
2. Click **Add New Project** → select `rugby-run-tracker`
3. Before clicking Deploy, click **Environment Variables** and add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** paste your key from Step 2
4. Click **Deploy**
5. In ~60 seconds you get a live URL like `rugby-run-tracker.vercel.app`

### Step 4 — Add to iPhone home screen
1. Open your URL in **Safari** on iPhone
2. Tap the **Share** button (box with arrow pointing up)
3. Scroll down → tap **Add to Home Screen** → tap **Add**

It opens full-screen like a native app. Works offline. All data saved locally.

---

## How the AI Coach works

The `api/claude.js` file is a serverless function that runs on Vercel's servers.
When you use the AI Coach in the app, your browser calls `/api/claude` (not Anthropic directly).
Vercel injects your `ANTHROPIC_API_KEY` server-side — it's never visible in the browser.

---

## Local development

```bash
npm install
npm run dev
```

For local AI to work, create a `.env` file:
```
ANTHROPIC_API_KEY=your_key_here
```

## Build
```bash
npm run build
```
