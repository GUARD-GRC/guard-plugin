# AI system fields (GUARD)

## What the person can set (`GUARD:add_ai_system`, `GUARD:update_ai_system`)
| Field | Values |
| --- | --- |
| `name` | required; the name people use for it internally (up to 200 characters) |
| `vendor` | who supplies it (or the company itself) |
| `type` | one of the words GUARD's form offers — llm_chatbot, credit_scoring, hr_screening, recommendation_engine, fraud_detection, medical_diagnosis, code_assistant, image_classifier, other — or a short free-text type |
| `version` | release or deployment label |
| `lifecycle_state` | `development` (pre-pilot, the default), `pilot` (limited rollout), `production` (live), `cessation` (winding down). Retiring is done only in GUARD. |
| `description` | what it does, who it affects, which data it uses, how people oversee it (up to 5,000 characters). More detail means fewer questions in the assessment later. |
| `deployment_footprint` | where it is deployed, or whose customers or users it affects, for example "UAE and EU retail customers" (up to 2,000 characters; set when adding) |

## What GUARD decides (classification, read-only here)
| Field | Values |
| --- | --- |
| risk class | minimal, limited (transparency duties), high (full conformity duties), unacceptable (prohibited use) |
| role | deployer (uses a third-party system), provider (built it or puts it on the market), embedded (AI inside a product the company sells), dual |
| autonomy | a human reviews every output; a human supervises and can step in; autonomous agent |
| impact on people | low, moderate, high (rights, access, livelihood or safety) |
| data categories | personal, sensitive (health), biometric, financial, behavioural or inferred, location |
| regimes | per regulation: Binding, Proposed or Voluntary, with a justification (for example EU AI Act, GDPR, DIFC Regulation 10, UAE PDPL, Saudi PDPL, NIST AI RMF, ISO 42001) |

These values come from the AI-system assessment answers plus GUARD's analysis. Each value carries its reasoning ("why this value"). Only GUARD can change them, through a manual override on the system's page.
