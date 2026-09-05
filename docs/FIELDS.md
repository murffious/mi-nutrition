# MI-Nutrition v0.1 fields

18 fields. 14 required in the tracker sheet; schema `required` keys are the six top-level blocks plus version and study_id.

| # | Field | Required | In STROBE-nut? | Notes |
|---|---|---|---|---|
| 1 | Value lane | yes | no | prevention / treatment / reversal / other |
| 2 | Study value hypothesis | yes | no | decision sentence, not the scientific hypothesis |
| 3 | Typed contrast | yes | partial | machine-readable contrast type |
| 4 | Inclusion / exclusion | yes | yes (STROBE 6 + nut-6) | structured `Criterion` objects |
| 5 | Population fence summary | yes | no (STROBE 21 is free text) | declarative fence |
| 6 | Generalizability note | recommended | partial | who *not* to apply to |
| 7 | Assessment method + version | yes | yes (nut-1, nut-8.1) | bare instrument name fails |
| 8 | Portion-size & administration | yes | yes (nut-8.1) | |
| 9 | Supplement handling | yes | partial | assessed + inside totals? |
| 10 | Composition DB + exact version **or** primary analysis | yes | partial (nut-8.2) | `"USDA"` alone fails |
| 11 | Matching & conversion | yes | yes (nut-8.2) | |
| 12 | Imputation / derivation flag | yes | no | EuroFIR / FDC codes; do not reinvent |
| 13 | Primary endpoint type | yes | partial | |
| 14 | Effect estimate + precision | yes | partial | |
| 15 | Statistical model | recommended | yes | |
| 16 | Data availability | yes | partial (nut-22.2) | |
| 17 | Code / protocol availability | recommended | partial | |
| 18 | Ontology crosswalks | recommended | no | bind FoodOn/CDNO/SEPIO; do not compete |

Methods-only or composition-only studies: use `value_lane` = `other` and `value_lane_other` until v0.2 adds `method_only` / `composition_only` to the enum.
