# MI-Nutrition v0.1 (Draft / RFC)

**Status:** proposal. Adopted by no journal, funder, or consortium.  
**Not** a community standard. Filling a record does not move field-level standardization scores.

Machine-readable companion to [STROBE-nut](https://www.strobe-nut.org/), modelled on MIAME. Proposed in:

> Murff, P. (2026). *Diagnosing Standardization Gaps in Nutrition Evidence: The Nine-Layer Framework and the Physics Control Case* (Working Paper v1.4). Zenodo. [10.5281/zenodo.22070406](https://doi.org/10.5281/zenodo.22070406) (concept DOI).

License: [CC BY 4.0](LICENSE).

## What this is

An 18-field StudyRecord schema so a nutrition paper can carry, in tokens:

1. value lane (`prevention` | `treatment` | `reversal` | `other`)
2. study value hypothesis (one decision sentence)
3. typed contrast
4. population fence (structured + summary)
5. composition database **and exact version**, or primary analysis
6. imputation / derivation flag (converges on EuroFIR / FDC; not invented here)

It does **not** replace STROBE-nut, CONSORT, FoodOn, CDNO, EN 16104, or a food-composition MIS. Bind to those. Own the gap they leave: scope + carry-forward of version and imputation into the study record.

Two of the five headline fields are prior art:

| Field | Relationship |
|---|---|
| Imputation flag | exact match intent: EN 16104 / EuroFIR Acquisition–Value–Method Type; USDA FDC `food_nutrient_derivation` |
| Population fence | close match to STROBE Item 21, made structured |

Value-lane typing and the study value hypothesis have no counterpart in the six standards checked in v1.4.

## What this is not

- A score for “how standardized nutrition is”
- A repair of Layer 0 (“a tomato” remains a category)
- A statute or journal policy
- A meal-physiology engine

## Files

| Path | Role |
|---|---|
| [`schema/mi-nutrition.v0.1.schema.json`](schema/mi-nutrition.v0.1.schema.json) | Canonical schema (JSON Schema 2020-12) |
| [`examples/template.v0.1.json`](examples/template.v0.1.json) | Shape only. Placeholders. Do not cite as a study. |
| [`docs/FIELDS.md`](docs/FIELDS.md) | 18-field list vs STROBE-nut |
| [`docs/STATUS.md`](docs/STATUS.md) | Adoption status of *this* artifact, and where it sits in the Nine-Layer stack |
| [`paper/Nine-Layer-Framework-Working-Paper-v1.4.pdf`](paper/Nine-Layer-Framework-Working-Paper-v1.4.pdf) | Working paper this schema is proposed in. Zenodo (concept DOI above) is the citable, versioned record; this copy is for convenience. |

## Conformance

- A field declared with an allowed `absent` / `not_available` / `not_food_study` token is **conforming**.
- An empty string where a required object is expected is **not**.
- Validator output belongs in `conformance` (emitted, not authored).

Levels implied by the schema:

- **core** — required blocks present (`intent`, `population_fence`, `exposure_assessment`, `food_composition`, `outcome`, `fair`)
- **full** — core plus recommended fields (generalizability note, statistical model, code availability, ontology crosswalks)

## Pilot (the next real step)

Extract fields 1–5 and 10–12 from 5–10 published papers. Score each `present` / `free_text_only` / `absent`. Do not grade study quality. That is piloting. Endorsement comes after.

## Cite

```
MI-Nutrition v0.1 (Draft/RFC). Proposed in Murff, P. (2026).
Concept DOI: https://doi.org/10.5281/zenodo.22070406
Schema: https://github.com/murffious/mi-nutrition
```
