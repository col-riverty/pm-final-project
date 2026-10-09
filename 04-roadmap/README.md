# 04-roadmap — Ordnerindex (Modul 4)

Modul 4 der Product-School-Abgabe: **Roadmap, PRD & Prototype**. Offizielle Abgabedateien sind die beiden Lab-Markdowns ohne `_answer`. Die restlichen Dateien sind Arbeitsmaterial (Prompts, HTML/PDF, Screenshots).

**Inhalt dieses Ordners:** Scenario C · Consumer Resolution Velocity (Riverty Collection) — nicht Sipworth. Sipworth (Wasser-Tracking für kalendergebundene Büroarbeit) ist die eigene Initiative fürs Gesamtprojekt; hier wurde das Kurs-Szenario durchgearbeitet.

**Stand:** Lab-Vorlagen leer. Antworten in `*_answer.md`. Artefakte ausgefüllt. Prototype-Link in Lab 2 hinterlegt; Screenshot/Wireframe fehlt in der offiziellen Lab-1-Datei.

---

## Wie die Dateien zusammenhängen

```
Lab 1  Backlog → Scoring-Prompt → Scoring → Roadmap → roadmap-prd-prototype(_answer)
Lab 2  Now-Feature → MoSCoW-Prompt → Scope → PRD (v1/v2) → Prototype-URL → prd-and-prototype(_answer)
```

HTML und PDF mit gleichem Stammnamen sind dasselbe Dokument (Anzeige vs. Druck). Ausnahme: `one_click_payment_plan_prd_v2.pdf` ist byte-identisch mit der v1-PDF, nicht mit der v2-HTML. Zur Roadmap gibt es nur HTML, kein PDF.

---

## Lab 1 — Roadmap & Priorisierung (Deliverable 4)

| Datei | Rolle | Inhalt | Bezug |
|---|---|---|---|
| `roadmap-prd-prototype.md` | Offizielle Abgabe Lab 1. Wird Folie „Roadmap, PRD & Prototype“ im Modul-6-Deck. | **Vorlage.** Abschnitte Roadmap / PRD-Snippets / Prototype leer. | Zielort für den Inhalt aus `_answer` plus Artefakt-Links. |
| `roadmap-prd-prototype_answer.md` | Ausgefülltes Lab-1-Arbeitsblatt. | **Ausgefüllt.** Anker (Persona, Digital Resolution Rate, Abbruch, MAC). Now: C2 Wizard, C3 One-Click Payment, C1 AI Claim Explanation. Cut: C11 Chat, C15 Escalation. | Verweist auf Backlog- und Roadmap-HTML. Menschliche Override weicht leicht von der generierten Scoring/Roadmap ab (dort u. a. C6/C4/C13 in NOW). |
| `consumer_resolution_velocity_backlog.html` | Feature-Backlog C1–C15 plus Themen-Cluster (kein finales Ranking). | **Ausgefüllt.** | Input für Scoring-Prompt und menschliche Quick-Win-Einschätzung. |
| `consumer_resolution_velocity_backlog.pdf` | Druckexport des Backlogs. | **Ausgefüllt**, Inhalt = HTML. | |
| `propmt_roadmap.txt` | Prompt „Senior PM Scoring“ (Effort vs. Value). Dateiname: Tippfehler *propmt*. | **Ausgefüllt.** Anker + Constraints + Featureliste C1–C15. | Wird auf den Backlog angewendet; Output ist die Scoring-Datei. |
| `2026-10-08_Product Management_pm-final-project-main_04_prompt1.png` | Screenshot desselben Scoring-Prompts in der Chat-UI. | **Ausgefüllt** (Prompt-Anfang sichtbar). | Beleg zu `propmt_roadmap.txt`. |
| `consumer_resolution_velocity_scoring.html` | KI-Scoring aller 15 Features (Value/Effort/Quadrant) plus Tiers. | **Ausgefüllt.** Time Sinker: C11, C15. | Quelle für die Roadmap-Lanes. |
| `consumer_resolution_velocity_scoring.pdf` | Druckexport des Scorings. | **Ausgefüllt**, Inhalt = HTML. | |
| `consumer_resolution_velocity_roadmap.html` | Now / Next / Later plus Cut-Liste. | **Ausgefüllt.** NOW u. a. C3, C2, C6, C4, C13, C1. | In der Answer-Datei als Prototype/Roadmap-Screenshot verlinkt. Kein PDF-Zwilling. |

---

## Lab 2 — PRD & Prototype-Sprint

| Datei | Rolle | Inhalt | Bezug |
|---|---|---|---|
| `prd-and-prototype.md` | Offizielle Abgabe Lab 2. Vertieft das Now-Feature aus Lab 1. | **Vorlage.** Alle sechs Felder ungefüllt. | Zielort für `_answer`. |
| `prd-and-prototype_answer.md` | Ausgefülltes Lab-2-Arbeitsblatt. | **Weitgehend ausgefüllt.** Now = Consumer Resolution Velocity; Must = One-Click Payment Plan Setup; Should = Wizard; Won’t = AI Claim Explanation (Genauigkeit). PRD-Lücke vs. Brief: Technical Constraints. Prototype-Lücke: Plan speichern. URL: https://frictionless-cash.lovable.app/ | Verweist auf `one_click_payment_plan_prd.html`. |
| `Prompt_Pick & scope with MoSCoW.txt` | Prompt für MoSCoW-Scope vor dem PRD. | **Ausgefüllt.** MUST C3, SHOULD C2, COULD C6, WON’T C1. | Output: MoSCoW-HTML. |
| `2026-10-08_Product Management_pm-final-project-main_04_prompt2.png` | Screenshot des MoSCoW-Prompts. | **Ausgefüllt** (Prompt-Anfang sichtbar). | Beleg zu `Prompt_Pick & scope with MoSCoW.txt`. |
| `consumer_resolution_velocity_moscow_scope.html` | MoSCoW mit Sub-Requirements (M1–M7 Eligibility bis Mobile, plus Should/Could/Won’t). | **Ausgefüllt.** | Scope-Grenze für das PRD. |
| `consumer_resolution_velocity_moscow_scope.pdf` | Druckexport des Scopes. | **Ausgefüllt**, Inhalt = HTML. | |
| `one_click_payment_plan_prd.html` | Simplified PRD (Product-School-Sample-Look, dunkel). Autor Carlos Olivera, Status Draft. | **Ausgefüllt.** Vision, Metriken, 3 User Stories, 3 Screens, FRs, Constraints, Evals. | In der Answer-Datei als PRD genannt. |
| `one_click_payment_plan_prd.pdf` | Druckexport von PRD v1. | **Ausgefüllt.** | |
| `one_click_payment_plan_prd_v2.html` | Zweite PRD-Fassung, helles Layout, inhaltlich gleich, etwas ausführlicher. | **Ausgefüllt.** | Layout-Variante von v1, nicht ein zweites Feature. |
| `one_click_payment_plan_prd_v2.pdf` | Dateiname legt v2 nahe. | **Identisch mit v1-PDF** (gleicher Hash), nicht Export der v2-HTML. | Für Abgabe die HTML nutzen oder PDF neu erzeugen. |

---

## Für die Abgabe als Nächstes

1. Inhalt aus den `_answer.md` in die offiziellen `.md` übernehmen (die leeren Vorlagen sind die Deliverables).
2. Roadmap-HTML und Prototype-URL dort verlinken; optional Screenshot.
3. Entscheiden, welche PRD-Fassung gilt (v1 visuell näher am Kurs-Sample; v2-PDF nicht verwenden).
4. Bei einem Sipworth-Final: diese Scenario-C-Artefakte ersetzen, nicht als Sipworth-Roadmap einreichen.
