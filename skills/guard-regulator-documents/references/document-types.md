# Regulator document types (GUARD)

GUARD checks the conditions below before it writes a document. If one fails, GUARD refuses and says why. Show the person the reason with the fix for it.

| `type` | Name | Subject | GUARD writes it when |
| --- | --- | --- | --- |
| `dpia` | Data Protection Impact Assessment | one AI system | a data-protection regime (GDPR, DIFC Regulation 10, UAE PDPL, ADGM Data Protection Regulations 2021, Saudi PDPL) is classified for the system; its risk class is high or limited; at least one personal-data category is recorded |
| `fria` | Fundamental Rights Impact Assessment (EU AI Act Art. 27) | one AI system | the EU AI Act is classified for the system; the organisation is a deployer (or both deployer and provider); the risk class is high |
| `difc_reg_10_2_2` | DIFC Regulation 10.2.2 attestation for automated decision-making | one AI system | DIFC Regulation 10 is classified for the system; the organisation has a DIFC signal (jurisdiction "UAE: DIFC", regulator DFSA, or a designated DIFC code); the system's impact on people is moderate or high |
| `privacy_notice` | Privacy Notice | the company | the business profile has a company name and at least one jurisdiction |
| `ai_transparency_statement` | AI Transparency Statement | the company | the business profile has a company name and at least one jurisdiction; at least one active AI system is registered |

A type GUARD has not switched on yet is refused as not available for now; there is no substitute.

## How to fix a failed condition
- **Regime or risk class missing:** the system needs a finished AI-system assessment; GUARD classifies it when the report is written. If the system was assessed but its details changed since, re-classify it.
- **No data categories:** answer the data-category question in the AI-system assessment.
- **No jurisdictions or no DIFC signal:** add them to the business profile (jurisdictions, primary regulator).
- **No active AI systems:** register at least one system in the AI system inventory.

## Versions
- Once a document of a type exists for a subject, a new one is a new version: pass the current version's `id` as `parent_artefact_id`.
- Earlier versions stay in GUARD, marked `superseded`.

## Where they are used
- Regulator response packs include the current version of each document, with its sign-off state.
- Each document has its own action plan (read with `artefact_id`) and its own sign-off.
