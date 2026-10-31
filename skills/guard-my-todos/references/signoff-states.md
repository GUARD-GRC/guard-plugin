# GUARD sign-off states

| State | Plain words | Who can move it on |
| --- | --- | --- |
| `draft` | not sent for approval | an owner, editor or consultant: request sign-off |
| `pending_approval` | waiting for the approver | the approver: approve or reject (GUARD link + fresh code). An owner, editor, consultant or the approver can withdraw it to draft. |
| `pending_review` | dual approval: the approver has endorsed it; waiting for the reviewer's final decision | the reviewer: approve or reject (GUARD link + fresh code); the reviewer can also withdraw it |
| `approved` | signed off; valid for 365 days | revoking happens only in GUARD |
| `rejected` | turned down, with the reason in the history | fix the item, then request sign-off again |
| `expired` | the 365-day approval ran out | an owner, editor, consultant or the approver returns it to draft, then requests sign-off again |

## Single or dual approval
- Each organisation chooses single or dual approval in GUARD. Owners change this on the Team page.
- **Single:** the approver decides. The steps are draft, then pending approval, then approved or rejected.
- **Dual:** the approver endorses first, then the named reviewer makes the final decision. The steps are draft, pending approval, pending review, then approved or rejected.

## What resets a sign-off
- Editing a policy or report in GUARD sends an approved item back for approval. It also re-opens the plan's sign-off, because the plan comes from the policy.
- Completing an implementation plan sends it to its approver to approve the completion.
- Reopening a completed plan resets its sign-off to draft. Only GUARD can reopen a plan.
- A manual change to an AI system's classification can un-approve it.

## Subject types
`assessment`, `policy`, `ai_system` (only after its assessment is finished), `action_plan` (a policy's implementation plan), `attestation` (a regulator document), `attestation_plan` (a regulator document's plan).

## The approval link (hand-off)
1. The assistant prepares the decision. GUARD freezes a summary of exactly what will happen.
2. The person opens the link. GUARD asks them to sign in as themselves if needed.
3. GUARD shows the summary and asks for a **fresh** code from their authenticator app. Then the person confirms or cancels.
4. The link works once and expires after 15 minutes. A different person cannot use it.
5. The assistant checks the outcome with `GUARD:get_handoff_status`: `pending` (not confirmed yet), `done`, `cancelled`, `expired`, or `stale` (the item changed after the link was made, so nothing was recorded; prepare a new link if the person still wants to decide).
