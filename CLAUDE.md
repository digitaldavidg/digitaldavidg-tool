# CLAUDE.md — digitaldavidg-tool

Session briefing for future Claude Code sessions. Load this first.

---

## What this project is

`digitaldavidg.com` is a **static HTML site** deployed on Vercel. The root
homepage (`/index.html`) exists as part of the live site and is owned by the
user — **never modify it**. This repo adds a new **interactive knowledge
graph tool** and an educational content hub alongside the existing home.

The tool lets a user describe a domain (e.g. "SEO", "AI search",
"schema markup"), generates a visual entity-relationship graph, then lets
the user select entities to produce new content angles from the
intersections.

**Author entity:** David Garcia / Digital David G — SEO engineer at Kaiser
Permanente, AI/SEO consultant, SaaS builder. Every page must assert him as
the author via schema (Person + Article on /learn/, Person anchor on /about/)
and sameAs links. This is an E-E-A-T requirement, not a nice-to-have.

**Differentiator:** no other tool visualizes the *relationship types* between
SEO entities. This is a thinking tool, not a keyword tool.

## Canonical source docs (in repo root)

- `SYSTEM_PROMPT.md` — the tool's core generation rules, graph JSON schema,
  topic angle rules, and prohibited behaviors.
- `RELATIONSHIP_TYPES.md` — the 10-type relationship taxonomy (the
  intellectual core of the topic combinator).
- `digitaldavidg_site_strategy.md` — site architecture, URL plan, keyword
  targets by tier, on-page SEO requirements, sprint plan.

When in doubt on scope, precedence is: strategy doc > system prompt >
relationship types > this file.

## Tech stack

- **Static HTML** + CSS (no framework). Vercel serves files as-is.
- One shared stylesheet at `/assets/css/site.css` for new pages.
- Each URL is a directory with an `index.html` (so `/learn/` → `/learn/index.html`).
- **Do not touch the existing `/index.html`** at the repo root. Match its
  visual style when building out new pages; never overwrite it.

## Site structure (scaffolded in Sprint 0)

```
/                               # Existing homepage — DO NOT TOUCH
/assets/css/site.css            # Shared styles for new pages (placeholder)
/learn/index.html               # Learning hub (links to 5 pillars)
/learn/knowledge-graphs/index.html
/learn/eeat/index.html
/learn/ai-search/index.html
/learn/schema/index.html
/learn/entity-seo/index.html
/tool/index.html                # Tool landing page
/about/index.html               # David Garcia entity anchor page
```

Future routes per the strategy doc:

- `/tool/[domain]/` — pre-generated graphs (seo, ai-search, content-strategy,
  schema, eeat, geo, entity-seo)
- `/tool/explore/` — open-ended input
- `/learn/[topic-slug]/` — cluster pages from tool intersections
- `/case-studies/`

URL rules: lowercase, hyphenated, ≤4 words, no dates, trailing slash on
canonicals.

## Page template (every new page)

- `<title>` ≤60 chars, primary keyword + brand
- `<meta description>` ≤155 chars, direct answer + value prop
- `<link rel="canonical">` pointing to absolute URL with trailing slash
- OG tags (type, url, title, description, site_name)
- `<link rel="stylesheet" href="/assets/css/site.css">`
- JSON-LD: BreadcrumbList + (Article | WebPage | SoftwareApplication)
- Person + Organization JSON-LD on `/about/` (the canonical entity anchors
  referenced by @id from every other page's Article schema)
- Consistent `<header class="site-header">` with brand + nav (Tool / Learn /
  About) and `<footer class="site-footer">`
- Visible `<h1>` matching the page's primary keyword
- Breadcrumbs nav at the top of `<main>`

Cross-document @id refs used across pages:

- `https://digitaldavidg.com/#organization` → Organization (defined on /about/)
- `https://digitaldavidg.com/#person` → David Garcia (defined on /about/)
- `https://digitaldavidg.com/#website` → WebSite (to be defined once)

## User mode system (tech / novice) — for future sprints

Every /learn/ page and the tool itself must ask once:

> How do you want this explained?
> [ Technical breakdown ] [ Plain-English version ]

- Persist to `localStorage` as `userMode: "tech" | "novice"`
- Override in footer ("Switch to [other] mode")
- Render **both** variants in HTML for SEO indexability; toggle with CSS/JS
  **after** JS loads (prevents CLS — don't `display:none` the active variant
  pre-hydration)
- Track per-variant engagement (time, scroll, CTR) to flag underperformers

**Tech mode:** precise terminology (entity, ontology, RAG, schema, vector
space, E-E-A-T). Flesch 12–16 acceptable.

**Novice mode:** plain-English + analogies + business outcomes. Target
grade 8–10, sentences ≤20 words, no undefined jargon.

## Relationship type taxonomy (10 types)

Every edge in a generated graph references exactly one of these. Each drives
a different topic-angle format (see RELATIONSHIP_TYPES.md for the full
matrix).

| # | Type | One-line meaning | Primary angle format |
|---|---|---|---|
| 1 | Causal | A directly causes/produces B | How-to / Process |
| 2 | Compositional | A is a component/subset of B | Guide / Breakdown |
| 3 | Enabling | A makes B possible or much stronger (not sufficient) | Strategy |
| 4 | Competitive | A and B solve the same problem differently | Comparison |
| 5 | Temporal | A precedes B in a sequence or evolution | Evolution piece |
| 6 | Amplifying | A multiplies B's signal strength | Optimization guide |
| 7 | Constraining | A gates/limits B | Requirements checklist |
| 8 | Analogous | A and B are the same idea in different domains | Explainer |
| 9 | Contradictory | Optimizing for A creates friction with B | Opinion / POV |
| 10 | Co-occurrence | A and B correlate; mechanism unclear | Research / data piece |

Strength: 3 = strong/documented (solid edge), 2 = moderate (reduced opacity),
1 = weak/emerging (dashed edge). Co-occurrence edges are always dashed.

Never present a topic angle without a mapped relationship type. If no type
fits, use `co-occurrence` and flag it unverified.

## SEO requirements (every new page)

- Title + meta description as above
- Canonical URL set
- OG tags (title, description, url, type, site_name)
- Article + Author schema on /learn/ pages (author refs `#person` @id)
- SoftwareApplication schema on /tool/ pages
- BreadcrumbList on every page
- FAQPage schema on /learn/ pages with FAQ sections (future)
- First 50 words = direct answer to the page's question (featured snippet)
- ≥2 contextual internal links to other /learn/ pages (when content lands)
- CTA to /tool/ using entity-named anchor text (never "click here")

## Core Web Vitals targets

- LCP ≤2.5s — lazy-load graph JS; render text first
- CLS ≤0.1 — reserve space for graph container before JS loads
- INP ≤200ms — debounce graph interactions, use rAF

## Sprint cadence

Rule: **one file per sprint, ship it, move on.**

- Sprint 0 (done): scaffold new section (learn hub, 5 pillars, tool landing,
  about) + shared CSS + this CLAUDE.md
- Sprint 1: flesh out `/about/` (full bio + sameAs) and `/learn/eeat/` (tech
  + novice variants + FAQ + internal links) + user mode toggle JS
- Sprint 2: build the knowledge graph viz as a standalone JS module and wire
  it into `/tool/` with 3 pre-built domain graphs
- Then: one pillar page or one tool graph per sprint

## Non-negotiables

1. **Never modify `/index.html` at the repo root** — it's the existing site.
2. David Garcia as the author entity on every new page (Person schema refs +
   sameAs set).
3. User mode confirmation before content renders (on applicable pages).
4. Both content variants in the HTML for SEO indexability.
5. Max 5 clusters / 20 nodes per graph view — split into overview + detail.
6. No edge without a relationship type from the taxonomy.
7. No hallucinated relationships — unclear gets `co-occurrence` + dashed edge.

## Deployment

- Vercel serves this repo as a static site.
- No build step currently — files are served as-is. If that changes, this
  doc must be updated.

## Branch

Work happens on `claude/build-nextjs-knowledge-graph-<suffix>` branches.
Never push to main without explicit permission.
