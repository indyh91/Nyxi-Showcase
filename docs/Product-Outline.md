# Nyxi

**Nyxi is an execution-time governance system for irreversible actions.**  
Models (or humans) may *propose* actions. Nyxi alone has *execution authority* — enforced at a single, fail-closed boundary.

If you’re looking for the *concept, proofs, and black-box demo* behind the category, see the companion repo: **execution-governance**.

---

## What Nyxi is

Nyxi is a **Windows-hosted, long-running governed executor** that turns high-level intent into **proposed actions**, then enforces a **policy contract** at the irreversible execution boundary:

- **POLICY_ALLOW** → mint `AuthorizedAction` → execute via governed sink  
- **POLICY_DENY** → block (no irreversible effect)  
- **POLICY_UNKNOWN** → stop and request guidance (fail-closed)

**Important:** `POLICY_ALLOW` means “authorized under the policy contract at execution time.”  
It does **not** imply the action will succeed (timeouts/failures are execution outcomes, and are logged).

---

## What Nyxi is not

Nyxi is **not**:
- an “agent framework” where the model executes actions directly
- a dashboard / post-hoc audit system
- a rollback-based safety story
- a per-action human approval workflow
- a probabilistic confidence gate

Nyxi is a **control topology**: propose → authorize → execute, with non-bypassable authority separation.

---

## Core mechanism

```text
Proposer (human or model)
        │
        │   proposes ProposedAction
        ▼
Nyxi Authorization Boundary (policy contract)
        │
        ├── POLICY_DENY    → no sink call
        ├── POLICY_UNKNOWN → stop + request guidance
        └── POLICY_ALLOW   → mint AuthorizedAction
                              │
                              ▼
                     Governed irreversible sink
