# BlueBull Investor MVP — Handoff

## Live URLs

- **Live site:** https://files-mentioned-by-the-user-pdf-2.vercel.app
- **GitHub:** https://github.com/utopia2283/bluebull-investor-mvp
- **Vercel project:** https://vercel.com/match2289s-projects/files-mentioned-by-the-user-pdf-2

Future `git push` to `main` will auto-deploy via Vercel.

## What was built

A single self-contained `index.html` (~78 KB) — bilingual (Traditional Chinese + English),
dark navy + red/cyan/gold palette, 11 sections with real interactivity so an LP can
*drive* the product instead of just read about it.

| Section | What it shows | Interactivity |
|---|---|---|
| Hero | "Hong Kong's credit system is 40 years behind. We're rebuilding it." | Animated network constellation (CRP / HK / GBA / BANK / ML) |
| FinancialGPT demo | "Compliance in the model" | 4 loan scenarios, animated 4-step processing, decision card |
| Consortium | Blue Bull Capital · Ping An · 中科院 | Static |
| Problem | 1 bureau / +80% cost / 0 GBA flow | Static |
| Iron Triangle | Capital × AI × Cryptography thesis | SVG diagram with 3 pillar labels |
| Architecture | 4 layers (Network / Crypto / AI / App) | Click each layer to highlight |
| Three engines | Per-pillar deep-dive | Static |
| Cost calculator | Live -80% math | 4 sliders (volume / headcount / cost / bureau fee) |
| Business model | Type I (banks) / Type II (money lenders) | Static |
| GBA cross-border flow | 5-gate encrypted handoff | Click steps or auto-play animated packet |
| Roadmap | 4 phases (Alliance → IA → Network → Launch) | Click to expand; "Play timeline" auto-advances |
| Numbers | 5.5M / 10× / -80% / 48-60mo | Static |
| The ask | Strategic capital, mailto CTAs | Static |
| Footer | Document map, consortium, contact | Static |

## What I verified

- HTTP 200, no console errors, no broken network requests
- No horizontal overflow at 1440px or 390px viewports
- Demo runs to completion: scenario buttons swap, 4 steps animate, decision card shows
- Calculator recalculates on every slider change
- GBA auto-play walks the packet HK → GBA across 5 gates
- All reveal-on-scroll animations trigger correctly

## What to verify before sending

- [ ] `strategy@bluebullvc.com` — replace with the real inbound inbox (or wire CTAs to a DocSend / Calendly)
- [ ] Legal entity name in the footer if you have one registered
- [ ] Add an HKD market-size card next to the 5.5M tile (HKMA publishes this quarterly)
- [ ] Phase 1 status — site says "Alliance & entity". If the joint lab LOI is signed, bump Phase 1 to "complete" and move IA forward
- [ ] CAS party — the deck uses 中國科學院 generically. If you have a specific lab name (計算所 / 數學與系統科學研究院), name it on the engines card

## File layout in the repo

```
.
├── .gitignore
├── README.md
├── vercel.json       # cleanUrls: true
├── index.html        # the entire site
├── outputs/
│   └── index.html    # duplicate of the above
├── work/             # scratch (gitignored)
└── brief.md          # this file
```

## Note on the reference you mentioned

The message included a link to `audio-visualization.md` from a Remotion skill — looked
like a stray reference from another thread. I didn't act on it; if you wanted audio
visualization on the site (e.g. a sound design for the demo reveal), say the word and
I'll add a minimal one with the Web Audio API.

## Update 2026-06-12 — Sample report generator

A new "Sample" section was added between the FinancialGPT demo and the problem
section. It generates fully synthetic credit reports on demand, mimicking the
TU HK report format (Summary / Personal / Score / Accounts / Inquiries tabs).
Click "Generate another" to produce a new random report. None of the names,
HKIDs, phones, addresses, or account numbers belong to a real person — they
are produced by the same client-side generator the production bureau uses
to render demo reports.

## Update 2026-06-12 — 繁/简 language switcher

A `[繁] [简]` toggle is now in the nav, just before the Investor Brief button.
Default is 繁 (Traditional). Click 简 to switch the entire page — including
the live sample report's tabs — to Simplified Chinese. Click 繁 to switch back.
The preference persists in localStorage.

Implementation: opencc-js (tw→cn only, 70KB) loaded from jsDelivr. The original
Traditional text is captured on first load so we can restore on toggle-back
without a reverse-conversion dictionary. The sample-report renderer re-applies
the current language to its dynamically-generated content on every tab switch.
