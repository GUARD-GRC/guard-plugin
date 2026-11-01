# Business profile fields (GUARD)

Fields that `GUARD:update_company_profile` accepts. Send only the fields that change.

| Field | What it holds | Limit |
| --- | --- | --- |
| `company_name` | legal or trading name | 200 characters |
| `website_url` | main website | 500 characters |
| `sector` | industry, in plain words (e.g. "retail banking", "healthcare software") | short text |
| `primary_regulator` | main regulator (e.g. DFSA, CBUAE, FCA, a data protection authority) | short text |
| `jurisdictions` | where the company operates or where its users are: list of codes below | codes only |
| `registered_in` | where the company is registered (incorporated), usually one code below | up to 20 codes |
| `free_text_description` | what the company does, its customers, how it uses or builds AI | 5,000 characters |

## Jurisdiction codes
Map the person's words to these codes and read the mapped list back to them before saving.

| Region | Codes |
| --- | --- |
| Americas | `us` (any state), `us_colorado`, `us_texas`, `us_california`, `ca`, `mx`, `br`, `ar`, `co`, `cl`, `latam_other` |
| Europe | `eu` (any member state), `uk`, `ch`, `europe_other` |
| Middle East | `ae_mainland` (UAE mainland), `ae_difc` (UAE: DIFC), `ae_adgm` (UAE: ADGM), `sa`, `qa`, `bh`, `jo`, `eg`, `me_other` |
| Asia-Pacific | `cn`, `in`, `jp`, `kr`, `sg`, `vn`, `au_nz`, `apac_other` |
| Africa | `za`, `africa_other` |
| None fixed | `global` |

Notes:
- A firm in the DIFC also often serves the UAE mainland. Ask, don't assume.
- "We sell online to EU customers" counts as `eu`. Many EU rules apply wherever the company is based.
- Where the company is registered decides more than where it operates: a law that reaches companies established in a place applies to every AI system when `registered_in` has that place (a personal-data law only to the systems that process personal data), and a regulator document that needs that law is offered without re-classifying (for example the DIFC Reg 10.2.2 attestation and `ae_difc`). A place only in `jurisdictions` is weighed for each system. The privacy notice needs at least one jurisdiction.

## Documents
- PDF only (`.pdf`, real PDF content), up to 20 MB, at most 10 per organisation.
- Good candidates: privacy policy, AI policy, data protection policy, company overview, terms of service, organisation chart.
- GUARD reads them when it writes the profile summary. The summary is what assessments and policies use.
