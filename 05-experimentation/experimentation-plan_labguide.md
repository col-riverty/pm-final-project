# Experimentation Plan (Module 5)

## Get your documents ready
- **From M3, your hypothesis sentence:** based on consumer_resolution_velocity_backlog.html i see my quick wins in AI Claim Explanation, Guided Resolution Wizard at first to decrease the consumer abandoning resolution afterwards i want simply the process bei introduicnt a One-Click Payment Plan Setup followed by Personalized Resolution Recommendations
- **From M3, your primary success metric & guardrail metric:** primary metric: Digital Resolution Rate
Guardial Metric: Monthly Active Consumers
- **From M4, the feature you scoped in your PRD this is what you're testing:** based on consumer_resolution_velocity_backlog.html i see my quick wins in AI Claim Explanation, Guided Resolution Wizard at first to decrease the consumer abandoning resolution afterwards i want simply the process bei introduicnt a One-Click Payment Plan Setup followed by Personalized Resolution Recommendations

## Define your experiment parameters
- **Feature under test pull from your M4 PRD:** One-Click Payment Plan Setup
- **Persona pull your M2 persona:** Consumers with stable income and opened cases
- **Expected outcome the behaviour change you expect, from your M3 hypothesis:** More eligible consumers successfully set up a payment plan and resolve their issue digitally in the same session
- **Primary success metric the one number that defines success, from M3:** Payment-plan flow completion rate, measured as the percentage of eligible consumers who reach the active payment-plan confirmation state
- **Baseline rate today's rate of your primary metric, from your M3 data:** 31% Digital Resolution Rate
- **Guardrail metric & boundary what must not break, and how far it can move before you investigate:** No statistically significant decline in Monthly Active Consumers; operational floor: 1,180,000 compared with the current baseline of 1,240,000
- **Minimum Detectable Effect (MDE) the smallest improvement worth shipping, your floor:** 14 percentage points, from 31% to 45%
- **Sample size per arm use the calculator in the builder, baseline + MDE:** 36,200 eligible consumers
- **Traffic split & test duration 50/50 standard · cover ≥ 2 weekly cycles:** 50% Control / 50% Variant
- **Significance threshold p < 0.05 is standard, explain any deviation:** p < 0.005

## Define your control and variant
- **Control (A) the current experience, reference your M2 moment of misery and M3 funnel/workflow data:** Existing self-service resolution experience. Eligible consumers follow the current payment-plan journey with the existing number of steps, current information hierarchy, and current confirmation experience.
- **Variant (B) your single change, copy the relevant screens & functional requirements from your M4 PRD:** One-Click Payment Plan Setup. Eligible consumers see two to three predefined payment-plan options, a complete real-time repayment summary, one explicit confirmation action, and an immediate success screen with the installment amount, next payment date, total repayment, and confirmation reference.
- **Isolation check, what has NOT changed? list everything identical between arms (app version, recommendation engine, notifications, onboarding). If something changed inadvertently, your test is compromised.:** Persona eligibility rules, opened-case data, available payment-plan values, repayment calculations, contractual wording, traffic source, device mix, support access, and all non-payment-plan portal functionality remain unchanged between Control and Variant.

## Formalize your hypothesis & shipping criteria
- **Your hypothesis (filled in):** I believe that providing One-Click Payment Plan Setup to consumers with stable income and opened cases will increase the payment-plan flow completion rate from 31% to at least 45%, because eligible consumers can understand, select, and confirm an affordable plan in one mobile-first session without repeated data entry or offline steps.

We expect this improvement to reduce the resolution-flow abandonment rate from 38% to below 25%, while protecting Monthly Active Consumers at or above the operational floor of 1,180,000 throughout the 30-day test.
- **Your shipping criteria (filled in):** We will ship if all of the following conditions are met after 30 days:

The payment-plan flow completion rate improves from 31% to at least 45%.
The result reaches statistical significance at p < 0.005.
Monthly Active Consumers do not fall below 1,180,000 and show no statistically significant negative movement.
Resolution-flow abandonment does not rise above the 38% baseline.
No safety failure occurs, including an invented repayment value, mismatched confirmation details, an unsupported eligibility decision, or a false success confirmation.
- **Hardest parameter to define, and did it change your hypothesis? quick debrief:** Event	Trigger	Required properties
payment_plan_entry_viewed	Eligible consumer sees the payment-plan entry point	experiment arm, case reference, device type
payment_plan_option_selected	Consumer selects a predefined plan	experiment arm, plan ID, installment amount, installment count
payment_plan_confirmation_started	Consumer selects the confirmation CTA	experiment arm, plan ID, validation status
payment_plan_confirmation_succeeded	Active-plan success screen is shown	experiment arm, plan ID, confirmation reference
payment_plan_confirmation_failed	Confirmation returns the predefined failure state	experiment arm, plan ID, failure type
payment_plan_flow_abandoned	Consumer leaves before confirmation success	experiment arm, last completed step, device type
