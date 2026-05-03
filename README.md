# NEA Portfolio Marker

GCSE Pearson Edexcel Design & Technology — AI-assisted portfolio marking tool.
Calibrated to moderator standards. Improves accuracy with each corrected portfolio.

---

## Deploy to Netlify (step by step)

### Step 1 — Get the code onto GitHub

1. Go to **github.com** and sign in (or create a free account)
2. Click the **+** button → **New repository**
3. Name it `nea-marker`, leave it Public, click **Create repository**
4. On your computer, open a terminal in this folder and run:

```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/nea-marker.git
git push -u origin main
```

### Step 2 — Connect to Netlify

1. Go to **netlify.com** and sign in with your GitHub account
2. Click **Add new site** → **Import an existing project**
3. Choose **GitHub** and select your `nea-marker` repository
4. Netlify will auto-detect the settings from `netlify.toml`:
   - Build command: `npm run build`
   - Publish directory: `dist`
5. Click **Deploy site**

### Step 3 — Add your API key

1. In Netlify, go to **Site configuration** → **Environment variables**
2. Click **Add a variable**
3. Key: `ANTHROPIC_API_KEY`
4. Value: your Anthropic API key (starts with `sk-ant-...`)
5. Click **Save**
6. Go to **Deploys** → **Trigger deploy** → **Deploy site**

That's it — your site is live!

---

## How to use

1. Open your Netlify site URL
2. Drop a student portfolio PDF onto the upload area
3. Click **Mark Portfolio** — takes 30–60 seconds
4. Review the marks, levels, and justifications for all 11 criteria
5. Click any criterion to expand it and read the full justification
6. If the AI got a mark wrong, click **"Correct this mark"**, set the right level/mark, and write a brief reason
7. When done, click **"Save corrections to calibration memory"**
8. Future portfolios will automatically be marked using your corrections

---

## How the learning works

The tool starts with **15 built-in moderator-verified corrections** from two real portfolios,
covering the most common marking errors (2.2 one-line tables, 2.5 placement, 3.1a material
misconceptions, 4.1 photo-testing vs measured testing, etc.).

Every time you correct a mark and save it, that correction is stored in your browser's
localStorage and injected into the prompt for all future marking calls. The more portfolios
you mark and correct, the more accurate it becomes for your specific cohort and context.

---

## Calibration memory

Click the **🎯 Calibration Memory** button to:
- See all stored corrections (built-in seed data + your own)
- Remove any user-added corrections that are no longer relevant
- Track how many corrections are active

Built-in seed corrections cannot be removed (they are baked into the code).

---

## Notes

- PDF portfolios only (single or multi-file)
- Works best with digitally submitted portfolios; scanned PDFs also work but may be slower
- Indicative grades (1–9) are based on raw mark percentages — always apply centre-level grade boundaries
- This tool is an aid to professional judgement, not a replacement for it
