# A/B Experiment Brief, Riverty business-unit case

## Parameters
| Parameter | Decision |
|---|---|
| Feature under test | One-Click Payment Plan Setup |
| Persona | Consumers with stable income and opened cases |
| Expected outcome | More eligible consumers successfully set up a payment plan and resolve their issue digitally in the same session |
| Primary success metric | Payment-plan flow completion rate, measured as the percentage of eligible consumers who reach the active payment-plan confirmation state |
| Baseline rate | 31% Digital Resolution Rate |
| Guardrail metric | Monthly Active Consumers |
| Guardrail boundary | o statistically significant decline in Monthly Active Consumers; operational floor: 1,180,000 compared with the current baseline of 1,240,000 |
| Second guardrail | Resolution-flow abandonment rate must not increase above the 38% baseline; target is below 25% |
| Minimum Detectable Effect | 14 percentage points, from 31% to 45% |
| Sample size per arm | 36,200 eligible consumers |
| Traffic split | 50% Control / 50% Variant |
| Test duration | 30 days |
| Significance threshold | p < 0.005 |

## Control vs. Variant
- **Control (A):** Existing self-service resolution experience. Eligible consumers follow the current payment-plan journey with the existing number of steps, current information hierarchy, and current confirmation experience.
- **Variant (B):** One-Click Payment Plan Setup. Eligible consumers see two to three predefined payment-plan options, a complete real-time repayment summary, one explicit confirmation action, and an immediate success screen with the installment amount, next payment date, total repayment, and confirmation reference.
- **Held constant (isolation check):** Persona eligibility rules, opened-case data, available payment-plan values, repayment calculations, contractual wording, traffic source, device mix, support access, and all non-payment-plan portal functionality remain unchanged between Control and Variant.

## Hypothesis
> I believe that One-Click Payment Plan Setup for Consumers with stable income and opened cases will result in More eligible consumers successfully set up a payment plan and resolve their issue digitally in the same session, as measured by a 14 percentage points, from 31% to 45% change in Payment-plan flow completion rate, measured as the percentage of eligible consumers who reach the active payment-plan confirmation state within 30 days. We will protect Monthly Active Consumers throughout the test.

## Shipping criteria
> We will **ship** if Payment-plan flow completion rate, measured as the percentage of eligible consumers who reach the active payment-plan confirmation state improves by ≥ 14 percentage points, from 31% to 45% at p < 0.005 and Monthly Active Consumers does not reach o statistically significant decline in Monthly Active Consumers; operational floor: 1,180,000 compared with the current baseline of 1,240,000 after 30 days.
> We will **iterate** if direction is positive but lift is below the MDE.
> We will **kill** if the primary metric shows no improvement or moves negatively.
> The read date is fixed at the end of 30 days, no results reviewed before this date.
