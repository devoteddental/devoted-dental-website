# Devoted Dental Group Website

Static site for Devoted Dental Group's 5 Metro Detroit locations
(Chesterfield, Highland, Livonia, Warren, Wyandotte).

## Structure
- Root `.html` files — main pages and city/service landing pages
- `blog/` — blog posts
- `assets/` — images, team photos, downloads
- `netlify/functions/` — serverless functions (provider referrals,
  employment applications, chat widget)
- `_redirects` — Netlify redirect rules (includes legacy WordPress
  URL preservation)
- `sitemap.xml`, `robots.txt` — SEO

## Required environment variables (set in Netlify, never in code)
- `ANTHROPIC_API_KEY` — for the chat widget function
- `PAUBOX_API_KEY` — for provider referral and employment form
  email delivery

## Deployment
Connected to Netlify for continuous deployment — pushes to `main`
deploy automatically. `netlify.toml` sets `functions = "netlify/functions"`
and `publish = "."`.

## Conversion tracking — read before touching anything tracking-related
GTM (`GTM-NM8FD7D4`) and GA4 (`G-1W8KPY8S6R`) base tags are installed
sitewide. Google Ads conversion events are deliberately isolated to
exactly 5 files — the office thank-you pages
(`thankyou-{office}-uploaded.html`) — each firing its own office's
Conversion ID/Label. This scoping is intentional; conversion-firing
code should never appear outside these 5 files.
