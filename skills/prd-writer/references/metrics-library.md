# Metrics Library — Common Product Metrics with Thresholds

Reference for defining success metrics, guardrails, and graduation criteria in PRDs. Each metric includes: definition, typical baseline, target delta, alert threshold, and measurement window.

---

## How to Use This Library

1. **Select metrics** that match your feature type (engagement, conversion, AI quality, etc.)
2. **Set your baseline** from current production data — never use industry benchmarks as your baseline
3. **Define targets** as specific deltas (≥10%) or absolute values (≤42s), never directional ("improve")
4. **Add at least 2 guardrail metrics** — things that must NOT get worse
5. **Specify MDE** (Minimum Detectable Effect) — smallest change worth detecting

---

## Section 1: Engagement Metrics

### 1.1 Session Metrics

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| DAU/MAU ratio | Daily actives / Monthly actives | 20-30% (consumer), 40-60% (productivity) | +5pp | Drop >3pp |
| Session duration (P50) | Median time in app per session | Varies by product | +10-15% | Drop >20% |
| Sessions per user per week | Avg sessions/active user | 3-5 (productivity), 1-2 (occasional) | +0.5 sessions | Drop >1 session |
| Feature adoption rate | % users who used feature in 30d | 0% (new feature) | ≥30% at D30 | <15% at D30 |
| Feature retention (D7/D30) | % who used feature again after first use | Varies | D7≥40%, D30≥25% | D7<25% |

### 1.2 Interaction Quality

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Task completion rate | % of users who complete intended task | 60-80% | +10pp | Drop >5pp |
| Time to first value | Time from signup to first meaningful action | Varies | -20% | +30% |
| Error rate (user-facing) | % of actions resulting in error state | <5% | <2% | >8% |
| Rage click rate | Multiple clicks in frustration | <2% | <1% | >4% |
| Abandonment rate | % who start a flow but don't complete | 20-40% | -15% | +10pp |

---

## Section 2: AI/ML Quality Metrics

### 2.1 Response Quality

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Relevance score | Human-rated relevance (1-5) | 3.2/5.0 | ≥4.0/5.0 | <3.0/5.0 |
| Accuracy (golden set) | % correct on labeled test set | N/A (set at launch) | ≥85% | <75% |
| Hallucination rate | % responses with factual errors | <5% (target at launch) | <2% | >8% |
| Refusal rate | % of valid requests incorrectly refused | <5% | <3% | >10% |
| Harmful output rate | % responses flagged by safety filters | <0.1% | <0.05% | >0.5% |

### 2.2 AI Feature Adoption

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Suggestion acceptance rate | % of AI suggestions accepted by user | 20-35% (inline code) | ≥35% | <15% |
| Edit rate post-accept | % of accepted suggestions user edits | 30-50% | <40% (lower = more accurate) | >70% |
| Regeneration rate | % of responses where user asks again | 10-20% | <15% | >30% |
| Thumbs up/down ratio | Explicit feedback signal | Varies | >4:1 positive | <2:1 |
| Click-through on suggestions | % suggested items clicked | 15-25% | ≥25% | <10% |

### 2.3 AI Performance (Technical)

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| P50 latency | Median response time | Varies by model | <500ms | >1000ms |
| P95 latency | 95th percentile response time | Varies | <2000ms | >3000ms |
| P99 latency | 99th percentile response time | Varies | <5000ms | >8000ms |
| Token cost per user/month | LLM API cost per active user | Set at launch | <$0.50 | >$1.00 |
| Cache hit rate | % served from cache vs live model | 0% (new) | ≥20% | N/A |
| Model error rate | % of model API calls that fail | <1% | <0.5% | >2% |

---

## Section 3: Conversion Metrics

### 3.1 Funnel Metrics

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Signup conversion | Visitors → registered users | 2-5% (SaaS) | +20% relative | Drop >1pp |
| Activation rate | Signups who reach "aha moment" | 30-50% | ≥50% | <25% |
| Free → paid conversion | Free users who upgrade | 2-5% (PLG) | ≥5% | <1.5% |
| Trial conversion rate | Trial → paid | 15-25% | ≥25% | <10% |
| Onboarding completion | % complete full onboarding flow | 40-60% | ≥70% | <30% |

### 3.2 Revenue Metrics

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| MRR | Monthly recurring revenue | Current | +X% from feature | Drop >5% |
| ARPU | Average revenue per user | Current | +10-20% | Drop >5% |
| Expansion revenue | Revenue from upsells/upgrades | Current | +15% | Flat |
| Payback period | Months to recover CAC | 12-18mo (SaaS) | <12mo | >24mo |
| LTV:CAC ratio | Lifetime value / acquisition cost | >3:1 (healthy) | ≥4:1 | <2:1 |

---

## Section 4: Retention Metrics

### 4.1 Cohort Retention

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| D1 retention | % back on Day 1 | 25-40% (consumer) | ≥40% | <20% |
| D7 retention | % back on Day 7 | 10-20% (consumer), 40-60% (B2B) | +5pp vs control | -5pp |
| D30 retention | % back on Day 30 | 5-15% (consumer), 30-50% (B2B) | +5pp vs control | -5pp |
| Logo retention (B2B) | % of accounts still active | >90% (target) | ≥95% | <85% |
| Net Revenue Retention | MRR retained + expansion / MRR | >100% (healthy SaaS) | ≥110% | <90% |

### 4.2 Churn Metrics

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Monthly churn rate | % users/revenue lost in 30d | 2-5% (SaaS) | <3% | >7% |
| Involuntary churn | Churn due to payment failure | 10-30% of total churn | <20% of churn | >40% |
| Time to churn | Avg days before churning | Varies | +20% longer | N/A |
| Save rate (win-back) | % churned users reactivated | 5-15% | ≥15% | <5% |

---

## Section 5: Performance & Reliability

### 5.1 Availability

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Uptime | % time system is available | 99.9% | ≥99.95% | <99.5% |
| MTTR | Mean time to recovery from incident | 30-60min | <30min | >2 hours |
| MTTD | Mean time to detect incident | 5-15min | <5min | >30min |
| Error budget consumption | % of error budget used | <50% of monthly | <80% | >100% |

### 5.2 Response Times

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| API P50 latency | Median API response | <100ms | <50ms | >200ms |
| API P95 latency | 95th pct API response | <300ms | <200ms | >500ms |
| Page load time (P75) | 75th pct page load | <2s | <1.5s | >3s |
| Core Web Vitals — LCP | Largest contentful paint | <2.5s (good) | <1.8s | >4s |
| Core Web Vitals — FID | First input delay | <100ms (good) | <50ms | >300ms |

### 5.3 Infrastructure

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| CPU utilization | Average CPU across fleet | <60% | <50% | >80% |
| Memory utilization | Average memory | <70% | <60% | >85% |
| DB query P95 | 95th pct DB query time | <50ms | <20ms | >200ms |
| Cache hit rate | % served from cache | 70-85% | ≥85% | <60% |

---

## Section 6: Support & Quality

### 6.1 Support Metrics

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| Ticket volume per 1K users | Support tickets per thousand users | Varies | -15% | +20% |
| First response time | Time to first agent reply | <2h (SaaS) | <1h | >4h |
| Time to resolution | Ticket open to closed | <24h | <8h | >72h |
| CSAT score | Post-support satisfaction | 4.0-4.5/5.0 | ≥4.5/5.0 | <3.8/5.0 |
| Deflection rate | % resolved without human agent | 30-40% | ≥50% | <20% |

### 6.2 Quality Signals

| Metric | Definition | Typical Baseline | Good Target | Alert |
|--------|------------|-----------------|-------------|-------|
| NPS | Net Promoter Score | 30-50 (SaaS) | +10 points | -10 points |
| CSAT (product) | Feature satisfaction rating | 3.8-4.2/5.0 | ≥4.3/5.0 | <3.5/5.0 |
| App store rating | iOS/Android store rating | 4.0-4.5 | ≥4.5 | <3.8 |
| Bug report rate | Bugs filed per 1K users per week | Varies | -20% | +30% |
| Crash rate | App crashes per 1K sessions | <0.1% | <0.05% | >0.5% |

---

## Section 7: A/B Test Specific Metrics

### 7.1 Statistical Requirements

| Parameter | Recommended Value | Minimum | Notes |
|-----------|------------------|---------|-------|
| Statistical significance | p < 0.05 | p < 0.1 | Two-tailed test preferred |
| Statistical power | 80% | 70% | Higher for high-stakes decisions |
| Minimum sample size | Calculate per MDE | N/A | Use power calculator |
| Test duration | 2-4 weeks | 1 week | Must cover full weekly cycle |
| Randomization unit | User-level | N/A | Session-level causes contamination |

### 7.2 Common MDE Targets

| Metric Type | Typical MDE | Minimum Viable MDE |
|-------------|-------------|-------------------|
| Conversion rate | +1-2pp absolute | +0.5pp |
| Retention rate | +3-5pp absolute | +2pp |
| Revenue per user | +5-10% | +3% |
| Latency | -10% | -5% |
| Engagement time | +10-15% | +5% |
| Error rate | -20% relative | -10% |

### 7.3 Guardrail Metric Checklist

For every A/B test, define guardrails for:
- [ ] Core engagement metric (don't let it drop)
- [ ] Revenue metric (watch for cannibalization)
- [ ] Performance metric (latency, error rate)
- [ ] Downstream funnel metric (does it affect conversion?)
- [ ] Specific sensitive metric for your domain (e.g., safety, privacy)

---

## Section 8: Cost Metrics

### 8.1 AI/LLM Cost

| Metric | Definition | Typical Range | Alert |
|--------|------------|--------------|-------|
| Cost per completion | LLM API cost per response | $0.001-0.05 | >$0.10 |
| Cost per active user/month | Total LLM cost / MAU | $0.10-2.00 | >$5.00 |
| Cost per 1K tokens (input) | LLM input token cost | $0.001-0.015 | Track vs budget |
| Cost per 1K tokens (output) | LLM output token cost | $0.002-0.060 | Track vs budget |
| Cost as % of revenue | LLM cost / MRR | <10% (healthy) | >25% |

### 8.2 Infrastructure Cost

| Metric | Definition | Good Target | Alert |
|--------|------------|-------------|-------|
| Cost per user/month | Total infra cost / MAU | Varies by scale | +20% month-over-month |
| Cost per transaction | Infra cost per billable event | Decreasing with scale | +15% |
| Reserved vs on-demand ratio | % compute on reserved pricing | ≥60% reserved | <40% reserved |

---

## Metric Anti-Patterns

### Never Use These in PRDs

| Bad Metric | Why It's Bad | Use Instead |
|------------|-------------|-------------|
| "Improve engagement" | No threshold, not measurable | "DAU/MAU increases ≥5pp" |
| "Reduce latency" | Direction only, no target | "P95 latency <200ms" |
| "Increase satisfaction" | Unmeasurable without operationalization | "NPS increases from 42 to 50+" |
| "Better retention" | Relative without baseline | "D30 retention ≥35% (from 28% baseline)" |
| "Positive user feedback" | Anecdotal, not trackable | "CSAT ≥4.2/5.0 with ≥100 responses" |
| "More signups" | No quantity, no timeframe | "Trial signups increase ≥20% in 30d" |
| "Fast response" | Not defined | "P50 API response <100ms" |

### The Threshold Rule

Every metric in a PRD must have:
1. **A baseline** — where you are today
2. **A target** — specific number you're trying to hit
3. **An alert threshold** — when to worry
4. **A measurement window** — how long to measure

Example:
- ❌ "Improve reply time"
- ✅ "P50 reply time: baseline 47s → target ≤42s → alert if >50s → measured over 14 days"
