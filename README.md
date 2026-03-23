# Reely Legal Site

Static HTML/CSS pages for Reely's Privacy Policy, Terms of Use, and Support.

## Files

| File | Purpose |
|---|---|
| `config.js` | **All configurable values** — edit this before deploying |
| `styles.css` | Shared Reely-branded stylesheet |
| `index.html` | Landing page with links to all three documents |
| `privacy.html` | Privacy Policy |
| `terms.html` | Terms of Use |
| `support.html` | Support / Contact |
| `404.html` | Not-found page (served by host on missing routes) |

---

## Running locally

From the repo root:

```
npm run legal
```

Then open: http://localhost:3001

Uses `npx serve` (no install required). Port 3001 avoids conflicts with Expo's port 8081.

---

## Before deploying

Edit **`legal-site/config.js`** if anything changes:

```js
window.REELY = {
  APP_NAME:          'Reely',
  TAGLINE:           'Find something to watch together.',
  SUPPORT_EMAIL:     'reelysupport@gmail.com',  // ← update if email changes
  LAST_UPDATED_DATE: 'March 23, 2026',          // ← update when content changes
};
```

No other files need to change for a typical deploy.

---

## Deploying

These are plain static files — deploy anywhere that serves static HTML:

- **Vercel**: `vercel legal-site` or point a Vercel project at the `legal-site` folder
- **Netlify**: drag-and-drop `legal-site/` folder into Netlify dashboard, or use `netlify deploy --dir legal-site`
- **GitHub Pages**: push `legal-site/` contents to a `gh-pages` branch
- **Any CDN/host**: upload the folder contents as-is — no build step required

The app's `privacy.tsx`, `support.tsx`, and `about.tsx` screens reference the deployed URLs
via `PRIVACY_POLICY_URL` / `TERMS_URL` / `SUPPORT_EMAIL` constants at the top of each file.
Update those to match the live URLs before beta launch.
