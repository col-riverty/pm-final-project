# GTM Strategy & Success Dashboard (Module 6)

## Get your prior work ready
- **The feature you're launching from your M4 PRD, one feature, not a list:** One-Click Payment Plan Setup. The feature enables eligible consumers to select a predefined installment option, review the complete repayment schedule, explicitly confirm it, and receive an immediate success confirmation in one mobile-first session.
- **What your M5 experiment told you shipped / iterating, the evidence behind the launch:** Pre-launch decision pending. The A/B experiment has not yet produced a launch result. The feature will ship only if the Variant achieves the prespecified minimum worthwhile lift in eligible payment-plan completion, does not increase payment-plan abandonment, remains within the engagement guardrail, and produces no critical financial-data safety failure. Until these criteria are met, the feature remains in validation rather than being described as proven or shipped.
- **Your persona pull your M2 persona, this anchors your audience:** Mara, 38, represents consumers with stable income and opened cases who want to resolve their case independently through a simple, trustworthy self-service process. The audience knows action is required but may abandon when the journey is unclear, repetitive, or does not make repayment terms and next steps explicit.

## Set your goal, then your audience
- **Primary GTM goal awareness · engagement · conversion, pick one:** Conversion.
- **Why this goal? what makes this the right goal for this feature right now:** he product problem is not primarily a lack of awareness. Eligible consumers already have an opened case and enter the resolution experience. The commercial and consumer outcome depends on converting more of those eligible consumers from payment-plan entry into a valid active payment-plan confirmation. The current Digital Resolution Rate baseline is 31%, while the prototype target is at least 45%; reducing abandonment from the 38% baseline to below 25% is the supporting diagnostic.
- **Target audience the specific segment your goal implies, be precise:** Eligible consumers with stable income, an opened collection case, and at least one predefined payment-plan option available. The initial audience is consumers entering the experience on mobile or desktop who can complete the agreement digitally without document upload, manual affordability review, or agent intervention.

## Size your launch
- **Launch tier S (minimal) · M (targeted) · L (multi-channel) · XL (full GTM):** M · Targeted launch.
- **Justification reach + revenue impact + what silence would risk:** The feature applies to a defined subset of opened cases rather than the full consumer base, but it directly influences Digital Resolution Rate, payment-plan activation, support demand, and cost per resolved case. A broad consumer campaign would create unnecessary traffic from ineligible consumers. Silence, however, would leave eligible consumers unaware that a shorter resolution path is available and could limit conversion during the launch window.
- **Is this a launch or a release? does it need go-to-market, or can it just ship?:** It is a targeted launch, not only a technical release. The journey changes how eligible consumers make a financial commitment, so the product experience, consumer messaging, Support guidance, measurement, and rollback criteria must be coordinated. It does not require a mass-market campaign.

## Choose your top three channels and plan assets
- **Channel 1 owned / earned / paid, and why it reaches your audience:** Owned ·
 Contextual portal and case-detail messaging. This is the highest-intent channel because it reaches eligible consumers while they are already reviewing an opened case and can immediately enter the payment-plan flow.
- **Channel 2 owned / earned / paid, and why:** Owned  
Triggered email to eligible consumers with an opened case and an available payment-plan option. The message should deep-link to the case entry point and explain that the consumer can review and confirm a plan digitally without contacting Support.
- **Channel 3 owned / earned / paid, and why:** Owned 
Push or in-app reminder for consumers who enter but do not complete the flow. This channel directly addresses the Moment of Misery by returning consumers to an incomplete resolution journey before the case remains unresolved.
- **Enablement & assets what Sales / CS / Support need, plus the assets to build (one-pager, demo, etc.):** Support and Customer Service need a one-page eligibility and troubleshooting guide, annotated screenshots of the three screens, approved responses for ineligible consumers and confirmation failures, and an escalation path for incorrect repayment details. Launch assets should include a short product demo, consumer-facing email and in-product copy, an experiment and KPI dashboard, event definitions, a launch checklist, and a rollback playbook. Sales enablement is limited to a concise overview of the consumer outcome and expected operational impact because this is primarily a self-service consumer feature.

## Make it executable
- **Ownership named owner per key activity, individual, not department:** Carlos Olivera is the accountable Product Owner for launch scope, experiment decision rules, consumer messaging approval, KPI review, and the final ship / iterate / kill recommendation. Engineering implementation owner, QA execution owner, Support-readiness owner, and Legal / Compliance approver must be assigned by name before launch; they are currently not specified in the available context and therefore remain launch blockers.
- **Budget & resource gaps what costs extra, and any asset you can't currently build:** The core product work must fit the established team of three developers and one QA working in two-week sprints. Additional effort may be required for production-grade eligibility integration, contractual and compliance review, localized consumer copy, email or push orchestration, analytics instrumentation, dashboard implementation, and Support training. The high-fidelity prototype explicitly excludes production APIs, authentication changes, real payment processing, persistent storage, document upload, and AI-generated explanations; these cannot be represented as launch-ready capabilities without separate scope and resources.
- **Timeline Phase 1 beta → Phase 2 launch moment → Phase 3 post-launch:** Phase 1 · Controlled beta: 
Validate instrumentation, financial-data consistency, eligibility handling, mobile usability, error recovery, and Support readiness with a restricted share of eligible traffic. Confirm that no false success state, incorrect installment amount, changed total repayment, or unsupported eligibility decision occurs.

Phase 2  
Targeted launch: Expand to the predefined eligible audience using contextual portal messaging and triggered lifecycle communication. Maintain the agreed Control / Variant allocation if the A/B test is still running; do not combine the experiment readout with an uncontrolled rollout.

Phase 3  
Post-launch: Review payment-plan completion, abandonment, engagement guardrails, confirmation errors, and Support contacts at the fixed decision point. Apply the prespecified ship, iterate, kill, or rollback rule rather than changing thresholds after seeing results.

## Define how you'll know it worked
- **Success metrics 2 to 3 metrics that match your GTM goal:** 1. Eligible payment-plan completion rate: Primary conversion metric. Baseline 31%; prototype target at least 45%, subject to the final prespecified experiment MDE and significance rule.

2. Payment-plan flow abandonment rate: Moment-of-Misery metric. Baseline 38%; target below 25%, with no increase versus Control.

3. Engagement guardrail: Monthly Active Consumers or, preferably, eligible-consumer return rate. The metric must not breach its prespecified non-inferiority boundary. The previously used operational MAU floor is 1,180,000 against a current baseline of 1,240,000.
- **Bad signal to watch for e.g. high reach, zero signups = message-market mismatch:** High entry-point reach or email click-through combined with unchanged completion and elevated abandonment indicates that messaging is creating intent but the payment-plan journey is still too difficult or unclear. A rise in confirmation errors, Support contacts, ineligible entries, or mismatched repayment details is a stronger negative signal than reach and requires investigation or rollback. Any false success confirmation or incorrect financial value is a zero-tolerance safety failure.
- **Most likely post-launch decision double-down · iterate · pivot · deprioritize, and what would trigger it:** Double-down: 
Completion reaches the prespecified business threshold and statistical rule, abandonment does not increase, the engagement guardrail remains within bounds, and no critical safety failure occurs. Expand eligible traffic and optimize the highest-performing owned channel.

Iterate: 
Completion improves but remains below the minimum worthwhile effect, or completion meets the target while a non-critical journey guardrail worsens. Use funnel events and usability findings to revise the plan-selection, summary, or confirmation experience before broader rollout.

Pivot: 
Consumers enter the flow but do not progress beyond plan selection, indicating that the available option design or affordability proposition does not match the persona's needs. Revisit the resolution proposition rather than adding more promotion.

Deprioritize or roll back: 
Completion is neutral or negative, abandonment increases materially, the engagement boundary is breached, instrumentation is unreliable, or any critical financial-data safety failure occurs.
