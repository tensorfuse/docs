# Whip Help Center — project instructions

## About this project

- Consumer-facing help center, FAQ, and changelog for **Whip** (whip.run) — the mobile app
  where anyone builds mini apps by chatting with AI. Built on [Mintlify](https://mintlify.com).
- Pages are MDX with YAML frontmatter; configuration lives in `docs.json`.
- Audience: everyday consumers (18+), NOT developers. Spell everything out.
- SEO is the top priority: every page needs a question/task-phrased `title` (≤60 chars),
  a 120–158 char `description`, `keywords`, and an answer-first opening paragraph
  (40–60 words that fully answer the title on their own).

## Terminology

- The product is **Whip**; the website is **whip.run**; the company is Tensorfuse, Inc.
- What users make: "app" in most prose; "a Whip" only when quoting UI ("Your Whip is
  Ready!"); "mini app" at most once per page, for definitions/SEO.
- Verbs: **build**, **edit** (not refine, in user-facing copy), **remix**, **publish**,
  **share**, **play**, **save**, **like**. "tap" never "click"; "sign in" never "log in".
- Feed tabs are **For You** and **Trending** (there is no Following tab).

## Style preferences

- Warm, plain-spoken, lightly playful — same energy as whip.run marketing. Never corporate.
- Active voice, second person, short sentences. Sentence case headings.
- Bold for UI elements: tap **Publish**. Paths like Settings → Permissions.
- Banned: "simply", "just", "easy", "obviously"; developer jargon (API, WebView, backend,
  SSE, endpoint); invented numbers, limits, or UI labels.
- Whip is free — never invent pricing, credits, or a "Pro" tier.
- Every page ends with a `## Related` CardGroup (2 cards). 3–6 internal links per page.
- Components: Steps for how-tos, AccordionGroup for FAQs, Tabs only for iOS/Android forks,
  CardGroup for navigation, Note/Tip/Warning callouts (1–3 per page).

## Content boundaries

- Facts come from the app and backend as shipped — when unsure, write around a detail
  rather than inventing it. There is NO self-serve password reset (route to
  support@whip.run). Deletion has a 28-day grace period; published apps survive deletion
  as "[deleted]".
- Don't document internal/unfinished features, admin tooling, or exact moderation
  thresholds. Don't promise timelines.
- Changelog (`changelog.mdx`): one `<Update>` per week, newest first, `label` like
  "Week of Jun 29, 2026", sections "### ✨ New & improved" and "### 🐛 Fixed",
  consumer language only — lead with user impact, never implementation.
- When renaming/moving a page, add a `redirects` entry in `docs.json` in the same change.

## SEO maintenance

- Once the custom domain is live (e.g. help.whip.run), set
  `"seo": { "metatags": { "canonical": "https://<domain>" } }` in `docs.json` — Mintlify
  appends each page's path automatically. Don't set it before the domain is final.
- Social/AI share cards use `/images/og-background.png` (via `thumbnails.background`) with
  the page title, description, and logo overlaid automatically — keep any replacement
  1200×630 and subtle enough for dark text.
- When screenshots are added, every image needs descriptive alt text (AI engines can't see
  images) and a descriptive filename; wrap screenshots in `<Frame caption="…">`.
- Don't add a custom `robots.txt` or `sitemap.xml` — Mintlify's defaults allow AI crawlers
  (GPTBot, ClaudeBot, PerplexityBot) via Content-Signal, and a custom file replaces that.
- `building/apis-and-libraries.mdx` mirrors two allowlists in the backend repo
  (brahma-backend `brahma/chakra/constants.py`: `WHITELISTED_DEPENDENCIES` and
  `NETWORK_FETCH_HOSTS_*`). When those change, update the page — and mention new
  sources/libraries in the changelog. Never list package version numbers on the page.
