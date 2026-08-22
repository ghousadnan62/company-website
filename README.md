# TerraLine Civil — Website

Static brand website for **TerraLine Civil**, a civil design studio (grading,
stormwater, hydrology, solar PV civil design). Pure HTML/CSS/JS — no build
step, no dependencies. Ready for GitHub Pages.

## File structure

```
terraline-website/
├── index.html          # Main single-page site
├── 404.html            # Custom error page (used by GitHub Pages automatically)
├── robots.txt          # SEO — update sitemap URL once live
├── sitemap.xml         # SEO — update domain placeholder once live
├── css/
│   └── styles.css      # Full design system
├── js/
│   └── main.js         # Menu, scroll reveals, nav highlighting, form
└── assets/
    └── favicon.svg     # Brand mark favicon
```

## Deploy to GitHub Pages

### Option A — User site (`yourusername.github.io`)
1. Create a new repository named `<your-username>.github.io`.
2. Upload **the contents of this folder** (not the folder itself — `index.html`
   must sit at the repo root).
   - Easiest: on the repo page → **Add file → Upload files** → drag everything in.
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch** → branch `main`, folder `/ (root)` → Save.
5. Your site goes live at `https://<your-username>.github.io` within a couple of minutes.

### Option B — Project site (e.g. `yourusername.github.io/terraline`)
Same as above but with any repo name (e.g. `terraline`). Source = `main` / root.
Live at `https://<your-username>.github.io/terraline/`. All asset paths in this
site are relative, so it works in both modes with zero changes.

### Custom domain (optional, recommended later)
1. Buy a domain (e.g. `terralinecivil.com`).
2. In **Settings → Pages**, enter the domain under **Custom domain**.
3. Create a file named `CNAME` (no extension) at the repo root containing:
   `terralinecivil.com`
4. At your DNS provider add: `A` records → GitHub's IPs (185.199.108.153, .154, .155, .156)
   and/or `CNAME` → `<your-username>.github.io`. Check **Enforce HTTPS** once active.

## Contact form setup (one-time)

The form posts to **FormSubmit** (free, no backend needed):

1. Open `js/main.js` and replace `info@terralinecivil.com` in `FORM_ENDPOINT`
   with your real email address (also update it in `index.html` where it appears).
2. Submit the form once — FormSubmit sends you an activation email. Confirm it.
3. Done: all inquiries land in your inbox.

Alternative: swap the endpoint for a Formspree/Basin/Netlify-style handler if preferred.

## Customization checklist

- [x] Replace `hello@terralinecivil.com` with `info@terralinecivil.com` (index.html + main.js)
- [ ] Add real project photos later if desired (replace the SVG drawings in the Work section)
- [x] Update `sitemap.xml` + `robots.txt` with the final URL
- [ ] Optional: add an `assets/og-image.png` (1200×630) for link-preview cards
  (already referenced in the HTML head)

## Tech notes

- Fonts: Fraunces (display), Inter (body), IBM Plex Mono (labels) via Google Fonts
- Animations: CSS contour draw-in on hero, IntersectionObserver scroll reveals,
  respects `prefers-reduced-motion`
- Responsive down to 360px; mobile has a full-screen overlay menu
- No frameworks, no build step — edit files directly and push
