# Status of this repository

as_of: 2026-09-05  
schema: v0.1  
lifecycle: living Draft/RFC

| ID | Element | Status |
|---|---|---|
| N01 | MI-Nutrition checklist | Proposed (this repo) |
| N07 | JSON Schema | Proposed (schema file in this repo) |
| N02–N06 | Required scope/provenance fields | Specified here; not started in journals |
| N08 | FoodOn / CDNO / SEPIO binding | Conceptual only |
| N09 | Journal companion submission | Not started |
| N10 | Funder nudge | Not started |

Piloting: **0 papers extracted**.

This table is first-party. It is not an endorsement by USDA, ASN, NIH, FoodOn, or any journal named as a *target*.

Do not treat GitHub stars or citations of the working paper as adoption.

## Where MI-Nutrition sits in the Nine-Layer Stack

MI-Nutrition is **not** a score for the stack. It is a **record format** that sits on three layers and leaves the rest alone.

The working paper (v1.4) argues the StudyRecord is the keystone because it moves **L4, L7, and L9** together. That is the whole fit.

### Where it plugs in

```text
L0 measurand           — not repaired (tomato stays a category)
L1 method               — only *named* (instrument + version)
L2 identity              — only *bound* if you add FoodOn (field 18, recommended)
L3 vocabulary/data   — version string carried; databases stay plural
L4 study record       — THIS IS THE OBJECT
L5 reporting            — companion to STROBE-nut, not a replacement
L6 synthesis            — unused; GRADE still separate
L7 scope / translation — fence + lane + decision sentence
L8 governance           — adoption path only (journal/repo), not a statute
L9 traceability         — carry-forward of DB version + imputation
```

Measurement stratum (L0–L1) is upstream of this schema. Judgment of evidence quality (L6) is downstream of it. MI-Nutrition is the envelope in between.

### Field → layer

| MI-Nutrition field | Layer it serves | What it does |
|---|---|---|
| 1 Value lane | L7 | Stops pooling prevention with reversal |
| 2 Study value hypothesis | L7 | Names the decision, so the result is not reused for another question |
| 3 Typed contrast | L7 / L4 | Makes the comparison a token, not a paragraph |
| 4–5 Population fence | L7 | Scope bound to the estimate (STROBE-21 made structured) |
| 6 Who *not* to apply to | L7 | Optional extra fence |
| 7–9 Assessment method, portions, supplements | L1 (named in the record) | Does not validate the assay |
| 10 DB + exact version *or* primary analysis | L3 → L4 | The missing hop from compiler to study |
| 11 Matching / conversion | L4 | How foods hit table rows |
| 12 Imputation flag | L9 | EuroFIR/FDC origin carried into the study |
| 13–15 Endpoints, estimate, model | L4 / L5 | Results in the same record as scope |
| 16–17 Data/code | L4 / L5 | Reuse |
| 18 Ontology crosswalks | L2 / L3 | Bind FoodOn; do not replace them |

The five fields the paper treats as required for the argument are **10, 12, 5, 1, 2** — version, imputation, fence, lane, decision. Those are L4 + L7 + L9.

### What it cannot do, by design

| Layer | Why MI-Nutrition does not "fix" it |
|---|---|
| L0 | A schema cannot turn "a tomato" or "dietary fibre = whatever the assay says" into an SI measurand. This is the ceiling; no record format repairs it. |
| L2 | Generic unbranded food still has no required ID. Field 18 can *point* at FoodOn. Uptake of that ID is still the field's problem. |
| L6 | GRADE / certainty is a different object. Lane typing stops illegal pooling; it does not grade the body of evidence. |
| L8 | Putting the schema on GitHub is not a journal gate. N09 (journal companion submission) is later. |

The compounding principle still holds: a perfectly filled MI-Nutrition record of an undefined measurand is a well-packaged ambiguous quantity.

### Two pieces of "nutrition," one checklist

| Piece | Layers | Role of MI-Nutrition |
|---|---|---|
| What is the food? | L0–L4, L9 | Names the table, version, derivation, matching. Does not analyze the food itself. |
| How it hits the body | Meal-physiology stages, not a chart layer | Out of scope. Absorption, transit, downstream metabolism are not checklist fields. |
| Hinge | L7 | Fence + lane + decision: *this* food/exposure, *this* host class, *this* question. |

This is why a meal-physiology completeness score and a standardization chart must not share a number, and why MI-Nutrition belongs with the record/judgment strata, not with a physiology engine.

### What "adoption" would mean on the stack

Score = existence **and** uptake, not existence alone.

| Event | Layers that may move *later* | What does **not** move |
|---|---|---|
| Schema published (this repo) | none | Existing per-layer scores are unaffected |
| 5–10 papers extracted (pilot) | still none | Evidence for N01 only |
| One journal *gates* on the companion file | L4, L5, L7, L9, maybe | Only after the gate is real |
| Compilers' derivation flags survive into those records | L9 | L0 unchanged |

MI-Nutrition fits as a proposed joint fix for three lowest-scoring *format* layers a study record can touch. It is not the stack, and publishing it does not move any layer's score.
