---
name: roadmap-architect
description: 'Turns a list of prioritized initiatives into a sequenced quarterly roadmap with themes, dependencies, capacity checks, and confidence ranges. Use when: build roadmap, quarterly planning, sequence initiatives, capacity planning, dependency mapping, theme grouping, commit vs stretch, roadmap narrative.'
---

# Roadmap Architect

Convert a backlog of decisions and initiatives into a credible quarterly roadmap — grouped by theme, sequenced by dependency, sized against team capacity, and presented with a stakeholder-ready narrative.

This skill is designed to run **after** the Decision Engine (which tells you *what* to do) and **before** the Stakeholder Translator (which tells the world). It answers the middle question: *in what order, against what capacity, with what trade-offs?*

## Output
Save to `outputs/roadmap-[quarter]-[YYYY-MM-DD].md`

## When to Use
- Quarterly or half-year planning with 5–15 initiatives competing for capacity
- Translating a list of "yes" decisions into a sequenced plan
- Pressure-testing an existing roadmap for hidden dependencies or overcommitment
- Producing a one-page roadmap narrative for an exec or board readout

## What You'll Get

| Artifact | Description |
|----------|-------------|
| **Theme Map** | Initiatives grouped into 3–5 strategic themes with a one-sentence "why now" per theme |
| **Sequenced Plan** | Initiatives placed into Now / Next / Later with rationale for each placement |
| **Dependency Graph** | Hard, soft, and reverse dependencies between initiatives (with risk callouts) |
| **Capacity Check** | Estimated effort vs. available team capacity, with overcommit / slack flags |
| **Commit vs. Stretch** | Clear split between committed scope and stretch goals, with confidence bands |
| **Narrative One-Pager** | A stakeholder-ready summary: themes, bets, trade-offs, risks |

## Process

### Step 1: Intake
I'll ask:
> "Share the initiatives you're considering. For each one, include: name, brief description, rough size (S / M / L / XL), strategic theme (if known), and any known dependencies. Then tell me your team capacity (number of engineers, designers, PMs) and the planning horizon (e.g., Q3 only, or Q3 + Q4)."

### Step 2: Theme Clustering
I'll group initiatives into 3–5 themes (e.g., *Move Upmarket*, *Activation*, *Platform Resilience*) and write a one-sentence "why this theme, why now" for each. Themes that contain only one initiative get challenged — they usually mean the theme is too narrow or the initiative is misclassified.

### Step 3: Dependency Mapping
For each initiative I'll identify:
- **Hard dependencies** — cannot start until X ships
- **Soft dependencies** — can start, but value is unlocked only when X ships
- **Reverse dependencies** — other teams blocked on this
- **Shared-resource conflicts** — two initiatives needing the same scarce skill or system

### Step 4: Sequencing into Now / Next / Later
- **Now** — committed, in-flight or starting this quarter
- **Next** — scoped and queued, will start when Now items free up capacity
- **Later** — accepted but not yet scoped; revisit in next planning cycle
Each placement gets a one-line rationale tied back to its theme and dependencies.

### Step 5: Capacity Check
I'll convert sizes (S=1, M=3, L=8, XL=20 person-weeks by default — you can override) and compare total committed effort to available capacity. If overcommitted, I'll flag it explicitly and propose 2–3 specific cuts or deferrals.

### Step 6: Commit vs. Stretch + Confidence Bands
- **Commit** items get a confidence band (High / Medium / Low) based on dependency risk, scope clarity, and team familiarity.
- **Stretch** items are explicit "if Commit goes well, we pull these in" — never quietly added.

### Step 7: Narrative One-Pager
I'll produce a single-page summary with:
- The 3–5 themes and their bets
- What we're deliberately *not* doing this quarter, and why
- The top 3 risks and mitigation owners
- A one-line "if this quarter goes right, by [end date] we will have…" outcome statement

## Demo Scenario: Q3 Planning for a B2B SaaS

**Input:**
> "10 initiatives in the hopper for Q3. Team: 8 engineers, 2 designers, 1 PM. Horizon: Q3 only. Initiatives:
> 1. Enterprise SSO (L) — depends on identity service refactor
> 2. Identity service refactor (M)
> 3. Usage-based billing (XL) — finance team blocked on this
> 4. AI summarization in dashboard (L)
> 5. Mobile push notifications (M)
> 6. SOC2 Type II evidence collection (M) — compliance theme
> 7. Onboarding redesign (L)
> 8. API rate limit overhaul (S)
> 9. Customer health score v2 (M)
> 10. Internal admin tool revamp (S)"

**Sample Theme Map:**

| Theme | Initiatives | Why Now |
|-------|-------------|---------|
| Move Upmarket | SSO, Identity refactor, SOC2 evidence | 3 enterprise deals gated on these in Q3 pipeline |
| Monetization Foundation | Usage-based billing | Finance committed to new pricing in Q4 — needs Q3 build |
| Activation & Retention | Onboarding redesign, Health score v2 | Trial-to-paid conversion plateaued at 12% for 2 quarters |
| Platform Hygiene | API rate limits, Admin tool | Pager incidents trending up; deferring further increases risk |

**Sample Capacity Check (default sizing):**

| Bucket | Effort (person-weeks) | Capacity (person-weeks) | Status |
|--------|----------------------:|------------------------:|--------|
| Commit (Now) | 42 | 48 | ✅ 12% slack |
| Stretch (Next) | 11 | — | Pulled in if SSO ships by week 8 |
| Deferred (Later) | 28 | — | Mobile push, AI summarization, Admin tool |

**Sample Risk Callouts:**

| Risk | Likelihood | Mitigation | Owner |
|------|-----------:|-----------|-------|
| Identity refactor slips → SSO slips → 2 deals miss Q3 | Medium | Start refactor week 1; weekly checkpoint with sales | Eng lead |
| Usage-based billing under-scoped (XL is a guess) | High | Spike in week 1 to firm up estimate before committing scope | Billing PM |
| Compliance evidence collection competes with onboarding designer | Medium | Borrow contract designer for 3 weeks of SOC2 screenshots | Design lead |

## Tips
1. **Bring decisions, not wishes** — this skill assumes prioritization is mostly done. If you're still picking, run Decision Engine first.
2. **Be honest about XL items** — anything sized XL almost always hides a missing decision. Spike before committing.
3. **Name what you're cutting** — a roadmap without an explicit "not doing" list is a wish list, not a plan.
4. **Re-run mid-quarter** — feed in actuals (what shipped, what slipped) and let the skill resequence Next / Later.
