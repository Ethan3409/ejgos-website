# ejgos.com

Marketing / customer-facing website for EJG Technologies Inc.

## Pages

- `index.html` — main landing
- `about.html`, `features.html`, `how-it-works.html`, `pricing.html`, `contact.html` — navigation
- `builders.html`, `installers.html`, `custom.html` — role-specific landing pages
- `privacy-policy.html`, `warranty.html`, `faq.html`
- `terms.html`, `support.html` — DRAFT pages (noindex, placeholders in `{{BRACES}}`); finish and remove the draft banner before publishing
- `docs/WORDING-RULES.md` — allowed and forbidden claims for any public copy
- `docs/store-listing.md` — App Store / Google Play listing drafts

## Local preview

Any static server works:

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Hosted on Netlify behind Cloudflare; pushing to `main` deploys. Domain `ejgos.com` is on Cloudflare.

## History

Extracted from `ejg-user` (the Pi PWA repo) on 2026-07-04 to work on independently without touching the Pi runtime.
