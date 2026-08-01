# Wanhap — Marketing Site

Public marketing/institutional site for Wanhap (`wanhap.com`). This repository is unrelated to the Wanhap application codebase (Laravel/Vue), which lives in a separate repository.

## Stack

No framework — plain static HTML/CSS. The repo was empty with no prior technical direction, so this is the fastest path to something deployable on any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages, S3+CloudFront, etc.), with no build step required.

Clean URLs are achieved via folder + `index.html` (e.g. `/terms/index.html` serves at `/terms`). Most static hosts handle this out of the box; if the eventual host doesn't, add its specific redirect/rewrite config (`_redirects`, `vercel.json`, etc.) at that point.

```
/
├── terms/index.html      → /terms
├── privacy/index.html    → /privacy
├── assets/style.css      → shared minimal styling
└── README.md
```

## Status

Only the Terms of Use and Privacy Policy pages exist so far — no homepage yet. Both pages currently link to `/` in the nav/footer for when a homepage is added later; that link is a placeholder and not yet functional.

Both documents are marked `noindex` and carry an HTML comment at the top:

```
DRAFT — requires legal review before production use.
Generated as starting point, not legal advice.
```

**Do not remove the `noindex` meta tag or publish these pages as final until legal review is complete and all placeholders below are filled in.**

## Placeholders that need real values before publishing

Search both files for `[...]` — every bracketed placeholder is a fact this draft could not invent and left blank on purpose:

- `[COMPANY LEGAL NAME]`, `[CNPJ NUMBER]`, `[COMPANY ADDRESS]` — legal entity details
- `[EFFECTIVE DATE]`, `[LAST UPDATED DATE]`
- `[GOVERNING LAW / JURISDICTION — TO BE DETERMINED]`, `[JURISDICTION / VENUE — TO BE DETERMINED]` (terms)
- `[REFUND POLICY AND TIMEFRAME — TO BE DETERMINED]` (terms)
- `[CONTACT EMAIL]` (terms)
- `[DATA PROTECTION CONTACT EMAIL]` (privacy, appears twice)

## Content notes

- Terms of Use and Privacy Policy were written from scratch based on Wanhap's actual product model (multi-platform scheduling, OAuth token storage, S3-compatible media storage, third-party AI features, Account/Workspace structure, Stripe billing, 30-day grace period before deletion) — not adapted from any competitor's policy text.
- Privacy Policy references LGPD explicitly (Brazil) and GDPR generically (international reach), per the product's actual footprint.
- Not committed to git yet — this repo has no commit/push conventions defined. Review the content, then decide how you want it versioned.
