---
name: financial-analyst
description: 'Build financial models from natural language with sensitivity analysis. Use when: feature ROI, business case, revenue projection, pricing analysis, TAM SAM SOM, unit economics, NPV, payback period, sensitivity analysis, ship or no ship.'
---

# Financial Analyst

Build rigorous financial models from natural language inputs. Fills gaps with SaaS benchmarks, runs sensitivity analysis, and produces ship/no-ship/de-risk recommendations.

## Output
Save to `outputs/financial-[topic]-[YYYY-MM-DD].md`

## When to Use
- Building a business case for a new feature
- ROI analysis for build vs. buy decisions
- TAM/SAM/SOM market sizing
- Pricing change impact modeling
- Any situation where you need numbers to justify a decision

## What You'll Get

| Output | Description |
|--------|-------------|
| **Assumptions Table** | Every input labeled by source (PM Input, SaaS Benchmark, Estimated) |
| **Key Metrics Dashboard** | Visual metric cards with color-coded status |
| **Full Model** | Unit economics, revenue projections, NPV, payback period |
| **Sensitivity Matrix** | Multi-variable sensitivity showing break-even boundaries |
| **Decision Framework** | Ship / Do Not Ship / De-risk with specific conditions |

## Process

### Step 1: Describe the Feature or Initiative
I'll ask:
> "What are you modeling? Describe the feature, initiative, or pricing change. Include any numbers you have — costs, expected users, pricing, timeline. I'll fill gaps with SaaS benchmarks."

### Step 2: Build Assumptions Table
Every model input gets a source label:
- **📌 PM Input** — You provided this number
- **📊 SaaS Benchmark** — Industry standard (sourced and cited)
- **🔮 Estimated** — My best estimate (flagged for validation)

```markdown
| Assumption | Value | Source | Confidence |
|---|---|---|---|
| Development cost | $180,000 | PM Input | High |
| Monthly active users (Year 1) | 2,400 | SaaS Benchmark (avg adoption 12%) | Medium |
| Conversion rate to paid | 5% | SaaS Benchmark (B2B freemium avg) | Medium |
| Average revenue per user | $45/mo | PM Input | High |
| Churn rate | 4%/mo | Estimated from category avg | Low |
```

### Step 3: Build the Model
Core calculations:
- **Unit Economics**: CAC, LTV, LTV/CAC ratio, payback period
- **Revenue Projections**: Monthly and annual with growth assumptions
- **Cost Structure**: Development, infrastructure, support, opportunity cost
- **NPV Analysis**: 3-year net present value at standard discount rate
- **Break-even Analysis**: When does cumulative revenue exceed cumulative cost?

### Step 4: Sensitivity Analysis
I'll vary the 2-3 most uncertain assumptions and show how the model changes:

```markdown
| Conversion Rate → | 3% | 5% (base) | 7% | 10% |
|---|---|---|---|---|
| Monthly Revenue | $3,240 | $5,400 | $7,560 | $10,800 |
| Annual Revenue | $38,880 | $64,800 | $90,720 | $129,600 |
| Payback Period | 55 months | 33 months | 24 months | 17 months |
| NPV (3yr) | -$42,000 | $68,400 | $178,800 | $356,400 |
```

### Step 5: Decision Framework
Based on the model:

- **🟢 Ship** — if base case NPV > 0 AND payback < 18 months AND LTV/CAC > 3
- **🔴 Do Not Ship** — if even optimistic case doesn't break even in 24 months
- **🟡 De-risk** — if base case is marginal; specify what assumptions to validate first

## Demo Scenario: Feature ROI Analysis

**Input:**
> "We want to build an AI assistant feature for our project management SaaS. It'll cost about $200K to build (2 engineers × 3 months + infra). We have 20,000 MAU, pricing is $49/user/month. We think it could increase conversion from free to paid by 2 percentage points and reduce churn by 0.5%."

**Sample Key Metrics:**

| Metric | Value | Status |
|---|---|---|
| Development Cost | $200,000 | 📌 PM Input |
| Incremental Annual Revenue | $235,200 | 🟢 Strong |
| Payback Period | 10.2 months | 🟢 Under 12 months |
| 3-Year NPV | $412,000 | 🟢 Positive |
| LTV/CAC Improvement | 3.2x → 4.1x | 🟢 Healthy |
| Break-even Users | 340 paid conversions | 🟡 Achievable but monitor |

**Sample Decision:**
> **🟢 SHIP** — Base case is strong (10-month payback, $412K NPV). Even at 50% of projected conversion lift, payback stays under 18 months. **De-risk by**: running a 30-day beta with 500 users to validate the conversion lift assumption before full rollout.

## Tips
1. **Share what you know** — Even rough numbers help. I'll benchmark the rest.
2. **Flag your biggest uncertainty** — I'll stress-test that variable first
3. **Include opportunity cost** — "These 2 engineers could be working on X instead"
4. **Ask for scenarios** — "What if pricing is $29 instead of $49?"

## Framework Reference

**SaaS Benchmarks Used:**
- B2B freemium conversion: 2-5% (OpenView Partners)
- Monthly churn: 3-7% for SMB, 1-2% for enterprise (ProfitWell)
- LTV/CAC ratio target: 3:1+ (Bessemer)
- CAC payback target: <18 months (SaaS Capital)
- Discount rate for NPV: 10-15% (standard SaaS)

> ⚠️ All benchmarks are industry averages. Your actual performance depends on product, market, and execution. Always validate with your own data.
