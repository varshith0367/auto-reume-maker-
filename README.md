# ResumeAI — AI Resume Maker & Auto Job Applier

A full-stack React app powered by Claude AI. Build resumes, tailor them to job descriptions, track applications, and auto-apply — all in one place.

---

## 🚀 Deploy to Vercel (5 minutes)

### Step 1 — Push to GitHub
1. Create a new repo on [github.com](https://github.com)
2. Upload all these files (drag & drop the folder), or run:
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/resumeai.git
git push -u origin main
```

### Step 2 — Deploy on Vercel
1. Go to [vercel.com](https://vercel.com) → **New Project**
2. Import your GitHub repo
3. Vercel auto-detects Vite — just click **Deploy**

### Step 3 — Add API Key
1. In Vercel dashboard → your project → **Settings** → **Environment Variables**
2. Add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** your key from [console.anthropic.com](https://console.anthropic.com)
3. Click **Redeploy** (Settings → Deployments → Redeploy)

✅ Done! Your app is live.

---

## 💻 Run Locally

```bash
# Install dependencies
npm install

# Create .env file
echo "ANTHROPIC_API_KEY=your_key_here" > .env

# Start dev server (needs separate API server for local)
npm run dev
```

> **Note for local dev:** The `/api/claude` route is a Vercel serverless function. For local testing, either deploy to Vercel or set up a simple Express server on port 3001.

---

## 📁 Project Structure

```
resumeai/
├── api/
│   └── claude.js          # Vercel serverless function (API proxy)
├── src/
│   ├── components/
│   │   ├── UI.jsx          # Shared UI components
│   │   ├── Builder.jsx     # Resume builder (5-step wizard)
│   │   ├── AiTailor.jsx    # AI resume tailor + chat
│   │   ├── JobTracker.jsx  # Job application tracker
│   │   └── AutoApply.jsx   # Auto apply assistant
│   ├── api.js              # Claude API utility
│   ├── App.jsx             # Main app + routing
│   ├── main.jsx            # React entry point
│   └── index.css           # Global styles
├── index.html
├── vite.config.js
├── vercel.json
└── package.json
```

---

## ✨ Features

- **Resume Builder** — 5-step wizard with live preview, AI-generated summary, AI skill suggestions, AI bullet points, AI project enhancement
- **AI Tailor** — Paste any job description, get match score, skill gaps, resume tweaks. Full AI chat assistant.
- **Job Tracker** — Track all applications with status pipeline (Saved → Applied → Interview → Offer/Rejected)
- **Auto Apply** — AI analyzes each job, generates tailored application package

---

## 🔒 Security

Your `ANTHROPIC_API_KEY` is stored as a Vercel environment variable and **never exposed to the browser**. All API calls go through the `/api/claude` serverless function.
