---
name: stakeholder-translator
description: 'Generate 5 audience-tailored communications from one product update. Use when: stakeholder update, executive summary, board narrative, customer changelog, sales enablement, translate for audience, multi-audience communication, sensitivity classification.'
---

# Stakeholder Translator

Transform a single product update into five audience-tailored communications — each with the right tone, detail level, technical depth, and framing. Includes sensitivity classification so you know what's shareable.

## Output
Save to `outputs/stakeholder-[topic]-[YYYY-MM-DD].md`

## When to Use
- Writing a product update that needs to reach multiple audiences
- Preparing exec summaries alongside engineering updates
- Creating board narratives from sprint outcomes
- Generating customer changelogs without leaking internal details
- Arming sales with talk tracks and objection handling

## What You'll Get

Five distinct communications from one input:

| Output | Audience | Framing |
|--------|----------|---------|
| **Engineering Update** | Dev team | Technical decisions, code references, debt trade-offs |
| **Executive Summary** | Leadership | Business impact, metrics, decisions needed |
| **Board Narrative** | Board of Directors | Strategic positioning, speaker notes |
| **Customer Changelog** | End users | Benefits-focused, no internal details |
| **Sales Enablement** | Sales team | Objection handling, competitive positioning, talk tracks |

Plus:
- **Sensitivity Classification** for each section (✅ Safe / ⚠️ Caution / 🔒 Internal Only)
- **Key Message Consistency Check** — ensures the core narrative is coherent across all five versions

## Process

### Step 1: Collect the Update
I'll ask for:
> "What's the product update? Paste your internal notes, sprint summary, or a rough description of what happened. Include any context about timeline, metrics impact, or decisions made."

### Step 2: Classify Sensitivity
Before generating anything, I'll classify each piece of information:
- **✅ Safe** — Can be shared with any audience including customers
- **⚠️ Caution** — OK for internal audiences, needs careful framing for external
- **🔒 Internal Only** — Engineering and leadership only, never external

### Step 3: Generate All Five Outputs
Each output follows audience-specific rules:
- **Engineering**: Include technical specifics, architecture decisions, known debt
- **Executive**: Lead with business impact, include metrics, end with decisions needed
- **Board**: Strategic framing, market context, forward-looking narrative with speaker notes
- **Customer**: Benefits only, no internals, action items for users
- **Sales**: Competitive angles, objection handling scripts, customer-facing talk tracks

### Step 4: Consistency Check
I'll verify the core message is consistent across all five versions — same facts, different framing.

## Demo Scenario: AI Feature Launch

**Input:**
> "We shipped the AI-powered search feature. It uses embeddings + hybrid search. Took 3 sprints instead of 2 because of infra issues. Early metrics show 40% improvement in search relevance. We cut the advanced filtering feature to hit the deadline. Competitor X launched something similar last week."

**Sample Engineering Output:**
```markdown
## Engineering Update: AI Search v1 Shipped 🚀

### What Shipped
- Hybrid search (BM25 + vector embeddings) using our new embedding pipeline
- New search index architecture — migrated from Elasticsearch to custom solution
- Search relevance improved 40% (measured by nDCG@10 on test queries)

### What We Cut
- Advanced filtering (date ranges, custom facets) — descoped to hit Q1 deadline
- Will pick up in next sprint as standalone work item

### Tech Debt Created
- Embedding pipeline runs synchronously — needs async job queue before scale
- No A/B testing framework for search yet — metrics are pre/post comparison only

### Timeline
- Originally scoped for 2 sprints, took 3 due to infra migration issues
- Root cause: staging environment parity — documented in retro
```

**Sample Customer Changelog:**
```markdown
## 🔍 Smarter Search is Here

Finding what you need just got a lot easier. Our new AI-powered search understands
what you mean, not just what you type.

### What's New
- **Smarter results** — Search now understands context and intent
- **40% more relevant results** in our testing

### Coming Soon
- Advanced filters for date ranges and custom categories

Try it now → [Search anything]
```

## Tips
1. **More context = better output** — Include metrics, decisions, trade-offs, and timeline
2. **Flag sensitive items** — If something is strictly confidential, tell me upfront
3. **Specify urgency** — Is this a routine update or a crisis communication?
