# Devasdf website

Static site (plain HTML/CSS, no build step) for Devasdf, deployed on Vercel's free (Hobby) plan.

| URL | File |
|---|---|
| `/` | `index.html` — landing page |
| `/privacy` | `privacy/index.html` — Privacy Policy (use this URL in Google Play Console) |
| `/terms` | `terms/index.html` — Terms of Use |
| any unknown path | `404.html` |

`/privacy-policy` and `/terms-of-use` redirect to the pages above (see `vercel.json`).

## Deploy to Vercel

**Option A — GitHub (auto-deploys on every push)**
1. Push this folder to a GitHub repo.
2. vercel.com → Add New → Project → import the repo.
3. Framework preset: **Other**. Leave Build Command and Output Directory empty. Deploy.

**Option B — CLI**
```bash
npm i -g vercel
vercel          # first time: links the project
vercel --prod   # deploys to production
```

## After the first deploy
The site assumes the domain `devasdf.vercel.app`. If Vercel gives you a different one (or you add a custom
domain), find-and-replace `devasdf.vercel.app` in: `index.html`, `privacy/index.html`, `terms/index.html`,
`robots.txt`, `sitemap.xml`.

Then in Google Play Console → App content → Privacy policy, paste `https://<your-domain>/privacy`.
Per-app deep links also work: `/privacy#dejadot`, `/privacy#helpline`, `/privacy#wayback`.

## Updating
- App icons: `assets/apps/*.png`
- Colours: the `:root` variables at the top of `assets/styles.css`
- When an app reaches Google Play, replace its "Coming soon" link in `index.html` with the Play Store URL.
- If an app's data handling changes, update its section in `privacy/index.html` and the "Last updated" date.
