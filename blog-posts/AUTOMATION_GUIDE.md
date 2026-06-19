# Blog Post Automation Playbook

This document is the master instruction guide for AI coding agents generating, editing, or linking search-optimized blog posts. It covers the 3 types of blog posts we produce:
1. **Comparison Pages** (e.g., *Product A vs. Product B vs. Our Product*)
2. **Review Pages** (e.g., *Product Review: Is It Worth It?*)
3. **Alternatives Lists** (e.g., *Top 5 Product Alternatives*)

---

## 1. VERIFIED PRICING DATABASE (Strict No-Hallucination Rule)

When writing copy, pricing grids, specs, or comparison cards, you **MUST** reference these exact verified prices. Do not make up figures.

### eCommerce B-Roll & UGC Sourcing
* **UGCDrop (Our Product):**
  * *Pro Plan:* $28/month (30 downloads, plus access to 100k+ B-roll library).
  * *Unlimited Plan:* $49/month (100 downloads, plus unlimited downloads from its 100k+ B-roll library).
  * *Enterprise Plan:* $199/month (Unlimited downloads, plus unlimited downloads from its 100k+ B-roll library, custom creator briefs).
  * *Pay-As-You-Go Credits:* From $1.69 per clip (no subscription commitment).
  * *CTA/Link URL:* `https://ugcdrop.com`
* **GridBank:**
  * *Quarterly Plan:* $890/quarter (120 downloads, ~$7.41 per clip).
  * *Agency Plan:* Custom enterprise.
  * *CTA/Link URL:* `https://gridbank.io`
* **Billo:**
  * *Pricing:* Pay-per-video starting at $59. No platform subscription fees.
  * *CTA/Link URL:* `https://billo.app`
* **Trend.io (Trend):**
  * *Pricing:* Bundles start around $550.
  * *CTA/Link URL:* `https://trend.io`
* **Insense:**
  * *Pricing:* Software subscriptions from $300–$500/month + creator fees + 10–20% platform marketplace fee.
  * *CTA/Link URL:* `https://insense.pro`

### AI Video Presenters & Voice/Avatar Cloning
* **VidCloner (Our Product):**
  * *Starter Plan:* $19/month (5 videos/credits, ~$3.80 per video).
  * *Creator Plan:* $49/month (15 videos/credits, ~$3.27 per video).
  * *Master Plan:* $59/month (30 videos/credits, ~$1.96 per video).
  * *CTA/Link URL:* `https://vidcloner.com`
* **Arcads.ai:**
  * *Starter Plan:* ~$110/month (10 videos, ~$11 per video).
  * *Creator Plan:* ~$220/month (20 videos).
  * *CTA/Link URL:* `https://arcads.ai`
* **HeyGen:**
  * *Pricing:* Creator starts at $29/month. Custom voice cloning gated behind higher-tier Pro plans.
  * *CTA/Link URL:* `https://heygen.com`
* **Doublespeed:**
  * *Pricing:* Hosted device fleets starting at $1,500/month.
  * *CTA/Link URL:* `https://doublespeed.ai`

### TikTok Warmup & Regional Growth
* **Tikomate (Our Product):**
  * *Pricing:* US Accounts from $25 (one-time setup), Posting Guide ($29), Domination System ($79). Done-for-you, automated warmup & posting setups without SIMs or VPNs.
  * *CTA/Link URL:* `https://tikomate.com`
* **Genviral:**
  * *Pricing:* $29/month API scheduler.
  * *CTA/Link URL:* `https://genviral.com`

---

## 2. THE 3 BLOG POST TYPES & STRUCTURES

Every blog page must follow these block layouts and styles. Never write consecutive paragraphs (always follow paragraphs with a list, stat, or block).

### A. Comparison Pages (`comparison-[competitor].html`)
1. **Hero Section:** Title: `[Our Product] vs. [Competitor]: Which is best for [Use Case]?`
2. **TL;DR:** Summary card outlining the winner and core trade-offs.
3. **Intro:** 2-sentence hook setting up the performance difference.
4. **H2 Question:** *What is the main difference between [Our Product] and [Competitor]?* (Followed by direct answer, then bullets).
5. **Stat Block:** Visual stat block proving our advantage (e.g. 8x lower entry cost, etc.).
6. **Detailed H2s:** 2-3 specific feature breakdowns (e.g., turnarounds, licensing).
7. **Spec Comparison Table:** Side-by-side spec comparison matrix.
8. **Pricing Compared:** Grid comparing pricing columns.
9. **Decision Cards:** "Choose [Our Product] if..." vs "Choose [Competitor] if..." side-by-side.
10. **FAQs:** Minimum 3 frequently asked questions.
11. **CTA:** Bottom dark box linking to our product.

### B. Review Pages (`review-[competitor].html` or `review.html` for our products)
1. **Hero Section:** Title: `[Product] Review 2026: Is It Worth It?`
2. **TL;DR:** Verdict, rating, and ideal audience summary.
3. **Intro:** Sets up trust factors (e.g. reviews on G2) and walks through if it fits their workflow.
4. **H2 Question:** *What are the pros and cons of [Product]?* (Followed by Pro bullets and a warning-style callout for Cons).
5. **Workflow Steps:** Step-by-step walkthrough of using the tool.
6. **Specs Table:** Spec overview grid.
7. **Customer Quote:** Blockquote highlighting a user success story.
8. **FAQs:** Structured FAQs answering common objections.
9. **CTA:** Links to product.

### C. Alternatives Lists (`alternatives-[competitor].html`)
1. **Hero Section:** Title: `Best [Competitor] Alternatives (2026): Top 4 Tools Compared`
2. **TL;DR:** Explains why people leave the competitor, and names top alternatives.
3. **Intro:** Contextual hook.
4. **H2 Question:** *Why are brands looking for alternatives to [Competitor]?* (Bullet list of pain points).
5. **Alternative Profile Cards:** Modular profiles (using `.competitor-profile`) for each alternative, starting with our product as #1.
6. **Overview Comparison Table:** Summary table matching all alternatives on pricing and use case.
7. **FAQs:** Comparative questions.
8. **CTA:** Links to our product.

---

## 3. SEO / GEO ENGINE RULES
* **H2/H3 Headings:** Must be questions (pre-empting Perplexity/Google queries).
* **JSON-LD Schema:** Every page **MUST** contain structured data scripts in `<head>`:
  * A `Product` schema detailing pricing Aggregates.
  * A `FAQPage` schema mapping questions and answers.

---

## 4. DEPLOYMENT & HUB PLAYBOOK

Whenever you add or update a blog post:
1. Create/modify the HTML page under `blog-posts/[ugcdrop | vidcloner | tikomate]/[filename].html`.
2. Add the link in root [index.html](file:///Users/shailebhyanand/Documents/business/simon/simon%20content/index.html) with a category badge.
3. Deploy changes using:
   ```bash
   npx surge . simon-content-staging-2026.surge.sh
   ```
   *If Surge displays a 404 project not found, perform a teardown first, then deploy:*
   ```bash
   npx surge teardown simon-content-staging-2026.surge.sh
   npx surge . simon-content-staging-2026.surge.sh
   ```
