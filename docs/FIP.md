# FAIR Implementation Profile — MI-Nutrition v0.1

Not a GO FAIR M4M submission, not a FAIR score, not an 11th layer. A checklist for
what this repo already does, so a stranger can see the choice instead of inferring it.

| Principle | This repo's choice |
|---|---|
| F (Findable) | GitHub repo `murffious/mi-nutrition` + concept DOI `10.5281/zenodo.22070406`; `README.md` and `docs/STATUS.md` as metadata |
| A (Accessible) | Schema and docs are public, no login (A1.2 not invoked); if the repo disappears the DOI record does not |
| I (Interoperable) | JSON Schema 2020-12; ontology crosswalks bind to **FoodOn** / CDNO / SEPIO (field 18) rather than inventing new terms |
| R (Reusable) | License **CC BY 4.0** (`LICENSE`); imputation field (12) is an exact-match crosswalk to EN 16104 / EuroFIR Acquisition–Value–Method Type, not a new code list; companion to **STROBE-nut**, not a replacement |

No validator is published yet (see `STUDY.md` in `fdp-1` / `biology_as_code`) — F and A cover the schema file, not a runnable check. Do not read this table as F-UJI-scored or as adoption.
