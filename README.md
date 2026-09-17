# Groww Reviews Analyser — Vercel edition (free, no API key)

A fully client-side rebuild of the weekly app-review pulse tool. Theme
classification, note generation, and email drafting are all done with plain
JavaScript rule/template logic in the browser — no Anthropic API key, no
backend, no billing, ever.

## Structure
```
index.html   the whole app — UI, CSV parsing, theme keyword-matching,
             note generation, and email drafting, all client-side
```

## What changed vs. the AI version
- Themes are picked by count + negative-review weight (already-existing
  keyword classifier), not an LLM judgment call.
- The note's summary lines and action ideas are filled in from templates
  per theme, not freshly written prose.
- The email draft is assembled from the same template, not AI-composed.
- Nothing calls out to any API — it all runs in the visitor's browser.

## Deploy
No environment variables, no serverless functions, no signup needed beyond
a Vercel account.

1. Push this folder to a GitHub repo (or use the Vercel CLI — see below).
2. In Vercel: **New Project > Import** your repo.
3. Leave build settings as default (static site, no build command needed).
4. Deploy. Done — the URL works immediately, for anyone, at no cost.

### Or deploy via CLI without GitHub
```bash
npm i -g vercel
cd groww-reviews-analyser
vercel          # follow prompts
vercel --prod   # promote to production
```
