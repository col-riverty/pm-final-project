# Senior PM Review: A/B Experiment Brief

## Scenario

**Riverty business-unit case · One-Click Payment Plan Setup**

## Senior PM Verdict

> **Do not launch this brief unchanged.** The hypothesis is directionally strong, but the variant bundles multiple experience changes, the guardrail is underspecified, and the proposed sample of **36,200 per arm** appears drastically oversized for detecting a move from **31% to 45%**.

---

## 1. Is the Variant Exactly One Change?

### Finding: No, it bundles at least four changes

The variant simultaneously introduces:

1. Two to three predefined plan options
2. A real-time repayment summary
3. A simplified, explicit confirmation action
4. An immediate, enriched success screen

That creates an **attribution problem**. If completion improves, you will know that the new end-to-end experience worked, but not which component caused the improvement.

### Recommendation

Decide what kind of experiment this is.

#### Option A: Test the Complete Experience

Use this if the shipping decision is binary: replace the existing journey with the complete One-Click experience or do not replace it.

Rename the intervention clearly:

> **Bundled end-to-end payment-plan journey redesign**

This is valid, but you must not claim that “one-click confirmation” alone caused any lift.

#### Option B: Isolate the Core Hypothesis

Preferred if you want actionable learning.

- **Control:** Existing payment-plan experience.
- **Variant:** Same eligibility logic, options, summary, and success screen as Control, but with the existing confirmation sequence replaced by one explicit confirmation action.

Then test the other components in later experiments.

### Senior PM Recommendation

For a high-fidelity prototype, test the complete journey. For a production A/B test, isolate the confirmation and step-reduction change wherever technically feasible.

---

## 2. Does the Primary Metric Measure the Moment of Misery?

### Finding: Partially

**Payment-plan flow completion rate** measures the desired final outcome. It tells you whether eligible consumers reached active confirmation.

But the Moment of Misery is:

> Consumers abandoning the resolution flow.

Completion and abandonment are related, but not identical. A completion increase could coexist with unchanged abandonment if, for example:

- more users enter the flow;
- some users take longer but eventually complete;
- traffic quality changes;
- consumers leave through an alternative route.

### Recommended Metric Hierarchy

#### Primary Metric

> **Eligible payment-plan completion rate:** Percentage of eligible, assigned consumers who reach a valid active payment-plan confirmation state within the defined experiment window.

Use assigned eligible consumers as the denominator, not only consumers who select a plan. This avoids excluding people who abandon early.

#### Key Secondary Metric

> **Payment-plan abandonment rate:** Percentage of eligible consumers who enter the payment-plan flow but leave without reaching valid confirmation within the defined abandonment window.

#### Diagnostic Funnel

Track progression through:

- Entry point viewed
- Plan selected
- Confirmation started
- Confirmation succeeded
- Confirmation failed
- Flow abandoned

This reveals where the variant removes friction.

---

## 3. Is the Primary Metric Distinct From the Guardrail?

### Finding: Yes conceptually, but the guardrail is not operationally defined

The distinction is valid:

- **Primary metric:** Payment-plan flow completion
- **Guardrail:** Monthly Active Consumers

However, Monthly Active Consumers may be too broad and slow-moving to protect this particular journey. A payment-plan experiment may affect only a small fraction of total monthly users, so even a harmful experience might not visibly move organization-wide MAU.

### Define MAU Precisely

Specify:

- eligible population or whole portal;
- unique-user definition;
- calendar or rolling-month calculation;
- allowed decrease;
- statistical rule;
- treatment-window handling.

### Add a Local Guardrail

Use one guardrail close to the intervention:

> **Support-contact-after-flow rate must not increase.**

Or:

> **Confirmation-error rate must remain below a predefined threshold.**

For this financial journey, also use a zero-tolerance safety guardrail:

- no incorrect installment amount;
- no mismatched repayment total;
- no unsupported eligibility outcome;
- no false success confirmation.

### Recommended Guardrail Set

1. **Engagement guardrail:** Eligible-consumer return rate or eligible-population MAU
2. **Journey guardrail:** Support-contact-after-flow rate or confirmation-error rate
3. **Safety guardrail:** Zero invalid financial confirmations

---

## 4. Is the Sample Size and Duration Realistic?

### Finding: The proposed sample is almost certainly oversized for the stated MDE

A two-proportion experiment requires the baseline rate, target rate, significance level, and statistical power. Using:

- **Baseline:** 31%
- **Target:** 45%
- **Absolute MDE:** 14 percentage points
- **Two-sided alpha:** 0.005
- **Equal allocation:** 50% / 50%

The approximate requirement is:

| Statistical power | Approximate sample per arm |
|---|---:|
| 80% | 319 |
| 90% | 400 |

The proposed **36,200 per arm** is more than 90 times the approximate 90%-power requirement for that large effect.

### Important Caveat

The exact requirement can increase because of:

- repeated exposure or non-independent observations;
- variance adjustment;
- attrition;
- sample-ratio imbalance;
- sequential testing;
- multiple comparisons;
- cluster randomization;
- imperfect event capture.

But none of those factors normally explains a jump from roughly 400 to 36,200 per arm without an additional unstated assumption.

### Duration Feasibility

To gather 36,200 consumers per arm in 30 days, you need:

- **72,400 eligible consumers in total**
- approximately **2,414 eligible consumers per day**

The information provided does not establish whether that traffic exists. Therefore, the 30-day duration is not yet justified.

### Required Correction

Add the missing power assumption and recompute sample size using:

- baseline;
- minimum worthwhile effect;
- significance threshold;
- statistical power;
- unit of randomization;
- expected eligible daily traffic;
- expected exclusions or data loss.

### Strategic Challenge

A 14-point MDE is extremely ambitious relative to a 31% baseline. It represents roughly a **45% relative lift**.

Ask:

> Would we reject the feature if it increased completion from 31% to 38%?

If the answer is no, then 14 points is not the real minimum worthwhile effect. Set the MDE to the smallest lift that would genuinely justify shipping, then recalculate the sample.

---

## 5. Are the Shipping Criteria a Real Decision Rule?

### Finding: Not yet

The current logic leaves several ambiguities:

- whether the test is one-sided or two-sided;
- required statistical power;
- what “protect MAU” numerically means;
- whether abandonment is a formal guardrail;
- how safety failures affect the decision;
- treatment of sample-ratio mismatch;
- treatment of missing events;
- whether the decision uses absolute or relative lift;
- whether reaching 45% is required, or merely beating Control significantly.

## Rewritten Decision Rule

### Ship

Ship the variant only if, at the fixed 30-day read:

1. At least the prespecified valid sample has been collected in both arms.
2. No sample-ratio mismatch or material instrumentation defect invalidates the experiment.
3. Variant payment-plan completion exceeds Control by at least the prespecified absolute MDE.
4. The primary result meets the prespecified two-sided threshold of `p < 0.005`.
5. Payment-plan abandonment does not exceed Control.
6. The defined engagement guardrail does not breach its prespecified non-inferiority boundary.
7. No critical financial-data safety failure occurs.

### Iterate

Iterate if:

- the primary result is positive and statistically significant but below the business MDE;
- or it meets the MDE but misses the significance threshold;
- or completion improves while a non-critical journey guardrail deteriorates;
- and no critical safety failure occurs.

A positive direction alone is insufficient.

### Kill

Kill the variant if any of these occurs:

- completion is neutral or negative;
- abandonment increases materially;
- the engagement guardrail breaches its boundary;
- support contact or confirmation errors exceed the predefined threshold;
- a critical safety failure occurs;
- instrumentation or sample-ratio issues make the result uninterpretable.

### Extend Without Reading

Extend the collection period only if:

- the predetermined sample has not been reached;
- the experiment remains operationally safe;
- no outcome data have been reviewed by the decision-makers;
- the maximum extension rule was defined before launch.

Do not extend merely because the observed result is inconclusive.

---

# Recommended Launch-Ready Hypothesis

> We believe that replacing the existing payment-plan journey with the One-Click Payment Plan Setup experience for eligible consumers with stable income and opened cases will increase the proportion of assigned eligible consumers who reach a valid active payment-plan confirmation state. We will compare the Variant with the existing self-service journey using a prespecified two-sided test at `p < 0.005`. We will ship only if the Variant achieves the prespecified minimum worthwhile absolute lift, does not increase payment-plan abandonment, remains within the engagement guardrail, and produces no critical financial-data safety failure.

## Final Assessment

| Area | Assessment |
|---|---|
| Variant isolation | **Needs revision** |
| Primary metric | **Good outcome metric, but add abandonment** |
| Guardrail separation | **Conceptually correct, operationally vague** |
| Sample size | **Likely heavily oversized** |
| Duration | **Unproven without eligible traffic data** |
| Shipping criteria | **Needs hard numerical boundaries** |
| Launch readiness | **Not ready until these points are resolved** |
