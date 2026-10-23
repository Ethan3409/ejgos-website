# Growth plan: off-site steps

The site now has the pages search engines and AI tools look for (FAQ, service area, builders, four sourced comparisons, llms.txt, structured data, sitemap). A new page does not rank by itself. These steps happen outside the repo and need the owner.

## 0. Before anything is published
- Fill or remove every `{{PLACEHOLDER}}` (`grep -rn "{{" *.html`): `{{SERVICE_AREA}}`, `{{HOURS}}`, `{{BUILDER_TERMS}}`, `{{STREET_ADDRESS}}` / `{{POSTAL_CODE}}` (index structured data), plus those already on terms, support and privacy.
- Remove the draft banner and `noindex` from terms and support only when they are final.
- Sentences marked `<!-- PUBLISH-GATE: customer app builds -->` stay until the customer app builds that show cameras ship.
- Re-read each comparison page against the live vendor pages (sources and dates are listed on each page) and update the "Last reviewed" date.

## 1. Make sure Google can see the site
1. Google Search Console: add `https://ejgos.com` as a Domain property (DNS TXT record in Cloudflare).
2. Submit `https://ejgos.com/sitemap.xml`; use URL Inspection on `/`, `/faq`, `/service-area`, `/pricing` and request indexing.
3. Bing Webmaster Tools: import the site from Search Console and submit the sitemap. (Bing also feeds several AI search tools.)
4. Check Page indexing weekly for the first month and fix anything "Excluded".

## 2. Local listings (what makes "smart home Calgary" show a map result)
- Google Business Profile: category "Home automation company" (or the closest available); service-area business if no public street address, otherwise the address. Add the phone number, `info@ejgos.com`, hours, service area (Calgary, Airdrie, Cochrane, Okotoks, Chestermere, Springbank), photos of real installs (with the owner's permission), and the site link. Verification may take a postcard, video or phone call.
- Bing Places for Business (can import from Google).
- Apple Business Connect.
- Keep the name, phone and address identical everywhere (company name EJG Technologies Inc.).
- Directories worth the time: Alberta and Calgary business directories, the Calgary chamber of commerce, Better Business Bureau, home-builder and renovation associations the company qualifies for. Skip paid link schemes.

## 3. Reviews
- After each install, ask the homeowner for a Google review with a direct link. Ask every customer; never offer payment or discounts for reviews, and never write your own.
- Reply to every review, short and factual.

## 4. Backlinks
- Local trade and builder associations, supplier and manufacturer "installer" pages, local news or podcasts, and any builder project that agrees to a case study with its own name and photos.
- Link to ejgos.com from the company profiles the owner already has (social profiles, app store listings, GitHub).

## 5. Domain and identity
- Confirm WHOIS contact privacy is on and the registrant is EJG Technologies Inc.
- Keep `ejgos.com` as the canonical host (www already redirects). Renew for several years.
- Set up SPF, DKIM and DMARC for `info@ejgos.com` so replies to enquiries do not land in spam.

## 6. Measuring (privacy-respecting)
- The site has no analytics or trackers today and the privacy policy says so. Keep it that way unless the policy is updated first.
- Search Console shows queries, impressions and clicks without any script on the site. Start there.
- If page-view counts are wanted later, choose a cookie-free, self-hosted or privacy-focused tool, and update the privacy policy and the Content-Security-Policy in `_headers` before adding it.

## 7. Content cadence
- Add real answers to the FAQ whenever a customer asks something new (the FAQ structured data is generated from the same text; keep the visible text and the JSON-LD identical).
- Re-review the comparison pages every quarter.
- A separate company site (EJG Technologies Inc.) is optional; if built, link it from the product site and use `parentOrganization`.
