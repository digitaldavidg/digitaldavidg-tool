# digitaldavidg.com — Visual Intelligence Tool
# Site Strategy, Content Architecture & SEO Build Plan

---

## 1. Positioning

**What this is:** An interactive knowledge graph tool that helps marketers and business owners understand SEO, AI search, and content strategy by visualizing entity relationships — then generating content angles from the intersections.

**Who it's for:**
- Primary: SEO professionals and digital marketers (tech mode)
- Secondary: Business owners and non-technical founders (novice mode)
- Tertiary: AI/ML practitioners exploring search applications

**Differentiator:** No other tool visualizes the *relationship types* between SEO entities and uses them to generate targeted content angles. This is not another keyword tool. It's a thinking tool.

**David Garcia as the entity:** Every page asserts David Garcia (Digital David G) as the author entity — SEO engineer at Kaiser Permanente, AI/SEO consultant, SaaS builder. Author schema, Person schema, sameAs links to LinkedIn/GitHub/social. This is non-negotiable for E-E-A-T.

---

## 2. Site Structure & URL Architecture

```
digitaldavidg.com/
├── /                              # Homepage — tool entry point + brand anchor
├── /tool/                         # The interactive knowledge graph app
│   ├── /tool/[domain]/            # Pre-generated graphs (SEO, AI search, content strategy...)
│   └── /tool/explore/             # Open-ended user input
├── /learn/                        # SEO content hub — all educational content
│   ├── /learn/knowledge-graphs/   # Pillar: what knowledge graphs are
│   ├── /learn/eeat/               # Pillar: E-E-A-T explained
│   ├── /learn/ai-search/          # Pillar: AI search + GEO
│   ├── /learn/schema/             # Pillar: Schema markup
│   ├── /learn/entity-seo/         # Pillar: Entity SEO fundamentals
│   └── /learn/[topic-slug]/       # Cluster pages generated from tool intersections
├── /for-marketers/                # Audience-specific landing page (tech mode)
├── /for-business-owners/          # Audience-specific landing page (novice mode)
├── /about/                        # Entity anchor page for David Garcia
├── /case-studies/                 # Proof layer: real results
└── /api/                          # (future) Public API for the graph engine
```

### URL Principles
- All slugs lowercase, hyphenated, max 4 words
- No dates in URLs (content is evergreen-first)
- Topic cluster pages live under `/learn/` regardless of when generated
- Tool pages are functional (`/tool/`), not editorial

---

## 3. Keyword Research — Target Clusters

### Tier 1 — High intent, moderate competition (build first)

| Head Term | Monthly Vol (est.) | Intent | Target Page |
|---|---|---|---|
| knowledge graph SEO | 2,400 | Informational | /learn/knowledge-graphs/ |
| entity SEO | 1,900 | Informational | /learn/entity-seo/ |
| E-E-A-T explained | 3,600 | Informational | /learn/eeat/ |
| AI search optimization | 1,300 | Commercial | /learn/ai-search/ |
| schema markup for SEO | 4,400 | Informational | /learn/schema/ |
| GEO generative engine optimization | 880 | Informational | /learn/ai-search/ |

### Tier 2 — Long-tail, high relevance (fill in Q2+)

| Long-tail Query | Intent | Target Page |
|---|---|---|
| how AI Overviews select sources | Informational | /learn/ai-search/how-ai-overviews-select-sources/ |
| E-E-A-T trustworthiness signals | Informational | /learn/eeat/trustworthiness/ |
| schema markup for authors | How-to | /learn/schema/author-schema/ |
| entity disambiguation SEO | Informational | /learn/entity-seo/disambiguation/ |
| knowledge graph vs keyword SEO | Comparison | /learn/knowledge-graphs/vs-keyword-seo/ |
| how to appear in AI Overviews | How-to | /learn/ai-search/appear-in-ai-overviews/ |
| topical authority building | Informational | /learn/entity-seo/topical-authority/ |
| person schema E-E-A-T | How-to | /learn/schema/person-schema-eeat/ |
| what is GEO SEO | Informational | /learn/ai-search/geo-vs-seo/ |
| sameAs schema Knowledge Graph | How-to | /learn/schema/sameas-knowledge-graph/ |

### Tier 3 — Tool-specific queries (build after tool is indexed)

| Query | Target |
|---|---|
| SEO knowledge graph tool | /tool/ |
| visualize SEO entities | /tool/ |
| SEO entity relationship map | /tool/ |
| content gap finder SEO | /tool/ |
| AI search topic generator | /tool/ |

---

## 4. On-Page SEO Requirements (Every Page)

### Required tags and attributes

```html
<!-- Title: primary keyword + brand, ≤60 chars -->
<title>E-E-A-T Explained: The Trust Framework for AI Search | Digital David G</title>

<!-- Meta description: direct answer + value prop, ≤155 chars -->
<meta name="description" content="E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness) is Google's quality framework for AI search. Learn how each component works and how to demonstrate them.">

<!-- Canonical -->
<link rel="canonical" href="https://digitaldavidg.com/learn/eeat/">

<!-- Open Graph -->
<meta property="og:title" content="E-E-A-T Explained: The Trust Framework for AI Search">
<meta property="og:description" content="...">
<meta property="og:image" content="https://digitaldavidg.com/og/eeat.png">
<meta property="og:type" content="article">

<!-- Schema: Article + Author -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "E-E-A-T Explained: The Trust Framework for AI Search",
  "author": {
    "@type": "Person",
    "name": "David Garcia",
    "url": "https://digitaldavidg.com/about/",
    "sameAs": [
      "https://www.linkedin.com/in/digitaldavidg",
      "https://twitter.com/digitaldavidg"
    ]
  },
  "publisher": {
    "@type": "Organization",
    "name": "Digital David G",
    "url": "https://digitaldavidg.com",
    "logo": "https://digitaldavidg.com/logo.png"
  },
  "datePublished": "2025-01-01",
  "dateModified": "2026-04-21"
}
</script>
```

### Content structure (every /learn/ page)

```
H1: [Primary keyword phrase — matches search intent exactly]
  → First 50 words: direct answer to the question (featured snippet target)

H2: [What is X] — definition, 100–150 words
H2: [Why X matters for AI search] — relevance layer
H2: [How X works] — mechanism explanation
  H3: [Component 1]
  H3: [Component 2]
H2: [How to implement / demonstrate X] — actionable layer
H2: [X and its relationship to Y] — entity connection (drives internal links)
H2: [Common mistakes with X] — differentiation layer
H2: [FAQ] — long-tail keyword capture, featured snippet bait
```

### Internal linking rules
- Every /learn/ page links to at least 2 other /learn/ pages via contextual anchor text
- Every /learn/ page links to the /tool/ with a CTA: "See how [topic] entities connect in the graph →"
- The homepage links to all 5 pillar pages
- Pillar pages link to all their cluster pages
- Never use "click here" as anchor text — always use entity names

---

## 5. User Mode System (Tech / Novice)

### How it works on the page

On every /learn/ page and in the tool, show a single question at the top before any content renders:

```
─────────────────────────────────────────
  Quick question before we start:
  How do you want this explained?

  [ I want the full technical breakdown ]
  [ Give me the plain-English version ]
─────────────────────────────────────────
```

Store the selection in `localStorage` as `userMode: "tech" | "novice"`. Persist across pages. Allow override in the footer ("Switch to [other] mode").

### Content variant system

Every page maintains two content layers:
- `.content-tech` — visible by default in tech mode
- `.content-novice` — visible by default in novice mode

Both layers are in the HTML (for SEO indexability). Toggle visibility with CSS + JS. Do not use `display: none` on the initial render for the active mode — use it only after JS loads to prevent CLS.

### Self-optimization logic

Track per variant:
- Time on page
- Scroll depth
- Click-through to related pages or tool
- Return visits

After 50 sessions per variant per page, compare engagement scores. If one variant consistently underperforms (>20% lower scroll depth), surface a flag in the CMS for content revision. This is not fully automated content rewriting — it's a signal system that tells David where to focus manual improvement.

Store signals in a lightweight JSON endpoint or Supabase table:
```json
{
  "page": "/learn/eeat/",
  "mode": "novice",
  "sessions": 73,
  "avg_scroll_depth": 0.42,
  "avg_time_on_page": 94,
  "ctr_to_tool": 0.11,
  "flag_for_review": true
}
```

---

## 6. Pre-Built Tool Graphs (Launch with These)

These domains get pre-generated graphs at `/tool/[domain]/` for immediate indexability and SEO value:

| Domain | URL | Primary keyword |
|---|---|---|
| SEO | /tool/seo/ | SEO knowledge graph |
| AI Search | /tool/ai-search/ | AI search entity map |
| Content Strategy | /tool/content-strategy/ | content strategy entities |
| Schema Markup | /tool/schema/ | schema markup relationships |
| E-E-A-T | /tool/eeat/ | E-E-A-T framework visualization |
| Generative Engine Optimization | /tool/geo/ | GEO entities and relationships |
| Entity SEO | /tool/entity-seo/ | entity SEO knowledge graph |

Each `/tool/[domain]/` page includes:
- The interactive graph (JS-rendered)
- A server-side rendered text summary of the key entities and relationships (for SEO crawlability)
- Schema: `SoftwareApplication` + `WebPage` + `BreadcrumbList`
- CTA to `/tool/explore/` for custom domains

---

## 7. Technical SEO Requirements

### Core Web Vitals targets
- LCP: ≤2.5s — lazy-load graph JS; render text content first
- CLS: ≤0.1 — reserve space for graph container before JS loads
- INP: ≤200ms — debounce graph interactions; use requestAnimationFrame for redraws

### Crawlability
- Server-side render all entity names, relationship labels, and topic angles as visible text (not just in SVG or canvas)
- Include a `<noscript>` fallback that renders a static version of the graph as an HTML list
- sitemap.xml: include all /learn/ and /tool/[domain]/ pages, exclude /tool/explore/
- robots.txt: allow all except /api/ and any auth routes

### Page speed
- Graph library (D3 or custom SVG): load async, defer until viewport intersection
- Google Fonts: self-host or use `font-display: swap`
- Images: WebP with explicit width/height attributes
- No render-blocking JS in <head>

### Schema hierarchy (site-wide)
```
Organization (homepage)
  └── Person: David Garcia (about page, sameAs all profiles)
      └── Article (every /learn/ page)
          └── BreadcrumbList (every page)
SoftwareApplication (tool pages)
FAQPage (every /learn/ page that includes FAQ section)
```

---

## 8. Content Roadmap

### Phase 1 — Foundation (Month 1–2)
Build the 5 pillar pages and the tool homepage. Get these indexed and generating internal links before building cluster pages.

1. `/learn/knowledge-graphs/` — What is a knowledge graph (SEO context)
2. `/learn/eeat/` — E-E-A-T explained top-to-bottom
3. `/learn/ai-search/` — AI search, GEO, and what changed
4. `/learn/schema/` — Schema markup for SEO practitioners
5. `/learn/entity-seo/` — Entity SEO fundamentals
6. `/tool/` — Tool landing page with 7 pre-built domains
7. `/about/` — David Garcia entity anchor page

### Phase 2 — Cluster Build (Month 3–4)
Generate 3–4 cluster pages per pillar from tool intersections. Prioritize intersection pages that cover multiple Tier 1 keywords.

Priority intersections:
- E-E-A-T + Schema → `/learn/eeat/schema-signals/`
- E-E-A-T + AI Search → `/learn/eeat/ai-search-trustworthiness/`
- Schema + AI Search → `/learn/schema/ai-search-structured-data/`
- Entity SEO + Knowledge Graph → `/learn/entity-seo/knowledge-graph-optimization/`
- GEO + E-E-A-T → `/learn/ai-search/geo-eeat-strategy/`

### Phase 3 — Authority Build (Month 5–6)
- Case studies showing real client results from entity SEO + schema work
- Original data: run the tool on 10 industries, publish the graphs as standalone assets
- Guest post / digital PR targeting links from SEO publications (Search Engine Land, Search Engine Journal, Moz Blog)
- David Garcia entity signals: podcast appearances, LinkedIn articles, conference talks citing digitaldavidg.com

### Phase 4 — Tool Expansion (Month 7+)
- User accounts: save custom graphs
- Export to JSON/PNG
- API access for agencies
- GEO-optimized content: structured for AI Overview citation (direct answers, verified citations, author schema on every page)

---

## 9. How to Work on This

Here is the honest recommendation, given your constraints (ADHD, ADHD, limited time blocks, parallel commitments):

### Use Claude Code — not this chat, not Cowork

**Why not this chat:**
This conversation window will expire. You can't version control what we build here. Every session starts fresh unless you paste context back in. For a multi-phase project with dozens of files, that's a constant tax on your initiation energy. You'll lose momentum at the worst times.

**Why not Cowork:**
Cowork is good for file management and task automation. It's not built for the kind of iterative code+content generation this project needs. You'd be fighting the tool instead of using it.

**Why Claude Code:**
- Persistent project context — it reads your files, not your memory
- You can commit `SYSTEM_PROMPT.md`, `RELATIONSHIP_TYPES.md`, and this strategy doc to a repo and Claude Code works from them directly
- Build incrementally in focused 30–60 minute sprints: one page, one component, one schema block at a time
- When you lose thread (and you will, that's not a character flaw, it's ADHD), `git status` and the files themselves restore context instantly
- The deliverable (a real website with real code) builds up in a repo you own

### Recommended sprint structure

**Sprint 0 (this week, 1 hour):**
- Create `digitaldavidg-tool` repo
- Commit `SYSTEM_PROMPT.md`, `RELATIONSHIP_TYPES.md`, this strategy doc
- Set up project scaffold (Next.js or Astro recommended for static + dynamic balance)
- Deploy blank shell to Vercel with domain pointed

**Sprint 1 (next week, 2–3 hours):**
- Build `/about/` with full schema
- Build `/learn/eeat/` pillar page (tech + novice variants)
- Wire up user mode toggle (localStorage, CSS classes)

**Sprint 2 (week after, 2–3 hours):**
- Port the knowledge graph visualization from this chat into a reusable React component
- Build `/tool/` landing page with 3 pre-built domains

**Then repeat** — one pillar page or one tool graph per sprint.

### The rule that keeps this alive given how your brain works:
**One file per sprint. Ship it. Move on.**
Not one feature. Not one phase. One file that goes from zero to deployed. The accumulation is the strategy.
