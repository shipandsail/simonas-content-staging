# Blog Posts — Claude Code Guide

## Project Overview
SEO blog post system for three products. All posts are static HTML files hosted on GitHub Pages.

## Critical: Deploy Setup
- Git repo root is **`/Users/shailebhyanand/Documents/business/`** — NOT inside `blog-posts/`
- The `index.html` hub lives at `/Users/shailebhyanand/Documents/business/index.html`
- Links in index.html use `blog-posts/` prefix (e.g. `blog-posts/ugcdrop/review.html`)
- GitHub repo: https://github.com/shipandsail/simonas-content-staging
- Live URL: https://shipandsail.github.io/simonas-content-staging/
- Deploy command (run from business/):
  ```
  cd /Users/shailebhyanand/Documents/business
  git add -A && git commit -m "message" && git push
  ```
- After adding any new post, add it to `/Users/shailebhyanand/Documents/business/index.html`

## Three Products

| Product | URL | Plans |
|---------|-----|-------|
| UGCDrop | ugcdrop.com | $28/mo (30 downloads), $49/mo (100 downloads), $199/mo (unlimited), $1.69/credit |
| VidCloner | vidcloner.com | $19/mo (5 videos), $49/mo (15 videos), $59/mo (30 videos) |
| Tikomate | tikomate.com | US Account $25, Posting Guide $29, Domination System $79 |

**Full verified pricing is in `VERIFIED_SITES_INFO.md` — always read it before writing copy.**

## File Structure
```
/Users/shailebhyanand/Documents/business/
├── index.html                          ← GitHub Pages hub (NOT in blog-posts/)
└── blog-posts/
    ├── AUTOMATION_GUIDE.md             ← Master content rules
    ├── VERIFIED_SITES_INFO.md          ← Verified pricing database
    ├── ugcdrop/
    │   ├── review.html
    │   ├── comparison-[competitor].html
    │   ├── alternatives-[competitor].html
    │   └── review-[competitor].html
    ├── vidcloner/
    └── tikomate/
```

## File Naming
- `comparison-[competitor].html` — e.g. `comparison-dansugc.html`
- `alternatives-[competitor].html` — e.g. `alternatives-shhotsai.html`
- `review.html` — our own product review
- `review-[competitor].html` — competitor review
- Root-level hub pages — e.g. `ugc-video-software.html`

## Three Post Types

### Comparison (`comparison-[competitor].html`)
1. Hero → TL;DR → Intro
2. H2: "What is the main difference between X and Y?"
3. Stat block proving our advantage
4. 2–3 H3 feature breakdowns
5. Spec comparison table
6. Pricing columns (`.cmp-pricing`)
7. Customer quote
8. Decision cards (`.cmp-choose`) — "Choose X if..." / "Choose Y if..."
9. FAQs (min 4)
10. Dark CTA block

### Alternatives (`alternatives-[competitor].html`)
1. Hero → TL;DR → Intro
2. H2: "Why do people look for alternatives to [Competitor]?"
3. Pain point bullet list
4. Stat block
5. Ranked profiles (`.competitor-profile`) — our product always #1
6. Overview comparison table
7. FAQs (min 4)
8. Dark CTA block

### Review (`review.html`)
1. Hero → TL;DR → Intro
2. H2: "What are the pros and cons of [Product]?"
3. Workflow steps
4. Specs table
5. Customer quote
6. FAQs
7. CTA

## HTML Rules
- **Always read an existing post of the same type before writing a new one** — copy CSS verbatim
- CSS is minified/inline in `<style>` tag in `<head>` — no external stylesheets
- Google Fonts: Inter (400/500/600/700/800)
- Every page needs JSON-LD in `<head>`: `Product` schema + `FAQPage` schema
- Hero image: Unsplash URL with `?q=80&w=1536&h=1024&auto=format&fit=crop`
- Never write consecutive paragraphs — always follow with a list, stat, or callout block
- H2/H3 headings must be questions (for Perplexity/Google query targeting)

## No-Hallucination Rule
- **Never invent pricing, features, or specs** for any tool
- Competitor data must come from content the user pastes into the session
- UGCDrop/VidCloner/Tikomate data must come from `VERIFIED_SITES_INFO.md`
- If you don't have verified data for a competitor, **ask before writing**

## Workflow for New Posts
1. User pastes competitor blog/pricing page content
2. Read `VERIFIED_SITES_INFO.md` for our product pricing
3. Read an existing post of the same type for CSS reference
4. Write the post
5. Add entry to `/Users/shailebhyanand/Documents/business/index.html`
6. Deploy from `/Users/shailebhyanand/Documents/business/`

## Common Competitors Already Covered (UGCDrop)
- Arcads, GridBank, MakeUGC, ReelFarm, DansUGC, Shhots AI, Creatify (via arcads-vs-creatify), Fastlane, Trend.io, Insense, Minisocial
