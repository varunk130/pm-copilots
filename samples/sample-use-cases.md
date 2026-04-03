# Sample Use Cases: PM Copilots
## Hypothetical Scenarios for Each Agent

> **NOTE:** All data in this document is entirely synthetic and mock-generated for demonstration purposes. Company names, person names, financial figures, and all agent outputs are fictional. No real customer data, proprietary information, or actual business metrics were used.

**Prepared by:** PM Copilots | **Date:** April 2026 | **Status:** Reference Document

---

## Overview

These use cases demonstrate how each of the three PM Copilot agents handles real-world product management scenarios. Each example shows the **input** a PM would provide and the **output** the agent produces, illustrating the structured reasoning each agent applies.

| # | Use Case | Agent | Scenario |
|---|----------|-------|----------|
| 1 | AI Feature Launch Communication | Stakeholder Translator | Translating a major product launch for 5 audiences |
| 2 | Missed Deadline Escalation | Stakeholder Translator | Communicating a critical delay without creating panic |
| 3 | Quarterly Feature Prioritization | Decision Engine | Choosing between 3 competing initiatives |
| 4 | Build vs. Buy Decision | Decision Engine | Evaluating whether to build an internal tool or buy a vendor solution |
| 5 | Feature ROI Business Case | Financial Analyst | Justifying investment in a new product capability |
| 6 | Pricing Model Change Analysis | Financial Analyst | Modeling the impact of shifting from seat-based to usage-based pricing |

---

## Use Case 1: AI Feature Launch Communication

### Agent: Stakeholder Translator

### Input

Person A (Senior PM at Company A, a $120M ARR enterprise SaaS platform) provides the following raw update:

> "We're launching AI-powered smart suggestions in our workflow builder next Tuesday. It uses a fine-tuned LLM to recommend next steps based on historical workflow patterns. We had to cut the multi-language support to hit the date — that'll come in v2 next quarter. Performance benchmarks show 340ms p95 latency which is within our SLA. Early beta users saw 23% reduction in workflow creation time. We're gating it to Enterprise tier only at launch. There's a known edge case with recursive workflows that we've documented but not fixed — engineering estimates 2 sprints to resolve. Company B (our biggest competitor) shipped something similar last month but it's template-based, not pattern-learned."

### Sensitivity Classification

| Information | Classification | Rationale |
|---|---|---|
| Feature launch date and capabilities | Safe | Public knowledge post-launch |
| 23% reduction in workflow creation time | Safe | Positive metric, shareable |
| Multi-language cut from v1 | Caution | Could concern international customers if framed poorly |
| 340ms p95 latency | Safe | Technical metric, within SLA |
| Enterprise tier gating | Safe | Pricing decision, publicly visible |
| Recursive workflow edge case | Internal Only | Known bug, competitive vulnerability |
| Company B competitive comparison | Caution | Sales-appropriate, not customer-facing |
| Engineering sprint estimate for bug fix | Internal Only | Internal roadmap detail |

### Agent Output (Abbreviated)

**Engineering Update:**
> Subject: Smart Suggestions shipping Tuesday — tech details and known issues
>
> We're deploying the fine-tuned LLM-based suggestion engine to production Tuesday. Key specs: 340ms p95 latency (within SLA), pattern-based recommendations from historical workflow data. Known issue: recursive workflow edge case — documented in JIRA-4521, estimated 2-sprint fix, slotted for next cycle. Multi-language tokenization deferred to v2 (Q3). No breaking API changes; existing workflow endpoints unchanged.

**Executive Summary:**
> Smart Suggestions launches Tuesday to Enterprise customers. Beta results: 23% faster workflow creation. Enterprise-only at launch to control rollout risk. Multi-language support follows in Q3. Competitive positioning: our approach (pattern-learned) is differentiated vs. Company B's template-based system.

**Board Narrative:**
> Our AI investment is producing measurable customer outcomes. Smart Suggestions — launching this week — reduced workflow creation time by 23% in beta, directly addressing our "time-to-value" strategic priority. We're launching to Enterprise tier first, with broader rollout in Q3 alongside multi-language support. This positions us ahead of Company B's recent template-based offering with a genuinely differentiated, data-driven approach.

**Customer Changelog:**
> **New: Smart Suggestions in Workflow Builder** — Your workflow builder now recommends next steps based on patterns from your team's most successful workflows. Beta customers created workflows 23% faster. Available now for Enterprise plans. Multi-language support coming soon.

**Sales Enablement:**
> **Talk track:** "Our Smart Suggestions don't just offer templates — they learn from your organization's actual workflow patterns. In beta, customers created workflows 23% faster. Unlike Company B's template approach, our system gets smarter the more your team uses it." **Objection handler:** If asked about multi-language → "Multi-language support is on the Q3 roadmap. Today's launch focuses on English workflows, which covers 85% of our Enterprise base."

---

## Use Case 2: Missed Deadline Escalation

### Agent: Stakeholder Translator

### Input

Person B (PM at Company C, a $45M ARR analytics platform) provides:

> "The real-time dashboard feature we committed to for April 15 is going to slip to May 6. Root cause: we underestimated the complexity of the streaming data pipeline — turns out our current architecture can't handle the concurrency requirements. Engineering needs to refactor the event processing layer. 3 enterprise customers (Company D, Company E, Company F) are waiting on this for their Q2 planning. The workaround is a 15-minute refresh interval instead of real-time. Person C (CTO) already knows. Person D (VP Sales) does not."

### Sensitivity Classification

| Information | Classification | Rationale |
|---|---|---|
| 3-week delay | Caution | Must communicate carefully to preserve trust |
| Architecture limitation root cause | Internal Only | Technical debt detail, not customer-relevant |
| Named customers waiting | Internal Only | Customer-specific deal details |
| Workaround availability | Safe | Constructive, shows proactive solution |
| Revised May 6 date | Caution | Only share if high confidence in new date |

### Agent Output (Abbreviated)

**Engineering Update:**
> Real-time dashboards delayed 3 weeks (April 15 → May 6). Root cause: event processing layer can't handle required concurrency under streaming load. Person E (Eng Lead) is refactoring the pipeline — estimated 2 sprints. This is architectural, not a bug fix, so no shortcuts. 15-minute refresh interval ships on original date as interim solution. No impact on other Q2 commitments.

**Executive Summary:**
> Real-time dashboards moving from April 15 to May 6. We're shipping a 15-minute refresh workaround on the original date to unblock customer workflows. Root cause was an architecture gap in our event pipeline — the fix is a proper refactor, not a patch. Three enterprise customers are affected; CS is preparing proactive outreach with the workaround plan. Person D (VP Sales) needs to be briefed before customer communication goes out.

**Customer Communication (for Company D, Company E, Company F):**
> We want to give you an early heads-up: the real-time dashboard capability we've been building will arrive on May 6, three weeks later than our original target. In the meantime, we're shipping an enhanced dashboard with 15-minute auto-refresh on April 15 — this covers most reporting use cases and will be available to your team on the original date. Your account team will schedule a walkthrough this week.

---

## Use Case 3: Quarterly Feature Prioritization

### Agent: Decision Engine

### Input

Person F (VP Product at Company G, a $200M ARR enterprise collaboration platform) needs to choose one initiative for Q3:

> **Option A: AI Meeting Summarizer** — Auto-generates meeting notes, action items, and follow-ups. High customer demand (top request in NPS for 3 quarters). Estimated 8 weeks to MVP. Revenue risk: none directly, but churn reduction estimated at 5-8%.
>
> **Option B: Enterprise Admin Console** — Centralized admin for permissions, audit logs, compliance reporting. Required by 4 enterprise prospects in active deals totaling $2.8M ARR. Estimated 10 weeks. Directly gates revenue.
>
> **Option C: API v3 with Webhooks** — Complete API overhaul enabling partner integrations. 12 partners waiting to build integrations. Estimated 12 weeks. Indirect revenue through ecosystem but no direct ARR.

### Agent Output

**Framework 1: Impact x Confidence Matrix**

| Option | Revenue Impact | Confidence | Weighted Score |
|---|---|---|---|
| AI Meeting Summarizer | Medium ($800K-$1.6M churn save) | Medium (65%) — churn reduction is estimated | 6.5 |
| Enterprise Admin Console | High ($2.8M gated pipeline) | High (85%) — deals are in active negotiation | 8.5 |
| API v3 with Webhooks | High ($3M+ ecosystem potential) | Low (40%) — partner revenue is speculative | 4.0 |

**Framework 2: Strategic Alignment**

| Criterion (Weight) | AI Summarizer | Admin Console | API v3 |
|---|---|---|---|
| Revenue growth (30%) | 6/10 | 9/10 | 5/10 |
| Retention impact (25%) | 9/10 | 4/10 | 3/10 |
| Competitive moat (20%) | 7/10 | 3/10 | 8/10 |
| Platform scalability (15%) | 4/10 | 5/10 | 9/10 |
| Time to value (10%) | 8/10 | 6/10 | 4/10 |
| **Weighted Total** | **6.85** | **5.70** | **5.65** |

**Framework 3: Second-Order Effects**

| Option | Positive 2nd-Order Effects | Negative 2nd-Order Effects |
|---|---|---|
| AI Summarizer | Increases daily engagement → higher expansion revenue; creates AI moat | Sets expectation for more AI features → resource pressure |
| Admin Console | Unblocks enterprise segment → larger deal sizes long-term | Feature parity play, not differentiation; doesn't improve retention |
| API v3 | Partner ecosystem becomes a growth engine; reduces custom integration requests | 12-week build delays other work; partner revenue timing is uncertain |

**Framework 4: Pre-Mortem Analysis**

> "It's December and the Q3 initiative failed. What went wrong?"

| Option | Failure Scenario | Probability |
|---|---|---|
| AI Summarizer | "Accuracy was below 80% and users stopped trusting it after first week. We shipped an AI feature that felt like a gimmick." | 25% |
| Admin Console | "We shipped it but the 4 deals closed anyway with manual workarounds — or churned for unrelated reasons. We solved a problem that wasn't the real blocker." | 20% |
| API v3 | "Partners built integrations but nobody marketed them. Ecosystem grew on paper but no user adoption." | 45% |

**Synthesized Recommendation:**

> **Ship Enterprise Admin Console (Option B) in Q3.**
>
> **Rationale:** Despite lower strategic alignment score, the Admin Console has the highest confidence-weighted revenue impact ($2.8M in gated pipeline at 85% confidence). The deals are in active negotiation — this is execution risk, not market risk. The AI Summarizer scored highest on strategic alignment but its revenue impact depends on a churn reduction estimate that hasn't been validated.
>
> **Sequence recommendation:** Admin Console in Q3 (capture the pipeline) → AI Summarizer in Q4 (highest customer demand, best retention impact) → API v3 in Q1 next year (after dedicated partner GTM plan is built).
>
> **Confidence:** 72% — high confidence in Admin Console revenue impact, moderate uncertainty on whether those deals would close anyway.

---

## Use Case 4: Build vs. Buy Decision

### Agent: Decision Engine

### Input

Person G (Director of Engineering at Company H, a $90M ARR fintech platform) needs to decide:

> "We need a feature flagging and experimentation platform. Options: (A) Build our own using open-source libraries — 6 engineers for 14 weeks, then ongoing maintenance. (B) Buy Company I's platform — $180K/year, 3-week integration, but limited customization for our fintech-specific compliance requirements. (C) Fork the open-source Company J project and customize — 3 engineers for 8 weeks, community maintenance for core, but we own the compliance layer."

### Agent Output (Abbreviated)

**Impact x Confidence Matrix**

| Option | 3-Year TCO | Confidence | Customization Fit |
|---|---|---|---|
| Build (A) | $1.4M (eng cost + maintenance) | Medium (60%) — scope creep risk | 10/10 |
| Buy (B) | $540K (license) + $120K (integration/workarounds) | High (85%) — known product | 5/10 |
| Fork + Customize (C) | $680K (eng cost) + community leverage | Medium (55%) — open-source dependency risk | 8/10 |

**Synthesized Recommendation:**

> **Buy Company I's platform (Option B) with a compliance adapter layer.**
>
> Build a thin compliance wrapper (2 engineers, 4 weeks) on top of Company I's platform to handle fintech-specific requirements. This captures 85% of Buy's speed and cost advantage while closing the customization gap from 5/10 to 7/10.
>
> **Why not Build:** At $90M ARR with a 6-engineer team, the opportunity cost of 14 weeks of build is too high — those engineers should be shipping customer-facing features. Feature flagging is not your competitive moat.
>
> **Why not Fork:** Open-source dependency risk in fintech is real. If the Company J community pivots direction or a critical security patch is delayed, you inherit the liability. At your scale, paying for a vendor's SLA is worth $180K/year.

---

## Use Case 5: Feature ROI Business Case

### Agent: Financial Analyst

### Input

Person H (PM at Company K, a $160M ARR HR tech platform) provides:

> "I want to build an AI-powered employee sentiment analysis feature. It would process survey data, Slack messages (anonymized), and performance review text to surface team health signals. Target: mid-market customers (200-2000 employees). I think we can charge $3/employee/month as an add-on. Our current customer base has about 1.2M employees across 800 accounts. Build estimate is 4 engineers for 16 weeks. I expect 15% attach rate in Year 1."

### Agent Output

**Assumptions Table**

| Assumption | Value | Source | Confidence |
|---|---|---|---|
| Addressable employee base | 1,200,000 | PM Input | High |
| Pricing per employee/month | $3.00 | PM Input | Medium |
| Year 1 attach rate | 15% | PM Input | Low |
| Year 2 attach rate | 28% | SaaS Benchmark (expansion) | Medium |
| Year 3 attach rate | 38% | SaaS Benchmark (maturity) | Medium |
| Build cost (4 engineers x 16 weeks) | $480,000 | Estimated ($150K/eng fully loaded) | Medium |
| Ongoing maintenance (2 engineers) | $300,000/year | Estimated | Medium |
| Gross margin | 78% | SaaS Benchmark (AI features) | Medium |
| Monthly churn on add-on | 1.8% | SaaS Benchmark (add-on products) | Medium |

**Key Metrics**

| Metric | Value | Status |
|---|---|---|
| Year 1 ARR (net of churn) | $4.9M | Strong |
| Year 3 ARR (net of churn) | $12.1M | Strong |
| Payback Period | 4.2 months | Excellent |
| 3-Year NPV (12% discount) | $18.7M | Strong |
| 3-Year ROI | 1,420% | Strong |
| Break-Even Attach Rate | 3.2% | Low bar — de-risks the bet |

**Sensitivity Matrix**

| | Attach 10% | Attach 15% (base) | Attach 20% |
|---|---|---|---|
| **$2/employee** | $2.1M Y1 ARR | $3.2M Y1 ARR | $4.3M Y1 ARR |
| **$3/employee (base)** | $3.2M Y1 ARR | **$4.9M Y1 ARR** | $6.5M Y1 ARR |
| **$4/employee** | $4.3M Y1 ARR | $6.5M Y1 ARR | $8.6M Y1 ARR |

**Crossover Analysis:**
> The feature becomes NPV-negative only if attach rate drops below 3.2% AND price drops below $1.50/employee — a scenario requiring catastrophic product-market fit failure. Even the worst-case modeled scenario ($2 price x 10% attach) generates $2.1M Y1 ARR against a $480K build cost.

**Recommendation:**

> **Ship.** The financial case is robust across all sensitivity scenarios. Break-even attach rate (3.2%) is well below the PM's conservative Year 1 estimate (15%). **De-risk by:** launching to top 50 accounts first with a 90-day pilot to validate the 15% attach rate assumption before scaling go-to-market spend.

---

## Use Case 6: Pricing Model Change Analysis

### Agent: Financial Analyst

### Input

Person I (VP of Product at Company L, a $75M ARR developer tools platform) asks:

> "We're considering shifting from seat-based pricing ($49/user/month) to usage-based pricing (per API call). Currently 4,200 paying customers, average 12 seats each. Usage data shows median customer makes 850K API calls/month but there's a long tail — top 10% of customers make 5M+ calls. I'm worried about revenue impact during the transition."

### Agent Output (Abbreviated)

**Current State Model**

| Metric | Value |
|---|---|
| Current ARR | $29.6M (4,200 customers x 12 seats x $49/mo x 12) |
| Average Revenue Per Account (ARPA) | $7,056/year |
| Revenue concentration | Top 10% of customers = 18% of revenue |

**Proposed Usage Pricing Scenarios**

| Tier | API Calls/Month | Price/1K Calls | Floor (Minimum) |
|---|---|---|---|
| Starter | Up to 500K | $0.10 | $199/mo |
| Growth | 500K – 2M | $0.07 | $499/mo |
| Enterprise | 2M+ | $0.04 | $1,499/mo |

**Revenue Impact Model**

| Segment | Customers | Current ARPA | Projected ARPA (Usage) | Revenue Change |
|---|---|---|---|---|
| Light users (< 500K calls) | 1,680 (40%) | $5,880 | $3,600 | -38.8% |
| Medium users (500K-2M calls) | 1,890 (45%) | $7,056 | $7,740 | +9.7% |
| Heavy users (2M+ calls) | 630 (15%) | $9,408 | $14,280 | +51.8% |
| **Blended** | **4,200** | **$7,056** | **$7,548** | **+7.0%** |

**Key Findings:**

| Metric | Seat-Based (Current) | Usage-Based (Projected) | Delta |
|---|---|---|---|
| Total ARR | $29.6M | $31.7M | +$2.1M (+7.0%) |
| At-Risk ARR (light users repriced down) | — | $3.8M in accounts that may churn during transition | Caution |
| Expansion Revenue (heavy users pay more) | — | $3.1M uplift from top 15% | Opportunity |
| Pricing Predictability for Customers | High (fixed seats) | Low (variable usage) | Risk |

**Recommendation:**

> **Proceed with hybrid model, not full cutover.** Keep a seat-based floor ($199-$1,499/mo minimum) so light users don't feel nickel-and-dimed, but add usage tiers on top so heavy users pay proportionally. This protects the $3.8M at-risk ARR from light users while capturing the $3.1M expansion from heavy users. **Grandfather existing customers** for 12 months; apply new pricing to new customers immediately to test elasticity before migrating the base.
>
> **Sensitivity warning:** If the $199 floor is too low, light-user revenue drops further. If too high, it negates the perceived benefit of usage pricing. Model suggests $299 floor optimizes for revenue protection while maintaining competitive pricing.

---

## Summary: When to Use Each Agent

| Situation | Agent | Why |
|---|---|---|
| "I need to communicate this update to 5 different audiences" | **Stakeholder Translator** | Generates audience-specific comms with sensitivity classification |
| "I need to explain a delay without creating panic" | **Stakeholder Translator** | Frames bad news constructively per audience |
| "I have 3 options and need to pick one" | **Decision Engine** | Applies 4 frameworks + pre-mortem, synthesizes recommendation |
| "Should we build or buy this capability?" | **Decision Engine** | Multi-framework analysis with TCO, risk, and opportunity cost |
| "I need to justify this feature investment to the CFO" | **Financial Analyst** | Full financial model with sensitivity analysis and ship/no-ship |
| "What happens to revenue if we change pricing?" | **Financial Analyst** | Revenue impact modeling with segment analysis and recommendations |

---

*Generated by PM Copilots — three purpose-built AI agents for product management.*
