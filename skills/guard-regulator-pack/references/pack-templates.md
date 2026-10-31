# Regulator pack templates (GUARD)

Pass the `template` value to `GUARD:build_regulator_pack`; without one GUARD uses the template it suggests for the organisation (`suggested_template`, with its `suggestion_reason`). Every item of the template is included unless the person leaves it out: pass its key in `leave_out`. The item keys of each template come from `GUARD:list_regulator_packs`: its `templates`, each with its `items` and its `use_for` (the regulators or requests it serves). Things the organisation will hand over itself go in `extra_items` (up to 10, 200 characters each).

## What each row source means
- **Register:** active AI systems and their classification. Retired systems are kept in the history.
- **Policies:** approved policies are included in full. Others are listed as pending.
- **Assessments:** finished assessments, with the full reports in an appendix.
- **Regulator documents** (privacy notice, AI transparency statement, DPIA, FRIA, DIFC 10.2.2): the current version of each, with its sign-off state. A missing document shows as "not yet generated".
- **Purpose mapping:** drawn from the DPIAs and the per-regulation classification. GUARD holds no separate record of processing (ROPA); the organisation supplies its own if the regulator asks for one.
- **Accountability:** active members and the approval mode (single or dual).
- **Audit trail:** consequential governance events over the last 12 months: sign-offs, plan completions, overrides, ownership changes.
- **Supplied by the organisation:** GUARD lists these rows. The organisation provides them from its own systems.

## Templates

| Template | Use for | Typical rows (supplied by the organisation in italics) |
| --- | --- | --- |
| `difc_information_request` | DFSA or DIFC Commissioner of Data Protection information request (there is no separate DFSA template) | privacy notice, AI transparency statement, register, policies, assessments, DPIAs, DIFC 10.2.2 attestations, purpose mapping, accountability, audit trail, *system design, data flows, DSAR logs* |
| `generic_regulator_request` | any regulator without its own template, or an internal or external audit | privacy notice, AI transparency statement, register, policies, assessments, DPIAs, FRIAs, purpose mapping, accountability, audit trail, *system design, data flows, DSAR logs* |
| `eu_ai_act_market_surveillance` | EU AI Act market-surveillance authority | register, AI transparency statement (Art. 50), FRIAs (Art. 27), DPIAs, assessments, policies, purpose mapping, accountability, audit trail, *technical documentation (Annex IV), instructions for use (Art. 13), system design, data flows* |
| `gdpr_sa_request` | GDPR supervisory authority | privacy notice (Arts. 13–14), DPIAs (Art. 35), records of processing / purpose mapping (Art. 30), automated decision-making transparency (Art. 22), register, policies, assessments, accountability (Art. 24), audit trail, *DSAR logs, processor agreements (Art. 28), data flows* |
| `uae_pdpl_request` | UAE Data Office (PDPL) | privacy notice, register, DPIAs, automated-processing transparency, policies, assessments, purpose mapping, accountability, audit trail, *DSAR logs, cross-border transfer safeguards, data flows* |
| `cbuae_request` | Central Bank of the UAE AI/ML model inquiry | AI/ML model register, model and AI risk assessments, model risk and AI governance policies, AI transparency statement, DPIAs, purpose mapping, accountability, audit trail, *model validation and back-testing, system design, data flows* |

## Readiness rules of thumb
- Policies count in full only when approved. Send drafts for sign-off before building the pack.
- A DPIA or FRIA row is empty until GUARD has written one for the relevant systems.
- An unassessed AI system shows as registered but not classified.
