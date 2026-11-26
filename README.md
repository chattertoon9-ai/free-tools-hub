# Free Tools Hub — GitHub Pages deploy package

Ready-to-publish files for the Free Tools Hub (10 free online tools:
Unit Converter, BMI, Age, Percentage, QR Code, Word Counter, Password
Generator, Loan/EMI, Image Compressor, PDF guide + in-browser PDF
inspector; plus About, Privacy, Terms, Contact and Site Audit views).

## Related site
- **Converters:** https://converters.alasadconstructors.com/ — dedicated
  length, weight, temperature, area, volume and time converter pages,
  with step-by-step conversion guides.

## Files
- `index.html` — the whole site, single self-contained file (82 KB).
  External CDN libraries it loads at runtime: QRCode.js and PDF.js
  (cdnjs), Google Fonts. No server code, no sign-up, no uploads.

## Why this folder exists
The GitHub connector in this workspace cannot create a repository:
`create_repository` returns `403 Resource not accessible by integration`.
So the repo must be created once by the account owner, then these files
can be pushed with the GitHub connector's push_files.

## Deploy steps (owner)
1. On github.com, create a new **public** repository named
   `free-tools-hub` under the account `chattertoon9-ai`. Leave it empty
   (no README, no .gitignore, no licence).
2. Push this folder's `index.html` to the repo's `main` branch
   (the connector's push_files can do this once the repo exists).
3. In the repo: Settings → Pages → Source: "Deploy from a branch",
   branch `main`, folder `/ (root)` → Save.
4. Live URL will be: https://chattertoon9-ai.github.io/free-tools-hub/
   (allow a few minutes for the first build; hard-refresh if cached).
5. Submit that URL to Google Search Console and request indexing.
   Only after the site is live and indexed should the AdSense
   application be made (AdSense code + ads.txt go in after approval
   steps, per the in-site Audit page).

## Audit status (19 Nov 2026, on the built site)
- All 10 tools present with working logic; audit-table results
  re-verified by independent recomputation (180 cm = 70.87 in,
  12 kg = 26.46 lb, BMI 24.2, EMI 22,244 on 1,000,000 @ 12% / 5 yrs).
- Inline JavaScript parses cleanly (node --check).
- About, Privacy (with AdSense cookie disclosure), Terms, Contact
  (Chattertoon9@gmail.com) and Site Audit pages all present.
- Mobile viewport set; JSON-LD structured data and Open Graph tags present.
- Gaps before AdSense application: (1) site not yet live on a public
  URL — blocked on repo creation above; (2) no sitemap.xml/robots.txt
  (single-page site; add when live); (3) per-tool pages are hash views
  (#/tool) in one file, not separate URLs — weaker per-tool SEO than
  separate pages; (4) AdSense code and ads.txt not yet placed (correct
  to wait until the live site is submitted); (5) QR render and PDF text
  extraction could not be live-tested in the sandbox (CDN blocked
  there) — verify on the live URL after deploy.
- No AdSense application was made and no payment/bank details entered.
