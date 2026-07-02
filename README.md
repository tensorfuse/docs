# Whip Help Center

Consumer docs, FAQ, and changelog for [Whip](https://whip.run) — the app where you describe
an idea in plain words and AI builds it into a real mini app.

Built with [Mintlify](https://mintlify.com). Content lives in MDX files; site config in
`docs.json`. Writing rules for contributors (and AI agents) are in `AGENTS.md`.

## Local development

```bash
npm i -g mint   # once
mint dev        # preview at http://localhost:3000
```

`mint broken-links` checks internal links before you push.

## Structure

- `index.mdx` — landing page ("What is Whip?")
- `getting-started/ building/ sharing/ discover/ social/ using/ account/ help/` — Help Center groups
- `faq/` — FAQ tab (general, creating apps, privacy & safety)
- `changelog.mdx` — weekly "What's new in Whip" (`<Update>` timeline)

Deploys via the Mintlify GitHub app on push to the default branch.
