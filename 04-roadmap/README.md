# 04-roadmap — Folder index (Module 4)

Module 4 of the Product School submission: **Roadmap, PRD & Prototype**. Files without `_answer` that still have empty placeholders are **templates — do not fill them in**. The solution lives in the matching `*_answer.md`. Everything else is working material (prompts, HTML/PDF, screenshots).

**What this folder contains:** Scenario C · Consumer Resolution Velocity (Riverty Collection) — not Sipworth. Sipworth (water tracking for calendar-constrained desk work) is the own-initiative product for the overall project; this folder walked through the course scenario.

### Template → solution (do not overwrite the template)

| Template (leave empty) | Solution (filled in) |
|---|---|
| `roadmap-prd-prototype.md` | `roadmap-prd-prototype_answer.md` |
| `prd-and-prototype.md` | `prd-and-prototype_answer.md` |

There are no other empty lab templates in this folder.

---

## How the files relate

```
Lab 1  Backlog → scoring prompt → scoring → roadmap → solution: roadmap-prd-prototype_answer.md
Lab 2  Now feature → MoSCoW prompt → scope → PRD (v1/v2) → prototype URL → solution: prd-and-prototype_answer.md
```

HTML and PDF with the same stem are the same document (on-screen vs. print). Exception: `one_click_payment_plan_prd_v2.pdf` is byte-identical to the v1 PDF, not to the v2 HTML. The roadmap exists as HTML only; there is no PDF twin.

---

## Lab 1 — Roadmap & prioritization (Deliverable 4)

| File | Role | Contents | Relates to |
|---|---|---|---|
| `roadmap-prd-prototype.md` | **Template** Lab 1. Course template for the “Roadmap, PRD & Prototype” slide. | **Empty — do not fill in.** Roadmap / PRD snippets / Prototype sections are placeholders. | Solution: [`roadmap-prd-prototype_answer.md`](roadmap-prd-prototype_answer.md). |
| `roadmap-prd-prototype_answer.md` | **Solution** for Lab 1 (filled worksheet). | **Filled in.** Anchors (persona, Digital Resolution Rate, abandonment, MAC). Now: C2 Wizard, C3 One-Click Payment, C1 AI Claim Explanation. Cut: C11 Chat, C15 Escalation. | Counterpart to template `roadmap-prd-prototype.md`. Points to backlog and roadmap HTML. The human override differs slightly from the generated scoring/roadmap (those put C6/C4/C13 in NOW). |
| `consumer_resolution_velocity_backlog.html` | Feature backlog C1–C15 plus theme clusters (not a final ranking). | **Filled in.** | Input for the scoring prompt and the human quick-win read. |
| `consumer_resolution_velocity_backlog.pdf` | Print export of the backlog. | **Filled in**, same content as the HTML. | |
| `propmt_roadmap.txt` | “Senior PM Scoring” prompt (Effort vs. Value). Filename typo: *propmt*. | **Filled in.** Anchors + constraints + feature list C1–C15. | Applied to the backlog; output is the scoring file. |
| `2026-10-08_Product Management_pm-final-project-main_04_prompt1.png` | Screenshot of the same scoring prompt in the chat UI. | **Filled in** (start of the prompt visible). | Evidence for `propmt_roadmap.txt`. |
| `consumer_resolution_velocity_scoring.html` | AI scoring of all 15 features (value/effort/quadrant) plus tiers. | **Filled in.** Time sinkers: C11, C15. | Source for the roadmap lanes. |
| `consumer_resolution_velocity_scoring.pdf` | Print export of the scoring. | **Filled in**, same content as the HTML. | |
| `consumer_resolution_velocity_roadmap.html` | Now / Next / Later plus cut list. | **Filled in.** NOW includes C3, C2, C6, C4, C13, C1. | Linked from the answer file as the prototype/roadmap screenshot. No PDF twin. |

---

## Lab 2 — PRD & prototype sprint

| File | Role | Contents | Relates to |
|---|---|---|---|
| `prd-and-prototype.md` | **Template** Lab 2. Course template for the Now feature from Lab 1. | **Empty — do not fill in.** All six fields are placeholders. | Solution: [`prd-and-prototype_answer.md`](prd-and-prototype_answer.md). |
| `prd-and-prototype_answer.md` | **Solution** for Lab 2 (filled worksheet). | **Mostly filled in.** Now = Consumer Resolution Velocity; Must = One-Click Payment Plan Setup; Should = Wizard; Won’t = AI Claim Explanation (accuracy). PRD vs. vague brief: technical constraints. Prototype gap: save the payment plan. URL: https://frictionless-cash.lovable.app/ | Counterpart to template `prd-and-prototype.md`. Points to `one_click_payment_plan_prd.html`. |
| `Prompt_Pick & scope with MoSCoW.txt` | Prompt for MoSCoW scope before the PRD. | **Filled in.** MUST C3, SHOULD C2, COULD C6, WON’T C1. | Output: MoSCoW HTML. |
| `2026-10-08_Product Management_pm-final-project-main_04_prompt2.png` | Screenshot of the MoSCoW prompt. | **Filled in** (start of the prompt visible). | Evidence for `Prompt_Pick & scope with MoSCoW.txt`. |
| `consumer_resolution_velocity_moscow_scope.html` | MoSCoW with sub-requirements (M1–M7 eligibility through mobile, plus Should/Could/Won’t). | **Filled in.** | Scope boundary for the PRD. |
| `consumer_resolution_velocity_moscow_scope.pdf` | Print export of the scope. | **Filled in**, same content as the HTML. | |
| `one_click_payment_plan_prd.html` | Simplified PRD (Product School sample look, dark). Author Carlos Olivera, status Draft. | **Filled in.** Vision, metrics, 3 user stories, 3 screens, FRs, constraints, evals. | Named as the PRD in the answer file. |
| `one_click_payment_plan_prd.pdf` | Print export of PRD v1. | **Filled in.** | |
| `one_click_payment_plan_prd_v2.html` | Second PRD version, light layout, same content, slightly more verbose. | **Filled in.** | Layout variant of v1, not a second feature. |
| `one_click_payment_plan_prd_v2.pdf` | Filename suggests v2. | **Identical to the v1 PDF** (same hash), not an export of the v2 HTML. | For submission, use the HTML or regenerate the PDF. |

---

## Notes

- The two templates above stay empty. Read and cite the `*_answer.md` files.
- Decide which PRD version is canonical (v1 is closer to the course sample visually; do not use the v2 PDF).
- For a Sipworth final: replace these Scenario C artifacts; do not submit them as a Sipworth roadmap.
