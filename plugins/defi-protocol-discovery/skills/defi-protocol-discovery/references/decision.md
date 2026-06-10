# Phase 6 — Go / No-Go

## Goal

Produce an explicit, reasoned go/no-go decision. If go: produce the Protocol Brief that feeds directly into `defi-spec-driven`.

This phase synthesizes everything — but synthesis is not the first step. Kill criteria come first.

---

## Step 1 — Kill criteria (before synthesis)

Before looking at the accumulated work, establish the conditions under which the answer is NO.

Ask the developer: *"Before we review everything — what would have to be true for you to decide not to build this? Think about the biggest risks we've identified."*

Confirm 3–5 kill criteria. Document them in DECISION.md before proceeding to synthesis. Examples:

- "If the validation plan for ASM-lp-demand shows <30% of LPs cite IL as their primary pain"
- "If there's no credible path to $5M sticky TVL after bootstrapping incentives end"
- "If the regulatory surface requires KYC/AML infrastructure we're not willing to build"
- "If the protocol can't survive the RISK-incentive-collapse spiral at current token emission rates"

Once kill criteria are documented, lock them. They cannot be revised during synthesis. This prevents the developer from unconsciously adjusting the bar as they review favorable evidence.

---

## Step 2 — Synthesis review

With kill criteria locked, review each phase's output in sequence:

**From PROBLEM.md**: Is the problem real, specific, and worth a protocol? Score: STRONG / ADEQUATE / WEAK
**From LANDSCAPE.md**: Is the competitive position viable? Are early adopters realistic? Score: STRONG / ADEQUATE / WEAK
**From CANVAS.md**: Is the UVP distinct and the mechanism defensible? Score: STRONG / ADEQUATE / WEAK
**From ECONOMICS.md**: Does the protocol survive the bear scenario? Are unit economics viable? Score: STRONG / ADEQUATE / WEAK
**From RISKS.md**: Are the highest-risk assumptions manageable? Are death spirals mitigated? Score: STRONG / ADEQUATE / WEAK

For each WEAK score: is it a blocker, or a known risk to carry forward?

---

## Step 3 — Kill criteria check

Apply the kill criteria from Step 1 to the synthesis results. Each criterion has one of three states:

- **NOT TRIGGERED**: evidence shows the kill condition is not met → this criterion passes
- **TRIGGERED**: evidence shows the kill condition is met → NO-GO; stop here
- **INDETERMINATE**: the validation experiment has not been run; the criterion cannot be evaluated yet

If any criterion is TRIGGERED: verdict is NO-GO. Document the specific criterion and the evidence. A NO-GO is not a failure — it's the skill working correctly.

If no criterion is TRIGGERED but one or more are INDETERMINATE: do not treat INDETERMINATE as passing. Proceed to Step 4, but each INDETERMINATE criterion becomes a blocking validation condition in the CONDITIONAL GO verdict — not an optional caveat.

If all criteria are NOT TRIGGERED: proceed to Step 4 and expect a GO or CONDITIONAL GO depending on Step 4 results.

---

## Step 4 — Open assumptions review

Review RISKS.md validation plan. For any CRITICAL or HIGH assumption that has NOT been validated:

Present two options to the developer:
1. **Build anyway** — document the assumption as ACCEPTED-AMBIGUITY with risk level and proceed
2. **Validate first** — the go verdict is conditional on validation; don't start spec until the experiment is done

Neither option is wrong. Building with known assumptions is common. The decision must be conscious and documented.

---

## Step 5 — Verdict

One of three outcomes:

**GO**: The protocol concept is viable enough to commit to specification. All kill criteria pass. High-risk assumptions are either validated or explicitly accepted.

**CONDITIONAL GO**: The protocol concept is viable but conditions must be met before starting spec. Conditions come from two sources: INDETERMINATE kill criteria (Step 3) and VALIDATE FIRST assumptions (Step 4). Type each condition explicitly:

- **Absolute blocker**: if this condition fails → NO-GO regardless of other results. List these first. Evaluate them in sequence — if one fails, stop; don't evaluate the rest.
- **Stage blocker**: if this condition fails → return to the relevant phase and revise before proceeding to spec or build. These are serious but not existential.

The Protocol Brief for a CONDITIONAL GO is withheld or produced with explicit `[TBD pending: condition N]` placeholders for fields that depend on unvalidated assumptions. Do not project unvalidated numbers into the handoff document — the spec team should know what's real and what's assumed.

**NO-GO**: One or more kill criteria triggered. Document the specific reason. Optionally: identify what would have to change for a future re-evaluation (different market conditions, different mechanism, different segment).

---

## Protocol Brief (Go and Conditional Go only)

The Protocol Brief is the handoff document to `defi-spec-driven`. It must be precise enough that the init phase of the spec process can start without re-deriving context.

```markdown
# Protocol Brief

## Identity
Working name: [name]
Category: [AMM / lending / yield vault / derivatives / infrastructure / other]
Target network: [or TBD if not yet decided]

## Problem
[PROBLEM.md problem statement, one paragraph]

## Target Segment
Primary: [from CANVAS.md]
Early adopters: [specific — from LANDSCAPE.md]

## Core Value Proposition
[From CANVAS.md UVP field — one sentence]

## Unique Mechanism
[From CANVAS.md — the how]

## Economic Model
Revenue source: [from ECONOMICS.md — sustainable streams only]
Fee structure: [specific]
Bootstrap path: [mechanism + cost + timeline]
Break-even TVL: [from ECONOMICS.md]

## Open Assumptions (carry forward into spec)
| Slug | Assumption | Risk | Status |
|---|---|---|---|
| ASM-X | [assumption] | HIGH | ACCEPTED-AMBIGUITY — [rationale] |

## Handoff Note
Start defi-spec-driven with: "[one sentence framing for the init prompt]"
Example: "A fixed-rate lending protocol for protocol treasuries on Ethereum mainnet, greenfield, targeting $10M TVL in 12 months."
```

---

## DECISION.md Template

```markdown
# Go / No-Go Decision

## Kill Criteria (defined before synthesis)
1. [Criterion 1]
2. [Criterion 2]
3. [Criterion 3]
...

## Synthesis Review
| Phase | Output | Score | Notes |
|---|---|---|---|
| Phase 1 — Problem | PROBLEM.md | STRONG / ADEQUATE / WEAK | [note] |
| Phase 2 — Landscape | LANDSCAPE.md | STRONG / ADEQUATE / WEAK | [note] |
| Phase 3 — Canvas | CANVAS.md | STRONG / ADEQUATE / WEAK | [note] |
| Phase 4 — Economics | ECONOMICS.md | STRONG / ADEQUATE / WEAK | [note] |
| Phase 5 — Risks | RISKS.md | STRONG / ADEQUATE / WEAK | [note] |

## Kill Criteria Check
| Criterion | State | Evidence |
|---|---|---|
| [criterion 1] | NOT TRIGGERED / TRIGGERED / INDETERMINATE | [evidence or "validation not run"] |
| [criterion 2] | NOT TRIGGERED / TRIGGERED / INDETERMINATE | [evidence or "validation not run"] |

## Unvalidated High-Risk Assumptions
| Slug | Decision | Rationale |
|---|---|---|
| ASM-X | ACCEPTED-AMBIGUITY | [why acceptable to proceed] |
| ASM-Y | VALIDATE FIRST | [experiment, deadline] |

## Verdict
**[GO / CONDITIONAL GO / NO-GO]**

[One paragraph rationale]

---

[Protocol Brief — if GO or CONDITIONAL GO]
```
