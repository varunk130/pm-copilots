# WSJF and Cost-of-Delay — Decision Engine Frameworks

The Decision Engine ships with RICE, Impact × Confidence × Effort, and Kano. This document adds two frameworks dominant in SAFe / Lean orgs that capture **time-sensitivity** in a way the others don't: **WSJF** (Weighted Shortest Job First) and **Cost of Delay**.

Use these when the decision is sequencing-sensitive — i.e., when *when* you do something matters as much as *whether* you do it.

---

## When to Reach for WSJF / CoD vs the Existing Frameworks

| Framework | Best When |
|-----------|-----------|
| **RICE** | Comparing many small initiatives with similar time horizons |
| **Impact × Confidence × Effort** | Rough triage when evidence quality varies a lot across options |
| **Kano** | Customer-facing initiatives where you need to separate must-haves, performance, and delighters |
| **WSJF** | Sequencing decisions in a continuous-delivery org with finite team capacity |
| **Cost of Delay** | Time-sensitive bets — competitive windows, regulatory deadlines, market-event-tied launches |

WSJF and CoD share the same intuition (*time has economic value*) but answer different questions: WSJF ranks a backlog; CoD quantifies the dollar cost of waiting on a *specific* item.

---

## WSJF — Weighted Shortest Job First

### The Formula

```
WSJF = Cost of Delay / Job Size
     = (Business Value + Time Criticality + Risk Reduction / Opportunity Enablement) / Job Size
```

All four inputs are scored on a **Fibonacci-like scale**: 1, 2, 3, 5, 8, 13, 20, 40 (or stop at 13 for tighter calibration).

### The Four Inputs

| Input | The Question | High-Score Example |
|-------|--------------|--------------------|
| **Business Value** | Revenue impact, customer value, strategic fit | "Unblocks $2M ARR enterprise deal" → 13 |
| **Time Criticality** | Does the value decay if we delay? Is there a hard deadline? | "Compliance deadline in 90 days; non-shipping = revoked license" → 20 |
| **Risk Reduction / Opportunity Enablement (RR/OE)** | Does this de-risk a future bet or unlock new options? | "Builds platform capability that 3 future initiatives depend on" → 13 |
| **Job Size** | Effort relative to other items (story points, person-weeks, T-shirt size mapped to Fibonacci) | XL initiative → 20 |

### The Critical Insight

WSJF *favors small, high-value, time-critical jobs.* A medium-value initiative that's huge gets correctly deprioritized against a slightly-smaller-value initiative that's tiny — because the tiny one frees capacity for *something else* sooner.

This is the most common mistake teams make: they rank by Business Value alone and consistently let large initiatives crowd out a series of smaller, faster wins that would compound to higher total value.

### Process

1. **Calibrate the scale.** Pick one well-understood reference initiative and assign it a `5` on each dimension. Score everything else relative to it.
2. **Score Business Value, Time Criticality, RR/OE independently.** Score by team consensus or by named stakeholders, but score each input on its own; don't let a high BV score drag TC up.
3. **Sum the three numerator inputs.** That's your Cost of Delay proxy.
4. **Divide by Job Size.** Highest WSJF goes first.
5. **Re-rank when the situation changes.** Time Criticality climbs as deadlines approach — a quarterly re-score keeps the queue honest.

### Worked Example

| Initiative | BV | TC | RR/OE | Sum (CoD) | Size | WSJF | Rank |
|------------|---:|---:|------:|----------:|-----:|-----:|-----:|
| Enterprise SSO | 13 | 13 | 5 | 31 | 8 | 3.9 | 2 |
| Usage-based billing | 20 | 8 | 8 | 36 | 20 | 1.8 | 5 |
| API rate limits | 5 | 3 | 13 | 21 | 3 | 7.0 | 1 |
| Mobile push | 5 | 2 | 2 | 9 | 5 | 1.8 | 5 |
| Onboarding redesign | 8 | 5 | 5 | 18 | 8 | 2.25 | 4 |
| AI summarization | 8 | 3 | 8 | 19 | 13 | 1.5 | 7 |
| SOC2 evidence | 5 | 13 | 8 | 26 | 5 | 5.2 | **3** |

Naïve ranking would put Usage-based billing first (highest BV). WSJF correctly surfaces that API rate limits and SSO move the most value-per-week of capacity, and SOC2 jumps because Time Criticality is high relative to its small size.

---

## Cost of Delay (CoD) — Quantified

WSJF uses CoD as a relative numerator. Cost of Delay as a standalone framework asks the harder question: **what's the dollar cost per unit of time of waiting?**

### When to Quantify CoD Standalone

- A specific initiative is being delayed and you need to make the case (or kill the case) for accelerating it
- You're sequencing two initiatives that share a critical resource and need to decide which goes first based on $ at stake
- An exec is asking "how much does it cost us if we slip a quarter?" and a hand-wave answer is unacceptable

### CoD Components

| Component | How to Estimate | Sensitivity |
|-----------|-----------------|-------------|
| **Revenue Forgone** | Customers who would have generated $X/month × months delayed | Moderate — depends on conversion model |
| **Increased Cost of Capture** | If a competitor ships first, our CAC goes up by N% | High — competitive estimates have wide error bars |
| **Opportunity Cost of Capacity** | The next-best initiative this team could ship instead during the delay | Moderate — depends on backlog |
| **Risk Realization** | Probability × impact of a risk that this initiative was meant to mitigate | High — probability estimates are noisy |

### CoD per Week Formula

```
CoD/week = Revenue Forgone/week + ΔCAC × expected_acquisitions/week + Opportunity_Cost/week + Σ(P_risk × Impact_risk / weeks_to_realization)
```

### Sensitivity Analysis

CoD estimates are noisy. The skill always produces a sensitivity table showing the recommendation under three scenarios:

| Scenario | Revenue Forgone | Risk Probability | CoD/week | Recommended Action |
|----------|-----------------|------------------|---------:|--------------------|
| Optimistic | Low end of range | Low end | $20k | Defer to next quarter |
| Base case | Midpoint | Midpoint | $80k | Ship this quarter |
| Pessimistic | High end | High end | $250k | Accelerate / add capacity |

If the recommendation flips between Optimistic and Pessimistic, the report flags the decision as **"sensitive to assumptions"** and lists the top 1–2 inputs to refine before committing.

---

## Surfacing in the Multi-Framework Synthesis

When the Decision Engine runs its full multi-framework synthesis, WSJF and CoD outputs feed in alongside the existing four frameworks:

- **Impact × Confidence Matrix** — captures certainty
- **Strategic Alignment** — captures fit with company priorities
- **Second-Order Effects** — captures cascades
- **Pre-Mortem** — captures failure modes
- **WSJF** — captures sequencing-against-capacity (new)
- **Cost of Delay** — captures dollar-value of timing (new)

The synthesis flags **convergence** (all six frameworks point the same way → high confidence) and **divergence** (frameworks disagree → genuine uncertainty surfaced for human judgment).

A common divergence: Impact × Confidence ranks initiative A first (high BV, high certainty), but WSJF ranks initiative B first (smaller, faster, frees capacity for A *sooner*). The synthesis surfaces this as a sequencing question — "do A second, B first" is often the right answer.

---

## Tips
1. **WSJF is for sequencing, not for picking.** It assumes the items in the backlog have already passed a basic merit bar. Don't use it to rank in-scope vs out-of-scope.
2. **Job Size dominates WSJF.** A 2× error in Size flips many rankings. Calibrate Size against a reference initiative the team has actually built.
3. **Time Criticality climbs over time.** A quarterly re-score is the minimum cadence for any team using WSJF in production.
4. **CoD is a *case-builder*, not a precise number.** The value is the sensitivity analysis, not the point estimate. Treat any CoD figure with at least ±50% uncertainty unless you have very strong revenue data.
5. **Don't quantify CoD for everything.** Reserve CoD analysis for the 2–3 decisions per quarter where the time-value of money is genuinely large.
