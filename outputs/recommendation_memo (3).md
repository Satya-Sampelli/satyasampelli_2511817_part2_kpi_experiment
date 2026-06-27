# Recommendation Memo — New Onboarding Campaign Experiment

**To:** Leadership Team
**From:** Satya, Business Analyst
**Date:** June 2026
**Subject:** Campaign Experiment Analysis — Launch Decision

---

## 1. Executive Summary

The company conducted a controlled experiment to evaluate whether a new onboarding campaign improves paid conversion performance relative to the existing experience. The experiment ran across 1,408 users split into a Control group (693 users) and a Treatment group (715 users).

The Treatment group demonstrated a statistically significant improvement in paid conversion rate — more than doubling from 3.17% to 6.99%. The result is supported by a p-value of 0.00053, well below the 0.05 significance threshold. All primary funnel metrics improved in the Treatment group. However, the support ticket rate increased materially, which presents an operational risk that must be managed post-launch.

**Recommendation: Launch the campaign to all users, with structured monitoring of support ticket volume and revenue quality for a minimum of four weeks post-launch.**

---

## 2. North Star Metric

**Selected Metric: Paid Conversion Rate**

Paid conversion rate was selected as the North Star metric because it is the most direct measure of whether the new campaign achieves its stated business objective — converting free or trial users into paying customers.

Supporting metrics such as landing page visit rate, trial start rate, and onboarding completion rate provide valuable diagnostic insight but do not independently constitute business success. Revenue is generated only when a user converts to a paid plan. Therefore, paid conversion rate is the primary metric against which the experiment outcome is evaluated.

**Risk of optimising this metric in isolation:** If the campaign drives conversions by pressuring users or creating an overly aggressive experience, it may produce short-term conversion gains while increasing refund rates, churn, and support burden. This is why guardrail metrics were evaluated alongside the primary metric.

---

## 3. KPI Tree Summary

The North Star metric (Paid Conversion Rate) is driven by three primary areas:

**Acquisition Quality**
Determines whether the right users are entering the funnel.
Sub-drivers: Landing page visit rate, traffic source quality, device type mix.

**Onboarding Engagement**
Determines whether users who enter the funnel progress through it effectively.
Sub-drivers: Trial start rate, onboarding completion rate, engagement score.

**Monetization**
Determines the revenue quality of converted users.
Sub-drivers: Average revenue per user, average revenue per converted user, days to convert.

**Guardrail Metrics**
Metrics monitored to detect unintended negative consequences of the campaign.
Guardrails evaluated: Refund rate, support ticket rate, segment-level conversion decline.

---

## 4. Experiment Result Summary

| Metric | Control | Treatment | Change | Direction |
|---|---|---|---|---|
| User Count | 693 | 715 | +22 | — |
| Landing Page Visit Rate | 63.64% | 72.59% | +8.95pp | ↑ Improved |
| Trial Start Rate | 25.11% | 29.09% | +3.98pp | ↑ Improved |
| Onboarding Completion Rate | 15.58% | 21.26% | +5.68pp | ↑ Improved |
| Paid Conversion Rate | 3.17% | 6.99% | +3.82pp | ↑ Improved |
| Avg Revenue Per User | 51.75 | 53.88 | +2.13 | ↑ Improved |
| Avg Revenue Per Converted User | 1,630 | 770 | -860 | ↓ Declined |
| Avg Days to Convert | 8.86 | 6.40 | -2.46 | ↑ Improved |
| Avg Engagement Score | 57.03 | 62.93 | +5.90 | ↑ Improved |
| Support Ticket Rate | 14.72% | 24.76% | +10.04pp | ↓ Risk |
| Refund Rate | 0.00% | 0.42% | +0.42pp | ↓ Monitor |

All primary funnel metrics improved in the Treatment group. The two metrics that moved in an unfavourable direction — support ticket rate and revenue per converted user — require investigation and monitoring post-launch.

---

## 5. Hypothesis Test Interpretation

| Parameter | Value |
|---|---|
| Test type | One-tailed two-sample t-test |
| Null hypothesis | Treatment conversion rate = Control conversion rate |
| Alternate hypothesis | Treatment conversion rate > Control conversion rate |
| Significance level | 0.05 |
| p-value | 0.00053 |
| Decision | Reject the null hypothesis |

The p-value of 0.00053 is substantially below the significance threshold of 0.05. This indicates that the probability of observing a conversion rate difference of this magnitude by random chance alone is less than 0.053%. The improvement in paid conversion rate is statistically significant and is attributed to the new campaign experience rather than random variation.

---

## 6. Guardrail Metric Analysis

**Support Ticket Rate — HIGH CONCERN**
Support tickets increased from 14.72% in Control to 24.76% in Treatment — an increase of over 10 percentage points. This is the most significant risk associated with the campaign. A higher support burden may indicate that the new onboarding experience creates confusion for a segment of users. If unmanaged, this could strain the support function and negatively affect the user experience post-conversion. The support team must be briefed and additional capacity should be arranged prior to launch.

**Refund Rate — LOW RISK, MONITOR**
Refund rate increased from 0.00% to 0.42% in the Treatment group. This represents three users requesting refunds out of 715 in the Treatment group. While the absolute number is small, a non-zero refund rate where none previously existed warrants monitoring. If this rate scales post-launch, it will need investigation.

**Revenue Per Converted User — UNRESOLVED CONCERN**
Average revenue per converted user declined from 1,630 in Control to 770 in Treatment — a reduction of approximately 53%. This finding requires further analysis. Possible explanations include Treatment-converted users selecting lower-tier plans, applying promotional codes, or converting at earlier stages before higher-value decisions are made. This metric should be tracked for 90 days post-launch to determine whether the revenue decline is a structural concern or a short-term effect.

**Days to Convert — POSITIVE SIGNAL**
Treatment users converted in an average of 6.4 days compared to 8.86 days for Control. Faster conversion reduces the risk of user drop-off during the decision period and is a positive outcome of the new campaign.

---

## 7. Segment-Level Insights

**By Region:**
The Treatment group outperformed Control in all four regions. The North region showed the largest conversion lift, with Treatment achieving 8.9% versus Control at 3.4%. No region showed a decline in Treatment performance, which supports a full rollout rather than a regionally selective launch.

**By Device Type:**
Treatment outperformed Control across all device types. Mobile users showed the most significant improvement — Control 2.6% versus Treatment 7.3%. Tablet users also showed strong lift — Control 1.8% versus Treatment 7.1%. Desktop improvement was more moderate — Control 4.5% versus Treatment 6.5%.

**By Traffic Source:**
Treatment outperformed Control across all traffic sources. Referral traffic showed the largest conversion lift in Treatment (11.0% versus 2.5% in Control). Social traffic was the only source where Treatment underperformed Control marginally (6.0% versus 7.7%).

The absence of segment-level declines strengthens the case for a full launch.

---

## 8. Final Recommendation

**Decision: LAUNCH to all users.**

The new onboarding campaign produced a statistically significant improvement in paid conversion rate across all regions, device types, and traffic sources. The primary funnel metrics — landing page visit rate, trial start rate, onboarding completion rate, and engagement score — all improved in the Treatment group. The hypothesis test confirmed that the conversion improvement is genuine and not attributable to random variation.

The support ticket rate increase and the revenue per converted user decline are the two areas of concern. Neither is sufficient to recommend against launch, but both require active monitoring and investigation in the weeks following rollout.

---

## 9. Risks and Limitations

- The support ticket rate increase represents a real operational risk. If ticket volume scales proportionally with a full user base rollout, the support function may be overwhelmed without additional resourcing.
- Revenue per converted user declined significantly in the Treatment group. If this reflects users selecting lower-value plans, the revenue impact of the campaign may be lower than the conversion rate improvement suggests.
- The experiment was conducted over a limited time window. Long-term retention, churn behaviour, and lifetime value of Treatment-converted users are unknown.
- Statistical significance does not imply causation. Factors external to the experiment — such as seasonal trends or concurrent marketing activity — cannot be entirely ruled out.

---

## 10. Recommended Next Steps

1. Brief the customer support team on the anticipated increase in ticket volume prior to launch and arrange temporary capacity increases.
2. Monitor support ticket volume on a weekly basis for the first four weeks post-launch and investigate the most common ticket categories.
3. Track revenue per converted user and plan selection rates for 90 days post-launch to determine whether the revenue decline observed in the experiment persists at scale.
4. Conduct a follow-up analysis at 90 days to assess retention and lifetime value of users acquired through the new campaign versus the existing experience.
5. Consider a targeted follow-up experiment focused on reducing support friction within the new onboarding experience, with the goal of capturing the conversion gains while reducing the support burden.
