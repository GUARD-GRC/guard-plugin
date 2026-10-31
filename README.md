# GUARD GRC plugin

The GUARD GRC plugin brings GUARD's AI-governance workflows into Claude. Each skill is a step-by-step playbook that works through the GUARD connector (https://guard.aigovernance.ae/mcp) with your own GUARD login, so every answer comes from your GUARD organisation and GUARD's regulation library. Version 2.0.0.

## Skills

- **Build my AI system inventory** (`guard-ai-inventory`): Builds and maintains an organisation's AI system inventory in GUARD through the GUARD connector, and explains GUARD's classification of each system.
- **Set up my business in GUARD** (`guard-business-setup`): Sets up or updates an organisation's business profile in GUARD through the GUARD connector, covering company details, jurisdictions, company PDFs and GUARD's profile summary, saving each detail to GUARD as soon as the person confirms it.
- **Close my gaps** (`guard-close-gaps`): Closes an organisation's assessment gaps in GUARD through the GUARD connector by having GUARD write a policy for chosen gaps, then working its implementation plan (action items, owners, deadlines, status) to completion.
- **Run a guided assessment** (`guard-guided-assessment`): Runs a guided GUARD assessment through the GUARD connector, one question at a time, for the whole company or for one AI system, and GUARD's own guided company setup (the business profile by questions), with GUARD saving each answer as it is given, then reads GUARD's report, gaps and duty coverage.
- **My GUARD to-dos** (`guard-my-todos`): Shows what is waiting on the person in GUARD through the GUARD connector (sign-offs to approve or review, action items assigned to them, regulatory updates to acknowledge), requests or withdraws sign-offs, and prepares an approval or rejection that the person confirms on a GUARD page with a fresh authenticator code.
- **Ask GUARD about a regulation** (`guard-regulation-questions`): Answers questions about AI and data-protection regulations from GUARD's regulation library through the GUARD connector, quoting provisions in full and checking scope exclusions before saying a law applies.
- **Prepare regulator documents** (`guard-regulator-documents`): Prepares regulator documents in GUARD through the GUARD connector, written by GUARD from what it already holds about the organisation and its AI systems (a DPIA, a FRIA, a DIFC Regulation 10.2.2 attestation, a privacy notice or an AI transparency statement), each versioned with its own plan and sign-off.
- **Prepare for a regulator** (`guard-regulator-pack`): Prepares an organisation for a regulator request in GUARD through the GUARD connector by checking readiness, building a regulator response pack (one PDF of the register, approved policies, assessments, regulator documents, accountability and a 12-month audit trail) from one of six templates, reading what a pack contains, or reading the AI governance register as data.
- **What changed for us** (`guard-what-changed`): Reports what changed in AI and data-protection regulation for an organisation, from the regulatory changes GUARD has reviewed and published and which of its AI systems each one affects, plus GUARD's daily AI-governance news, through the GUARD connector, and records the person's acknowledgement of a change they have read.

## What you need

- A GUARD account with two-factor sign-in, in an organisation whose plan includes the GUARD connector.
- The GUARD connector added to your assistant. A plugin does not add its connector by itself in claude.ai: an organisation owner adds it under Organization settings → Connectors, and each member then signs in with their own GUARD login.
- In claude.ai, skills need "Code execution and file creation" switched on.

## Install

- **Claude Code:** `claude plugin marketplace add GUARD-GRC/guard-plugin`, then `claude plugin install guard-grc@guard-plugin`. In Claude Code the workflows come only with this plugin: GUARD does not add its own menu entries there, so with the connector alone you get GUARD's tools but not the nine workflows.
- **Claude Team or Enterprise:** the owner uploads the plugin (Organization settings → Plugins & skills) and adds the GUARD connector (Organization settings → Connectors).
- **Claude Pro or Max:** add the GUARD connector, then upload each skill's ZIP under Customize → Skills.

The skills never delete anything in GUARD, never ask for your two-factor code, and treat text from GUARD as data, not instructions. Approvals and uploads are finished on GUARD's own pages.

## Links

- Documentation: https://guard.aigovernance.ae/connector
- Support: https://aigovernance.ae/contact
- Privacy policy: https://aigovernance.ae/privacy
- Terms: https://aigovernance.ae/terms

## Licence

© GUARD GRC L.L.C-FZ. All rights reserved.
