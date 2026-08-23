# Deploying to GitHub — `awais-portfolio`

I can't push to GitHub myself (no write access to your account), so here's the exact
sequence to get this live in ~2 minutes.

## 1. Create the new repository

Go to https://github.com/new and create:
- Repository name: `awais-portfolio`
- Visibility: Public (required for free GitHub Pages)
- Do NOT initialize with a README, .gitignore, or license (this package already has files)

## 2. Push these files

From the folder containing this file, run:

```bash
git init
git add .
git commit -m "Initial deploy: Awais Shahid portfolio"
git branch -M main
git remote add origin https://github.com/<your-username>/awais-portfolio.git
git push -u origin main
```

Replace `<your-username>` with your actual GitHub username.

## 3. Enable GitHub Pages

In the new repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch
→ Branch: `main`, folder: `/ (root)` → Save.**

Your live URL will be:
`https://<your-username>.github.io/awais-portfolio/`

GitHub usually takes 1–2 minutes to publish after the first push.

## What's in this package

- `index.html` — the complete site (single file, no build step needed)
- `assets/cv/Awais_Shahid_Sales_Marketing_Manager.pdf` — the one CV linked from the site
- `assets/images/` — empty, reserved for future case-study creative assets (per the
  no-base64-images policy already applied to this site)

## QA already performed on this build

- Full tag/JS balance check — clean
- Every nav anchor (`#about`, `#results`, `#skills`, `#experience`, `#education`,
  `#reviews`, `#cvs`, `#contact`) resolves to a real section
- Mobile hamburger menu — fixed a real overlapping-hit-area bug found during this
  QA pass (nav links now have `display:block` so touch targets don't overlap)
- "View More Reviews" toggle — opens and closes correctly
- All contact links verified: `mailto:`, `tel:+971582605516`,
  `https://wa.me/971582605516`, LinkedIn, Fiverr — all present with `rel="noopener"`
  on external links
- Hero chart animation — plays on load, repeats while in view, pauses off-screen,
  and correctly shows the static completed chart when `prefers-reduced-motion` is on
- CV card decorative animation — same reduced-motion fallback confirmed
- Tested at 1440px (desktop), 390px (mobile), with full-page screenshots reviewed
