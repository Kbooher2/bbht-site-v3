# Deploying BBHT v1.0

This folder is the complete website. It's plain HTML + CSS — no build step, no Node, no framework. You can open `index.html` in your browser right now and see the site.

## What's in this folder

```
website-v1/
├── index.html       ← Homepage
├── platform.html    ← The IOA Suite, all 5 modules + roadmap
├── company.html     ← About, case study, team, trust
├── contact.html     ← Demo request form
├── privacy.html     ← Privacy policy
├── styles.css       ← Shared stylesheet
├── robots.txt       ← Search engine instructions
├── sitemap.xml      ← Search engine sitemap
└── DEPLOY.md        ← This file
```

## Preview locally

Just double-click `index.html`. The whole site works offline because there are no external dependencies except a Google Fonts stylesheet and the page-fonts request degrades gracefully if blocked.

## Deploy options (in order of speed)

### Option 1 — Cloudflare Pages (recommended, ~10 minutes)

Free. Global CDN. Auto HTTPS. No server to manage.

1. Sign in at https://dash.cloudflare.com (create a free account if needed)
2. Workers & Pages → Create application → Pages → **Upload assets**
3. Project name: `bbhealthtech` (becomes `bbhealthtech.pages.dev`)
4. Drag the entire `website-v1` folder into the upload area
5. Click **Deploy site**. You get a live URL in ~30 seconds.

To point `bbhealthtech.com` at it:
6. In the project, Custom domains → **Set up a custom domain** → `bbhealthtech.com`
7. Cloudflare will either auto-configure (if your DNS is already at Cloudflare) or give you a CNAME record to add at your current registrar. The change usually propagates in 5–30 minutes.

### Option 2 — Netlify (similar, also free)

1. Sign in at https://app.netlify.com
2. Sites → **Add new site** → **Deploy manually**
3. Drag the `website-v1` folder into the drop zone
4. Site is live at a `*.netlify.app` URL immediately
5. Domain management → Add custom domain → follow their DNS instructions

### Option 3 — Any static host

The folder is fully static. Vercel, GitHub Pages, S3, Surge, an FTP server, your existing WordPress host's static hosting — anything that serves files works. Just upload all the files to the document root.

## After deploy

**Quick wins to do in the first hour after going live:**

1. **Make the form actually email you.** The contact form currently uses `mailto:` as a fallback, which opens the visitor's email client — works, but clunky. Replace it with Formspree (free tier):
   - Create an account at https://formspree.io and add a new form
   - In `contact.html`, change `<form action="mailto:Support@BBHealthTech.com" method="post" enctype="text/plain">` to `<form action="https://formspree.io/f/YOUR_FORM_ID" method="post">`
   - Delete the `enctype="text/plain"` attribute
   - Re-upload `contact.html` to your host
2. **Add Google Analytics or Plausible.** Drop the snippet into the `<head>` of each HTML file (search for `</head>` and add it just before). Plausible (https://plausible.io) is a cleaner privacy-friendly alternative and is what I'd recommend for a healthcare-adjacent business.
3. **Submit the sitemap.** Once live, go to Google Search Console (https://search.google.com/search-console), add `bbhealthtech.com` as a property, and submit `https://www.bbhealthtech.com/sitemap.xml`. Same for Bing Webmaster Tools.
4. **Add a favicon.** Drop a 32x32 PNG named `favicon.png` into the folder root, then add `<link rel="icon" href="/favicon.png">` inside the `<head>` of each HTML file.
5. **Add an OG preview image.** Same idea — drop a 1200x630 PNG (or JPG) and reference it as `<meta property="og:image" content="https://www.bbhealthtech.com/og.png">` in the `<head>` so LinkedIn/Slack/Twitter previews look polished.

## What's NOT in v1.0 (intentionally)

- **Blog / content marketing.** Add when you have something to publish. Easy to bolt on a Markdown-driven static blog generator later (Astro or Eleventy).
- **A real CMS.** Direct file editing for now. If you need non-technical edits, point me at it and we'll wire up a headless CMS (Sanity / Contentful) in a half-day.
- **Multiple language support.**
- **Per-module landing pages** (e.g., a dedicated `/admitiq` page for paid-ad campaigns). Easy to spin up when sales asks.
- **Customer login portal.** That stays on `app.bbhealthtech.com` (or wherever your platform lives) — the marketing site doesn't try to be a portal.

## How to edit content

The site is plain HTML. Open the `.html` file in any text editor (VS Code, Sublime, even Notepad), find the text, change it, save, re-upload. No build step required.

If you'd rather have a CMS or page builder, tell me what you'd find easiest to maintain and I'll wire it up.
