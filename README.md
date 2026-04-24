# 🧠 PM Copilots

**Your AI co-pilots for product management — translate updates for any audience, make data-backed decisions, and build financial models in seconds, not hours.**

Three purpose-built agents that handle the grunt work so you can focus on strategy: a **Stakeholder Translator**, a **Decision Engine**, and a **Financial Analyst**.


> **⚠️ Disclaimer:** All data in this project is entirely synthetic and mock-generated for demonstration purposes. Customer names, company names, financial figures, market data, and all agent outputs are fictional. No real customer data, proprietary information, or actual business metrics were used.

---

## Screenshots

<p align="center">
  <img src="screenshots/ai-pm-dashboard.png" alt="AI PM Agents Dashboard" width="100%"/>
  <br/><em>Landing page — 3 specialized agents with one-click launch</em>
</p>

---
<p align="center">
  <img src="screenshots/decision-engine.png" alt="Decision Engine — Impact × Confidence Matrix" width="100%"/>
  <br/><em>Decision Engine — multi-framework strategic analysis with scoring methodology</em>
</p>

---
<p align="center">
  <img src="screenshots/financial-analyst.png" alt="Financial Analyst — Key Metrics Dashboard" width="100%"/>
  <br/><em>Financial Analyst — assumption sourcing, key metrics, and sensitivity analysis</em>
</p>

---
<p align="center">
  <img src="screenshots/stakeholder-translator.png" alt="Stakeholder Translator — Sensitivity Classification and Tabbed Outputs" width="100%"/>
  <br/><em>Stakeholder Translator — sensitivity classification with 5 audience-tailored outputs</em>
</p>

---

## Why This Exists

Product managers spend a disproportionate amount of time on communication translation, decision structuring, and financial justification — not on the strategic thinking itself. A single product update requires five different versions for five different audiences. A prioritization decision requires manually applying three or four frameworks. A feature business case requires hours of spreadsheet modeling.

This project demonstrates how **purpose-built AI agents** — each with a distinct cognitive role — can compress these workflows:

```
One product update  →  5 audience-tailored communications (engineering, exec, board, customer, sales)
One strategic question  →  4-framework analysis with synthesized recommendation
One feature description  →  Full financial model with sensitivity analysis and ship/no-ship decision
```

Each agent doesn't just generate text. It applies structured reasoning: sensitivity classification, multi-framework scoring, crossover analysis, pre-mortem scenarios, and audience-specific framing.

---

## The Three Agents

### 1. Stakeholder Translator

**Cognitive function: Audience Adaptation**

Takes a single product update and produces five tailored communications — each with the right tone, detail level, technical depth, and framing for its audience. Includes sensitivity classification (Safe / Caution / Internal Only) so PMs know what's shareable and what's not.

| Output | Audience | Framing |
|--------|----------|---------|
| Engineering Update | Dev team | Technical decisions, code references, debt trade-offs |
| Executive Summary | Leadership | Business impact, metrics, decisions needed |
| Board Narrative | Board of Directors | Strategic positioning, speaker notes |
| Customer Changelog | End users | Benefits-focused, no internal details |
| Sales Enablement | Sales team | Objection handling, competitive positioning, talk tracks |

**Demo scenarios:** AI feature launch, missed deadline communication, competitive response strategy.

→ **[View Skill Definition](skills/stakeholder-translator/SKILL.md)**

---

### 2. Decision Engine

**Cognitive function: Strategic Reasoning**

Applies four distinct analytical frameworks to a product decision, then synthesizes them into a single prioritized recommendation with confidence scoring and a pre-mortem analysis.

| Framework | What It Evaluates |
|-----------|-------------------|
| Impact × Confidence Matrix | Revenue impact weighted by execution certainty |
| Strategic Alignment | Weighted scoring against company goals |
| Second-Order Effects | Downstream consequences (positive and negative) for each option |
| Pre-Mortem Analysis | "It's December and this failed — what went wrong?" with probability estimates |

**Demo scenarios:** Quarterly prioritization (3 competing initiatives), ship/iterate/sunset decision for an underperforming feature.

→ **[View Skill Definition](skills/decision-engine/SKILL.md)**

---

### 3. Financial Analyst

**Cognitive function: Quantitative Modeling**

Builds rigorous financial models from natural language inputs. Fills gaps with SaaS benchmarks, runs sensitivity analysis across multiple variables, and produces ship/no-ship/de-risk recommendations.

| Output | Description |
|--------|-------------|
| Assumptions Table | Every input labeled by source (PM Input, SaaS Benchmark, Estimated) with edit affordance |
| Key Metrics Dashboard | Visual metric cards with color-coded status |
| Full Model | Unit economics, revenue projections, NPV, payback period |
| Sensitivity Matrix | Multi-variable sensitivity showing break-even boundaries |
| Decision Framework | Ship / Do Not Ship / De-risk with specific conditions for each |

**Demo scenarios:** Feature ROI analysis, TAM/SAM/SOM market sizing, pricing change impact modeling.

→ **[View Skill Definition](skills/financial-analyst/SKILL.md)**

---

## Installation (Claude Code Skills)

Each agent is available as a standalone Claude Code skill:

```bash
# Clone and copy all skills
git clone https://github.com/varunk130/pm-copilots.git
cp -r pm-copilots/skills/* ~/.claude/skills/

# Or copy individual skills
cp -r pm-copilots/skills/stakeholder-translator ~/.claude/skills/
cp -r pm-copilots/skills/decision-engine ~/.claude/skills/
cp -r pm-copilots/skills/financial-analyst ~/.claude/skills/
```

Restart Claude Code after copying skills. Use via slash commands or natural language prompts.

---

## What Makes This Interesting (for AI Researchers)

- **Structured reasoning over free-form generation**: Each agent applies named analytical frameworks (Impact × Confidence, Pre-Mortem, Crossover Analysis) rather than open-ended generation
- **Sensitivity classification as a first-class concept**: The Stakeholder Translator classifies information by sensitivity level *before* generating — knowing what not to say to which audience
- **Multi-framework convergence**: The Decision Engine applies four independent frameworks and checks whether they converge — divergence surfaces genuine uncertainty
- **Explicit assumption sourcing**: The Financial Analyst labels every model input with its source (user-provided, benchmark, estimated) — making it visible where confidence is high vs. interpolating
- **Audience-aware generation at scale**: Five distinct communications from one input, each correct for its audience

---

## Skills Structure

```
pm-copilots/
├── README.md
├── screenshots/
│   ├── ai-pm-dashboard.png
│   ├── decision-engine.png
│   ├── financial-analyst.png
│   └── stakeholder-translator.png
└── skills/
    ├── stakeholder-translator/
    │   └── SKILL.md
    ├── decision-engine/
    │   └── SKILL.md
    └── financial-analyst/
        └── SKILL.md
```

## License

MIT — see [LICENSE](LICENSE) for details.

---


<p align="center">
  <strong>Built by Varun Kulkarni</strong><br/>
  <sub>Powered by Claude Code</sub>
</p>
