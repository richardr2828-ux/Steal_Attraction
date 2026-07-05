# Stealth Attraction — Bridge Page

A curiosity-driven pre-landing ("bridge") page. Its only job is to warm up cold
traffic and push clicks to your external video presentation — it is **not**
the sales page itself.

## Project structure

```
stealth-attraction-bridge/
├── index.html          # All page content + SEO/Open Graph tags
├── style.css            # Full design system (dark, high-contrast, amber accent)
├── script.js            # CTA link injection, sticky mobile bar, year, click tracking hooks
├── README.md
└── assets/
    ├── favicon.svg
    └── og-cover.jpg     # Placeholder social-share image (1200×630) — swap for your own
```

## 1. Set your video link (do this first)

Open `index.html` and find this line near the top of `<body>`:

```html
<script>
  window.STEALTH_CTA_URL = "https://your-video-link-here.com";
</script>
```

Replace the URL with your real video presentation / VSL link. Every CTA
button on the page (`data-cta` links) picks up this one value automatically
via `script.js` — you only need to change it in one place.

## 2. Swap the placeholder social image (optional but recommended)

Replace `assets/og-cover.jpg` with your own 1200×630 image for Facebook,
Pinterest, and other social previews. Keep the same filename, or update the
`og:image` / `twitter:image` paths in `index.html`.

## 3. Update the domain in meta tags (optional)

In `index.html`, replace:

```html
<meta property="og:url" content="https://your-domain-here.com/">
```

with your real deployed URL once you have it.

## Deploying to GitHub Pages

1. Create a new GitHub repository and push these files to the root of the
   `main` branch (or a `docs/` folder — your choice).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch",
   choose `main` and `/ (root)`, then save.
4. GitHub will give you a URL like `https://yourusername.github.io/repo-name/`
   within a minute or two.

## Deploying to Vercel

**Option A — Vercel dashboard**
1. Go to [vercel.com/new](https://vercel.com/new) and import the GitHub repo
   (or drag-and-drop this folder if you're not using Git).
2. Framework preset: choose **"Other"** — this is a static site, no build
   step needed.
3. Leave the build command empty and the output directory as `.` (root).
4. Click **Deploy**.

**Option B — Vercel CLI**
```bash
npm install -g vercel
cd stealth-attraction-bridge
vercel
```
Follow the prompts; accept the defaults for a static project.

## Notes

- The page is fully responsive and uses a single dependency: Google Fonts
  (loaded via `<link>` tags). No build tools, frameworks, or bundlers
  required — just static files.
- A sticky "Watch The Presentation" bar appears on mobile once the visitor
  scrolls past the hero section, to keep the CTA reachable at all times.
- `script.js` includes optional hooks for Google Analytics (`gtag`) and Meta
  Pixel (`fbq`) click tracking — wire up your own tracking snippets in
  `index.html`'s `<head>` if you want conversion data, and the click events
  will fire automatically.
- Copy avoids explicit, crude, or exaggerated claims by design — tone is
  confidence- and psychology-focused throughout, per the brief.
