# Hypothesis Test Notes
## Part 2 — KPI Framework, Business Experiment Analysis & Decision Recommendation
**Student:** Satya SAmpelli| **ID:** 211817

---

## 1. Metric Being Tested

**Metric:** Paid Conversion Rate

**Definition:** The proportion of users in each group who converted to a paid subscription plan within 30 days of signup.

**Reason for choosing this metric:** Paid conversion rate is the North Star metric for this experiment because it directly measures whether the new onboarding campaign achieved its core business objective — getting users to pay for the product. All other funnel metrics (landing page visits, trial starts, onboarding completion) are intermediate steps that only matter if they ultimately result in paid conversions. A statistically significant improvement in this metric would provide sufficient evidence to justify a full rollout of the campaign.

---

## 2. Hypotheses

**Null Hypothesis (H0):**
The paid conversion rate of the Treatment group is equal to the paid conversion rate of the Control group. Any observed difference is due to random variation and not the effect of the new campaign.

**Alternate Hypothesis (H1):**
The paid conversion rate of the Treatment group is greater than the paid conversion rate of the Control group. The new onboarding campaign has a genuine positive effect on conversions.

---

## 3. Test Setup

| Parameter | Value |
|---|---|
| Test type | One-tailed two-sample t-test |
| Significance level (α) | 0.05 |
| Control group size | 693 users |
| Treatment group size | 715 users |
| Metric tested | converted_to_paid (binary: 1 = converted, 0 = did not convert) |
| Tool used | Microsoft Excel — T.TEST function |

**Why one-tailed:** A one-tailed test was selected because the business question is directional — the company wants to know whether the Treatment performs *better* than Control, not simply *different*. A two-tailed test would be appropriate only if we were testing for any difference in either direction, which is not the case here.

**Why t-test:** A two-sample t-test is appropriate for comparing the means of two independent groups. Since converted_to_paid is a binary variable (0 or 1), the mean of each group represents the conversion rate, and the t-test can be used to determine whether the difference in means is statistically significant.

---

## 4. Test Results

| Result | Value |
|---|---|
| Control conversion rate | 3.17% |
| Treatment conversion rate | 6.99% |
| Absolute difference | +3.82 percentage points |
| Relative lift | +120% |
| p-value | 0.00053 |
| Significance level (α) | 0.05 |

---

## 5. Decision Rule and Interpretation

**Decision rule:** If p-value < 0.05, reject the null hypothesis.

**Result:** p-value (0.00053) < α (0.05)

**Decision: Reject the null hypothesis.**

The p-value of 0.00053 indicates that there is less than a 0.053% probability of observing a difference of this magnitude between the two groups if the null hypothesis were true. This result is statistically significant at the 0.05 level.

---

## 6. Business Interpretation

The new onboarding campaign more than doubled the paid conversion rate compared to the existing experience — from 3.17% to 6.99%. This improvement is statistically proven and is extremely unlikely to have occurred by chance.

However, statistical significance alone is not sufficient grounds for a launch decision. Guardrail metrics must also be evaluated:

- **Support ticket rate** increased from 14.72% to 24.76% in the Treatment group — a material increase that represents an operational risk post-launch
- **Refund rate** increased from 0.00% to 0.42% — a small increase that should be monitored
- **Average revenue per converted user** declined from 1630 to 770 — this warrants further investigation before concluding that the conversion lift translates directly into equivalent revenue growth

**Connection to business decision:** The hypothesis test provides strong statistical evidence that the new campaign improves conversion. Combined with the guardrail analysis, the recommendation is to launch the campaign with active monitoring of support ticket volume and revenue quality in the first four weeks post-launch.

---

## 7. Limitations

- The t-test confirms statistical association, not causation. External factors during the experiment period cannot be fully ruled out.
- The experiment was conducted over a limited time window. Seasonal variation may affect generalisability.
- The revenue per converted user decline is an unresolved concern that requires further investigation before the full financial impact of the launch can be quantified.
