# Part 2 — KPI Framework, Business Experiment Analysis & Decision Recommendation

**Student:** Satya Sampelli | **ID:** 211817  
**Course:** Business Analytics — Bitsom  
**Repo:** satya_211817_part2_kpi_experiment

---

## Business Context

A subscription-based digital product company ran an A/B test on their onboarding experience. Users were split into two groups — Control (old onboarding) and Treatment (new campaign). The company wants to know whether the new campaign worked well enough to roll out to all users.

My job was to define the right success metrics, analyse the experiment results, run a statistical test and make a clear recommendation.

## Business Problem Statement

**Decision to be made:** Whether to launch the new onboarding campaign to all users or keep the existing experience.

**Who it impacts:** The product team, marketing team, support team, and all new users who sign up after the decision is made.

**Metric that should improve:** Paid Conversion Rate — the percentage of users who convert from free/trial to a paid plan.

**Risks to monitor:** Support ticket volume increasing, refund rate rising, revenue per converted user dropping, and segment-level decline in any specific region or device type.

**Evidence required:** A statistically significant improvement in paid conversion rate (p-value below 0.05), with no major deterioration in guardrail metrics like refund rate and support tickets.

---

## Dataset Description

| Detail | Value |
|---|---|
| File | campaign_experiment_data.xlsx |
| Total users | 1,408 |
| Control group | 693 users |
| Treatment group | 715 users |
| Time period | Jan–May 2025 |

**Key columns:** user_id, experiment_group, region, device_type, traffic_source, plan_type, visited_landing_page, started_trial, completed_onboarding, converted_to_paid, revenue_30d, support_tickets_30d, refund_requested, days_to_convert, engagement_score

---

## Data Preparation and Validation

Before running the experiment analysis, I checked the dataset for the following:

| Check | Finding | Action |
|---|---|---|
| Missing values - device_type | 18 missing | Retained, not used in hypothesis test |
| Missing values - traffic_source | 24 missing | Retained, not used in hypothesis test |
| Missing values - days_to_convert | 1336 missing | Expected — only converted users have this value |
| Missing values - engagement_score | 14 missing | Retained, excluded from averages |
| Duplicate user IDs | 8 duplicates found | Flagged, retained for analysis |
| Invalid binary values | 0 invalid | All binary columns clean |
| Revenue outliers | Max = 8610.72, 71 users in top 5% | Retained as legitimate high-value users |
| Group balance | Control 693, Treatment 715 | Acceptable balance for testing |
| Region distribution | Similar split across groups | No imbalance detected |
| Device distribution | Similar split across groups | No imbalance detected |

## North Star Metric

**Selected Metric: Paid Conversion Rate**

**Why this is the main success metric:**
Paid conversion rate directly measures whether the new campaign 
achieves its core goal — getting users to pay for the product. 
Every other metric in the funnel only matters if it eventually 
leads to this outcome.

**Why other metrics are supporting metrics:**
Landing page visits, trial starts and onboarding completion are 
all steps toward conversion but do not generate revenue on their 
own. Engagement score and days to convert tell us about user 
behaviour but not business outcome. Only paid conversion rate 
confirms the campaign actually worked.

**How it connects to business growth:**
Every 1% increase in conversion rate directly increases revenue. 
With 1408 users in this experiment, moving from 3.17% to 6.99% 
means roughly 54 additional paying customers — a direct and 
immediate revenue impact.

**What could go wrong if optimised blindly:**
If we only chase conversion rate, we might attract users who 
convert quickly but then refund or churn. We could also increase 
support burden by pushing users through an experience they find 
confusing. This is why we also monitored refund rate, support 
ticket rate and revenue per converted user as guardrail metrics.

---

## KPI Tree Summary

The North Star metric breaks down into:

**Acquisition Quality** → Landing Page Visit Rate, Traffic Source Quality, Device Type Mix  
**Onboarding Engagement** → Trial Start Rate, Onboarding Completion Rate, Engagement Score  
**Monetization** → Avg Revenue Per User, Avg Revenue Per Converted User, Days to Convert  
**Guardrail Metrics** → Refund Rate, Support Ticket Rate, Segment-Level Performance

---

## Experiment Analysis Approach

1. Loaded raw data into experiment_analysis.xlsx
2. Built a Summary Metrics sheet comparing all key metrics for Control vs Treatment
3. Added segment analysis by region and device type
4. Ran a one-tailed two-sample t-test on paid conversion rate using Excel's T.TEST function
5. Evaluated guardrail metrics to check for hidden risks

---

## Hypothesis Test Summary

- **Null Hypothesis:** Treatment conversion rate = Control conversion rate
- **Alternate Hypothesis:** Treatment conversion rate > Control conversion rate
- **Test:** One-tailed two-sample t-test
- **p-value:** 0.0011
- **Decision:** Reject null hypothesis — result is statistically significant

---

## Key Results

| Metric | Control | Treatment | Change |
|---|---|---|---|
| Paid Conversion Rate | 3.17% | 6.99% | +3.82% |
| Onboarding Completion | 15.58% | 21.26% | +5.68% |
| Avg Engagement Score | 57.03 | 62.93 | +5.90 |
| Support Ticket Rate | 14.72% | 24.76% | +10.04% |
| Refund Rate | 0.00% | 0.42% | +0.42% |

---

## Guardrail Metrics Considered

1. **Support Ticket Rate** — increased significantly, main risk post-launch
2. **Refund Rate** — small increase, low risk
3. **Days to Convert** — improved, positive signal

---

## Final Recommendation

**Launch the campaign to all users.**

The conversion rate more than doubled and the result is statistically proven (p = 0.0011). All funnel metrics improved across all regions and device types. The main risk is the support ticket increase — the support team should be briefed and ticket volume tracked weekly for the first month after launch.

---

## Assumptions and Limitations

- Statistical significance does not prove causation
- Short experiment window — seasonal effects possible
- Long-term retention impact unknown

---

## Screenshots

| File | What It Shows |
|---|---|
| summary_metrics.png | Control vs Treatment comparison table with all key metrics |
| hypothesis_test_output.png | T-test setup and p-value result in Excel |
| kpi_tree_preview.png | KPI tree showing North Star metric and all drivers |
