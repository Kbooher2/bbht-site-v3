# bbhealthtech.com — v1.0

Marketing site for **BB HealthTech** (BBHT) — the connected operating layer for mid-market behavioral health RCM.

Static HTML/CSS, no build step, no framework. Five pages, one stylesheet. Designed to ship over the legacy WordPress site at `bbhealthtech.com`.

## Pages

| File | Description |
|---|---|
| `index.html` | Homepage — hero dashboard, IOA framework, 5 modules + IA card, AI roadmap, case study, integrations, testimonials |
| `platform.html` | The IOA Suite deep-dive — each of the 5 modules + AI roadmap + implementation timeline |
| `company.html` | About, case study, team, trust & compliance |
| `contact.html` | Demo-request form (mailto fallback, Formspree swap documented in DEPLOY.md) |
| `privacy.html` | Privacy policy |

## Preview locally

Double-click `index.html` — the site is fully self-contained.

To preview on a local server (clean URLs, no `file://` quirks):

```bash
# Python (built into macOS and Linux; available on Windows if installed)
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deploy

See [`DEPLOY.md`](./DEPLOY.md) for full instructions. Short version:

- **Cloudflare Pages** (recommended): drag the folder into Cloudflare Pages → live in 30 seconds → point `bbhealthtech.com` DNS at it
- **GitHub Pages**: enable in repo Settings → Pages → branch `main`, folder `/ (root)` → live at `https://kbooher2.github.io/bbhealthtech-website/`
- **Netlify**: drag the folder into Netlify Drop → instant preview URL

## Stack

- Plain HTML5 + CSS3
- One Google Fonts request (Inter)
- No JavaScript, no dependencies, no build
- Total page weight: ~92 KB across the whole site

## Brand

- Navy `#0F2A47` · Cyan `#1FA9D9` · Gold `#F5C842`
- Font: Inter

## License & ownership

Proprietary — © 2026 BB Healthcare Technology Partners LLC.
