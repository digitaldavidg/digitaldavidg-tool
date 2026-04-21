# RELATIONSHIP_TYPES.md
# Entity Relationship Taxonomy — Visual Intelligence Tool

## Purpose

This file defines every valid relationship type between entities in a knowledge graph. Relationship types are the intellectual core of the topic combinator — they determine *what kind* of content angle is generated when two entities are combined. A relationship is never decoration; it drives the question: "What does the connection between A and B actually mean for someone trying to do something?"

Every edge in a generated graph must reference exactly one relationship type from this taxonomy. If no type fits cleanly, use `co-occurrence` and flag it for review.

---

## Taxonomy

### 1. CAUSAL
**Definition:** Entity A directly causes, produces, or triggers Entity B. Remove A and B weakens or disappears.

**Tech framing:** A → B with directional dependency. B cannot exist at full strength without A as an input.

**Novice framing:** A is the reason B happens. If you want B, you need to work on A first.

**Examples in SEO/AI search:**
- Schema markup → Entity disambiguation (schema causes cleaner disambiguation)
- E-E-A-T signals → AI citation probability (trust signals cause citation selection)
- Content freshness → Featured snippet eligibility

**Topic angle trigger:** "How [A] drives [B]" / "Why [B] requires [A]" / "The [A] factor in [B]"

---

### 2. COMPOSITIONAL
**Definition:** Entity A is a component or subset of Entity B. A lives inside B structurally.

**Tech framing:** A is a proper subset of B. B is the container; A is one of its constituent parts.

**Novice framing:** A is one piece of the bigger puzzle called B.

**Examples in SEO/AI search:**
- Author schema ⊂ E-E-A-T signals (author schema is one component of E-E-A-T)
- Trustworthiness ⊂ E-E-A-T (trustworthiness is a component of the framework)
- LLM re-ranking ⊂ AI Overview pipeline

**Topic angle trigger:** "The [A] component of [B]" / "How [A] fits into [B]" / "Understanding [A] as part of [B]"

---

### 3. ENABLING
**Definition:** Entity A makes Entity B possible or significantly more effective, but does not directly cause it. A is a prerequisite or amplifier.

**Tech framing:** A is a necessary but not sufficient condition for B. B can exist weakly without A, but A dramatically increases B's probability or magnitude.

**Novice framing:** A doesn't guarantee B, but without A, B is much harder to achieve.

**Examples in SEO/AI search:**
- Topical authority → AI Overview citation (authority enables citation but doesn't guarantee it)
- Structured data → Knowledge Graph inclusion
- Author credentials → E-E-A-T trust signals

**Topic angle trigger:** "How [A] enables [B]" / "Why [A] is the foundation of [B]" / "Building [B] through [A]"

---

### 4. COMPETITIVE
**Definition:** Entities A and B address the same user need or occupy the same conceptual space, but through different mechanisms. Gaining ground with A may reduce reliance on B.

**Tech framing:** A and B are substitutable or rival approaches within the same solution category.

**Novice framing:** A and B are two different ways to solve the same problem. You often have to choose, or at least prioritize.

**Examples in SEO/AI search:**
- Traditional SEO vs. GEO (Generative Engine Optimization)
- Keyword targeting vs. entity targeting
- Backlink building vs. brand mention building

**Topic angle trigger:** "[A] vs. [B]: which matters more in [context]" / "When to use [A] instead of [B]" / "The tradeoffs between [A] and [B]"

---

### 5. TEMPORAL
**Definition:** Entity A precedes Entity B in a process, workflow, or evolutionary sequence. A comes before B; B builds on or replaces A.

**Tech framing:** A and B exist in an ordered sequence. B depends on A having occurred first, or B is the evolved form of A.

**Novice framing:** A comes first, then B. You can't skip A to get to B.

**Examples in SEO/AI search:**
- Keyword SEO → Entity SEO (temporal evolution)
- Content creation → Schema markup → Entity recognition (workflow sequence)
- Search indexing → E-E-A-T filtering → LLM re-ranking (pipeline sequence)

**Topic angle trigger:** "From [A] to [B]: the evolution of [domain]" / "Why [B] replaced [A]" / "The [A] → [B] workflow"

---

### 6. AMPLIFYING
**Definition:** Entity A makes Entity B stronger, more visible, or more effective without changing what B fundamentally is. A is a multiplier.

**Tech framing:** A increases the signal strength of B. The effect is multiplicative rather than additive.

**Novice framing:** A turns up the volume on B. B still works without A, but A makes it much louder.

**Examples in SEO/AI search:**
- Schema markup amplifies E-E-A-T signals (schema makes existing trust signals machine-readable)
- External citations amplify topical authority
- Content clusters amplify individual page authority

**Topic angle trigger:** "How [A] amplifies [B]" / "Using [A] to strengthen [B]" / "The multiplier effect of [A] on [B]"

---

### 7. CONSTRAINING
**Definition:** Entity A limits, gates, or defines the boundaries of Entity B. Without satisfying A's requirements, B cannot fully function.

**Tech framing:** A is a gate condition for B. B operates within the constraints A establishes.

**Novice framing:** A sets the rules that B has to follow. If you don't meet A's requirements, B won't work for you.

**Examples in SEO/AI search:**
- E-E-A-T filter constrains AI Overview eligibility (must pass trust gate to be considered)
- YMYL classification constrains content quality requirements
- Domain authority constrains citation probability in AI search

**Topic angle trigger:** "How [A] limits [B]" / "The [A] requirements for [B]" / "Why [B] fails without [A]"

---

### 8. ANALOGOUS
**Definition:** Entity A and Entity B serve parallel functions in different contexts or systems. Understanding one deeply illuminates the other.

**Tech framing:** A and B are structurally isomorphic — they solve the same class of problem using similar mechanisms in different domains.

**Novice framing:** A and B are basically the same idea applied in two different places. If you get one, you get the other.

**Examples in SEO/AI search:**
- PageRank ≈ Citation frequency in AI search (both measure authority through reference counting)
- Schema markup ≈ Structured resume (both translate identity into machine-readable form)
- Knowledge Graph ≈ Long-term memory for search engines

**Topic angle trigger:** "Why [A] is the [B] of [domain]" / "[A] and [B]: the same idea in different clothes" / "The [A] analogy that explains [B]"

---

### 9. CONTRADICTORY
**Definition:** Entity A and Entity B are in genuine tension. Optimizing fully for A creates friction with B, and vice versa. Both are valid; the relationship is a managed tradeoff.

**Tech framing:** A and B occupy opposing positions on a spectrum or create conflicting optimization pressures within the same system.

**Novice framing:** A and B pull in different directions. Getting more of one usually means getting less of the other — at least in the short term.

**Examples in SEO/AI search:**
- Content velocity vs. content depth (publishing more vs. publishing better)
- AI content efficiency vs. E-E-A-T experience signals
- Zero-click visibility vs. traffic volume

**Topic angle trigger:** "The [A] vs. [B] tradeoff in [domain]" / "Why more [A] can hurt your [B]" / "Balancing [A] and [B]"

---

### 10. CO-OCCURRENCE
**Definition:** Entity A and Entity B appear together frequently in the same context, but the nature of their relationship is not yet clearly defined. The connection is real but the mechanism is unclear or debated.

**Tech framing:** A and B are statistically correlated within the domain corpus, but causality direction or dependency type is unestablished.

**Novice framing:** A and B tend to show up together, but it's not yet clear why — or which one drives the other.

**Examples in SEO/AI search:**
- High domain authority and AI Overview citation (correlated, not necessarily causal)
- Long content and featured snippet eligibility (observed pattern, mechanism debated)

**Topic angle trigger:** "The [A]-[B] correlation: what it means and what it doesn't" / "Do you need [A] to get [B]?" / "The relationship between [A] and [B]: what we know so far"

**Flag for review:** Always mark co-occurrence relationships in the graph with a dashed edge and a visual indicator. These are hypotheses, not facts.

---

## Relationship Strength Scale

Every edge carries a strength rating from 1–3:

| Strength | Meaning | Visual |
|---|---|---|
| 3 — Strong | Direct, well-documented, high-confidence relationship | Solid edge, full opacity |
| 2 — Moderate | Indirect or context-dependent relationship | Solid edge, reduced opacity |
| 1 — Weak / Emerging | Hypothesized, early evidence, or debated | Dashed edge |

---

## Topic Angle Generation Matrix

When two entities are selected, cross-reference their relationship type against this matrix to determine which topic angle formats to generate:

| Relationship Type | Primary Format | Secondary Format |
|---|---|---|
| Causal | How-to / Process | Explanation |
| Compositional | Guide / Breakdown | Definition |
| Enabling | Strategy | Foundation guide |
| Competitive | Comparison | Decision guide |
| Temporal | Evolution piece | Migration guide |
| Amplifying | Optimization guide | Case study angle |
| Constraining | Requirements checklist | Troubleshooting |
| Analogous | Explainer | Mental model piece |
| Contradictory | Opinion / POV | Framework piece |
| Co-occurrence | Research/data piece | Question-framing piece |

---

## Adding New Relationship Types

When a relationship between two entities doesn't fit any type above:
1. Document the pair and context
2. Describe the mechanism in plain English
3. Identify the closest existing type and note the deviation
4. If 3+ instances exist with the same deviation pattern, propose a new type

New types require: a definition, tech framing, novice framing, 3 examples, and a topic angle trigger.
