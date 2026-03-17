# Sampaguita — Deploy Guide

## What's in this folder
```
sampaguita/
  public/
    index.html      ← the full app
    manifest.json   ← makes it installable on phones (PWA)
  api/
    advice.js       ← secure backend (hides your API key)
  vercel.json       ← Vercel routing config
```

---

## Step 1 — Get your Anthropic API key

1. Go to https://console.anthropic.com
2. Sign up for a free account
3. Click **API Keys** in the left menu
4. Click **Create Key** → give it a name → copy the key (starts with `sk-ant-...`)
5. Save it somewhere safe — you'll need it in Step 4

---

## Step 2 — Put the code on GitHub

1. Go to https://github.com and sign up / log in
2. Click the **+** button (top right) → **New repository**
3. Name it `sampaguita` → click **Create repository**
4. On the next screen, click **uploading an existing file**
5. Upload ALL the files keeping the folder structure:
   - `public/index.html`
   - `public/manifest.json`
   - `api/advice.js`
   - `vercel.json`
6. Click **Commit changes**

---

## Step 3 — Deploy to Vercel

1. Go to https://vercel.com and sign up with your GitHub account
2. Click **Add New Project**
3. Find your `sampaguita` repo → click **Import**
4. Leave all settings as default → click **Deploy**
5. Wait ~30 seconds — Vercel builds it automatically

---

## Step 4 — Add your API key (important!)

Your API key must never be in the code. Vercel stores it safely:

1. In Vercel, go to your project → **Settings** → **Environment Variables**
2. Click **Add**
3. Name: `ANTHROPIC_API_KEY`
4. Value: paste your key (`sk-ant-...`)
5. Click **Save**
6. Go to **Deployments** → click the 3 dots on your latest deploy → **Redeploy**

---

## Step 5 — Share it

Your app is now live at:
`https://sampaguita.vercel.app` (or similar URL Vercel assigned)

Share this link with your users. On mobile, they can tap **Share → Add to Home Screen** to install it like an app.

---

## Updating the app later

Any time you update files on GitHub, Vercel automatically redeploys within ~30 seconds.
