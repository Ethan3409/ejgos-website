# ejgos.com

Marketing / customer-facing website for EJG Smart Systems.

## Pages

- `index.html` — main landing (copy of `ejg-os-website.html`)
- `about.html`, `features.html`, `how-it-works.html`, `pricing.html`, `contact.html` — navigation
- `builders.html`, `installers.html`, `deploy.html`, `custom.html` — role-specific landing pages
- `marketing-site.html` — alternate compact landing page (older/simpler variant)
- `ejg-os-website.html` — source of `index.html`
- `privacy-policy.html`

## Local preview

Any static server works:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Static host — Cloudflare Pages, Netlify, Vercel, or drop into any S3/R2 bucket. Domain `ejgos.com` is on Cloudflare.

## History

Extracted from `ejg-user` (the Pi PWA repo) on 2026-07-04 to work on independently without touching the Pi runtime.
