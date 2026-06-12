# BlueBull — Investor MVP

A bilingual (Traditional Chinese + English) single-page investor site for
[BlueBull](https://files-mentioned-by-the-user-pdf-2.vercel.app), a consortium of Blue Bull Capital, Ping An One
Connect, and the Chinese Academy of Sciences building Hong Kong's third credit
bureau seat on privacy-computing + AI + GBA cross-border rails.

## What's in here

- `index.html` — the entire site (HTML + inline CSS + inline JS, ~78 KB)
- `vercel.json` — Vercel routing config (clean URLs)
- `brief.md` — design rationale, what to verify before sending, follow-ups

No build step, no framework, no dependencies. Open `index.html` in a browser
or deploy to any static host (Vercel, Netlify, Cloudflare Pages, S3+CloudFront).

## Deploy

```bash
# Vercel (this repo)
vercel --prod

# Or any static host
rsync -avz --delete ./ user@host:/srv/bluebull/
```

## Sections

1. Hero — bilingual headline, animated network constellation
2. Live FinancialGPT demo — 4 scenarios, animated AI processing
3. Consortium strip — Blue Bull / Ping An / CAS
4. Problem — three failure cards (one bureau / +80% cost / 0 GBA flow)
5. Iron Triangle — Capital × AI × Cryptography, SVG diagram
6. Architecture — 4-layer click-to-explore stack
7. Three engines — per-pillar detail
8. Cost calculator — drag-the-sliders -80% math
9. Business model — Type I (banks) / Type II (money lenders)
10. GBA cross-border flow — animated 5-gate handoff
11. Roadmap — 4 phases, click-to-expand
12. Numbers — 5.5M / 10× / -80% / 48-60mo
13. The ask — strategic capital, mailto CTAs
14. Footer

## Privacy

No PII from any source PDF is republished. The site uses the deck's
numbers (5.5M consumers, +80% cost, 10× compliance, 48-60mo runway),
not data from individual credit reports.
