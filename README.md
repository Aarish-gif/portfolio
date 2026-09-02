# Aarish Khan — Portfolio

A single-page portfolio site (plain HTML/CSS, no build step, no framework).
Everything — including the profile photo — is embedded inside `index.html`,
so this folder is the entire project.

## Files

```
.
├── index.html      the whole site (HTML + CSS + embedded photo)
├── favicon.svg      browser tab icon
├── vercel.json      Vercel config (clean URLs)
├── package.json      project metadata (no build step required)
└── .gitignore
```

## Option A — Deploy with the Vercel CLI (fastest, no GitHub needed)

1. Install the CLI (needs Node.js installed):
   ```
   npm install -g vercel
   ```
2. From inside this folder, run:
   ```
   vercel
   ```
3. Follow the prompts:
   - Log in / create a free account when asked.
   - "Set up and deploy?" → Yes
   - "Link to existing project?" → No
   - "What's your project's name?" → press Enter to accept default, or type one
   - "In which directory is your code located?" → press Enter (`./`)
   - It will detect no framework — that's correct, just confirm.
4. Vercel prints a live URL (something like `aarish-khan-portfolio.vercel.app`) —
   open it, that's your site.
5. Any time you make changes, run `vercel --prod` from this folder to push a new
   version live.

## Option B — Deploy via GitHub + Vercel dashboard (best if you'll keep editing)

1. Create a new GitHub repository and push this folder to it:
   ```
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
2. Go to https://vercel.com → **Add New… → Project**.
3. Import the GitHub repository you just created.
4. Framework preset: choose **Other** (or leave as detected — it needs no build
   command since this is static HTML).
5. Click **Deploy**. Vercel gives you a live `*.vercel.app` URL.
6. From now on, every `git push` to `main` auto-deploys a new version — no need
   to touch the Vercel CLI again.

## Custom domain (optional, either option)

In the Vercel dashboard → your project → **Settings → Domains** → add your own
domain (e.g. `aarishkhan.dev`) and follow the DNS instructions Vercel shows you.

## Editing the site later

Everything lives in `index.html` — text, styles, and the embedded photo are all
in that one file. Open it in any text editor, change what you need, then either
run `vercel --prod` (Option A) or `git push` (Option B) to update the live site.
