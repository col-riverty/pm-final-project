# A/B Experiment Brief · Riverty Collection

## Consumer Resolution Velocity · One-Click Payment Plan Setup

### Parameters

| Parameter | Decision |
|---|---|
| **Feature under test** | One-Click Payment Plan Setup |
| **Persona** | Consumers with stable income and opened cases |
| **Moment of Misery** | Consumers abandoning the resolution flow before successfully resolving their issue |
| **Expected outcome** | More eligible consumers successfully set up a payment plan and resolve their issue digitally in the same session |
| **Primary success metric** | Payment-plan flow completion rate, measured as the percentage of eligible consumers who reach the active payment-plan confirmation state |
| **Baseline rate** | 31% Digital Resolution Rate |
| **Target rate** | At least 45% payment-plan flow completion among eligible consumers |
| **Guardrail metric** | Monthly Active Consumers |
| **Guardrail boundary** | No statistically significant decline in Monthly Active Consumers; operational floor: 1,180,000 compared with the current baseline of 1,240,000 |
| **Second guardrail** | Resolution-flow abandonment rate must not increase above the 38% baseline; target is below 25% |
| **Minimum Detectable Effect** | 14 percentage points, from 31% to 45% |
| **Sample size per arm** | 36,200 eligible consumers |
| **Traffic split** | 50% Control / 50% Variant |
| **Test duration** | 30 days |
| **Significance threshold** | p < 0.005 |

## Control vs. Variant

- **Control (A):** Existing self-service resolution experience. Eligible consumers follow the current payment-plan journey with the existing number of steps, current information hierarchy, and current confirmation experience.
- **Variant (B):** One-Click Payment Plan Setup. Eligible consumers see two to three predefined payment-plan options, a complete real-time repayment summary, one explicit confirmation action, and an immediate success screen with the installment amount, next payment date, total repayment, and confirmation reference.
- **Held constant (isolation check):** Persona eligibility rules, opened-case data, available payment-plan values, repayment calculations, contractual wording, traffic source, device mix, support access, and all non-payment-plan portal functionality remain unchanged between Control and Variant.

## Hypothesis

I believe that providing **One-Click Payment Plan Setup** to **consumers with stable income and opened cases** will increase the **payment-plan flow completion rate from 31% to at least 45%**, because eligible consumers can understand, select, and confirm an affordable plan in one mobile-first session without repeated data entry or offline steps.

We expect this improvement to reduce the **resolution-flow abandonment rate from 38% to below 25%**, while protecting **Monthly Active Consumers at or above the operational floor of 1,180,000** throughout the 30-day test.

## Shipping Criteria

We will **ship** if all of the following conditions are met after 30 days:

1. The payment-plan flow completion rate improves from 31% to at least 45%.
2. The result reaches statistical significance at **p < 0.005**.
3. Monthly Active Consumers do not fall below **1,180,000** and show no statistically significant negative movement.
4. Resolution-flow abandonment does not rise above the 38% baseline.
5. No safety failure occurs, including an invented repayment value, mismatched confirmation details, an unsupported eligibility decision, or a false success confirmation.

We will **iterate** if the payment-plan flow completion rate moves positively but remains below the 14-percentage-point MDE, provided both guardrails remain within their boundaries and no safety failure occurs.

We will **kill** the variant if the primary metric shows no improvement or moves negatively, if Monthly Active Consumers breach the operational floor, if resolution-flow abandonment exceeds 38%, or if any financial-data safety failure occurs.

The read date is fixed at the end of the 30-day test. No shipping decision will be made from interim results.

## Experiment Instrumentation

| Event | Trigger | Required properties |
|---|---|---|
| `payment_plan_entry_viewed` | Eligible consumer sees the payment-plan entry point | experiment arm, case reference, device type |
| `payment_plan_option_selected` | Consumer selects a predefined plan | experiment arm, plan ID, installment amount, installment count |
| `payment_plan_confirmation_started` | Consumer selects the confirmation CTA | experiment arm, plan ID, validation status |
| `payment_plan_confirmation_succeeded` | Active-plan success screen is shown | experiment arm, plan ID, confirmation reference |
| `payment_plan_confirmation_failed` | Confirmation returns the predefined failure state | experiment arm, plan ID, failure type |
| `payment_plan_flow_abandoned` | Consumer leaves before confirmation success | experiment arm, last completed step, device type |

## Analysis Notes

- Analyze only consumers who meet the predefined eligibility conditions and have an opened case.
- Use an intention-to-treat comparison based on the initially assigned experiment arm.
- Report the primary result as both percentage-point change and relative change.
- Segment diagnostic results by mobile and desktop, but do not change the primary shipping decision based on a post-hoc segment alone.
- Treat safety failures as zero-tolerance events, independent of statistical lift.
