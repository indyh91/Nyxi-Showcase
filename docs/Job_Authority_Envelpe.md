Naming + first-class documentation (the concept)
Canonical name

Job Authority Envelope (JAE)

Short alt names (if you want tighter branding):

Authority Envelope

Job Envelope

Intent Envelope

But “Job Authority Envelope” matches the audit language and is extremely unambiguous. 

AUDIT_JOB_AUTHORITY_ENVELOPE

First-class concept definition (drop into docs)

Job Authority Envelope (JAE) is a job-scoped, human-approved, immutable authority contract that narrows Nyxi’s globally allowed action space to only those actions consistent with the user’s initial goal.
The JAE is derived once, locked before execution, and enforced at the execution boundary for every irreversible action. It cannot be widened mid-run; violations are denied and logged; ambiguity stops with GuidanceRequest.

“Governing Laws” (short list)

Derive once, lock once

Narrow-only: envelope ⊆ global ceilings

Boundary-enforced: action ∉ envelope ⇒ DENY

No widening via guidance

Evidence-bound: envelope hash in every decision/execution record

Unknown stops: missing envelope or ambiguous scope ⇒ POLICY_UNKNOWN + GuidanceRequest

These laws correspond exactly to the gaps/blockers and recommended changes. 

AUDIT_RECOMMENDED_CHANGES

 

AUDIT_GAPS_AND_BLOCKERS