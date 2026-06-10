# Phase 1 — Idea Sharpening

## Goal

Transform a raw idea or selected concept into a precise, defensible problem statement. By the end of this phase, the developer should be able to answer clearly: what specific problem, for whom, and why this matters enough to build a protocol.

`PROBLEM.md` produced here is the foundation that all subsequent phases build on. A vague problem statement produces a vague canvas, a vague economic model, and eventually a vague protocol. Push until the problem is crisp.

## Entry modes

**From Phase 0**: the concept hypothesis is already formed. Phase 1's job is to challenge it — find the assumption beneath the hypothesis that's most likely to be wrong, and test it through the techniques below.

**Direct entry (Profile A)**: the developer has a raw idea. Phase 1 must first extract the problem (not the solution) before any sharpening can happen. Many developers arrive with a solution in mind and a problem they've only loosely defined. The first move is always: *separate problem from solution*.

---

## Step 1 — Separate problem from solution

If the developer describes a mechanism ("I want to build a vault that auto-rebalances positions"), extract the problem beneath it:

*"Before we go into the mechanism — what's the problem a user has today that this vault solves? What are they doing manually, or failing to do, that your protocol would handle for them?"*

This step is complete when the developer can state the problem independently of the solution. If they can't, stay here.

**Mechanism feasibility check**: once the problem is extracted, flag whether the mechanism described is confirmed (existing infrastructure, proven approach) or a hypothesis. Two distinct types require different logging:

- **Technical hypothesis**: depends on unproven primitives, novel combinations without clear precedent, or infrastructure that exists but hasn't been used this way before. Log as `OQ-N blocking Phase 3`.
- **Market precondition hypothesis**: the mechanism works technically but depends on an ecosystem condition that doesn't yet exist at sufficient adoption scale (e.g., V4 hooks require meaningful V4 TVL depth, intent-based architecture requires wallet penetration above a useful threshold). Log as `OQ-N blocking Phase 3` AND note in STATE.md: *"Phase 3 should apply the bifurcated v1/v2 pattern — mechanism depends on ecosystem precondition."* A market precondition is a viability-level concern, not just a technical flag — surface it with that weight.

A mechanism that has never been examined for feasibility should not enter the canvas as if it were settled.

---

## Step 2 — Jobs-to-be-Done

Apply JTBD framing to sharpen the problem statement. A "job" is the progress a user is trying to make in a specific situation — not a feature they want.

Ask these three JTBD questions **one at a time** — wait for the developer's answer before moving to the next. The answer to Q1 shapes how Q2 is framed; the answer to Q2 shapes Q3. Batching all three in one message sacrifices the signal that makes JTBD useful.

1. *"When does someone decide they need to solve this problem? What triggers that moment?"*
   — This reveals the situation. A problem without a concrete trigger situation is often too abstract.

2. *"What does someone do today to make progress on this job — even if it's a bad solution?"*
   — The current workaround is always revealing. If there is no workaround, ask whether the problem is real. If the workaround is good enough, ask whether a protocol is actually needed.

3. *"What would make someone 'fire' their current solution and 'hire' yours?"*
   — This surfaces the switching cost and the specific improvement required. A protocol that's "a little better" rarely bootstraps liquidity.

---

## Step 3 — 5 Whys

Take the problem statement from Step 2 and apply 5 Whys to find the root cause. The goal is to verify that the stated problem is the real problem, not a symptom of something deeper.

Example:
- "LPs lose money to impermanent loss" → Why? → "Price divergence between assets"
- Why does price divergence matter? → "LP positions are static while prices move"
- Why are positions static? → "Rebalancing requires active monitoring and gas"
- Why is monitoring hard? → "No on-chain trigger mechanism exists for position adjustment"
- Root problem: absence of a reactive, gas-efficient position management primitive

At depth 3–5, the problem either becomes more specific (good) or reveals that the original framing was a symptom of something the developer isn't actually solving (important finding — log as OQ or trigger a pivot back).

---

## Step 4 — Segment sharpening

A problem that belongs to "everyone" belongs to no one. Identify the most specific segment that has this problem acutely.

Ask:
- *"Who has this problem most acutely — and would they adopt a protocol to solve it first?"*
- *"Is the primary user a human end-user, or a protocol/DAO (which integrates your protocol as infrastructure)?"*

The distinction between end-user and protocol-as-customer changes channels, pricing, bootstrapping strategy, and governance design. Make it explicit here.

Output: a named segment with a qualification (e.g., "LPs with concentrated positions on Uniswap V3 managing >$50k", "protocol treasuries holding idle USDC without governance approval requirements").

---

## Step 5 — Problem statement synthesis

Combine Steps 1–4 into a single structured problem statement:

```
[Segment] faces [problem] when [situation/trigger].
Today they [current workaround], which fails because [specific failure mode].
A protocol could solve this by [mechanism sketch — one sentence only].
The job-to-be-done: [active verb phrase — what progress the user is making].
```

The mechanism sketch is allowed here (one sentence) because it anchors the problem to a tractable solution space. It is not a commitment — it will be challenged in Phase 3.

---

## PROBLEM.md Template

```markdown
# Problem Statement

## Segment
[Specific segment with qualification]

Primary user type: [End-user / Protocol-as-customer / Both]

## Problem
[One paragraph: problem, situation, why it matters]

## Current Workarounds
[What people do today, and why it's insufficient]

## Job-to-be-Done
[Active verb phrase: the progress the user is trying to make]
Example: "Protect LP yield from directional price moves without exiting the position"

## Root Cause (5 Whys)
[The structural reason this problem exists — one sentence]

## Mechanism Sketch
[One sentence: how a protocol could address the root cause]
Note: this is a hypothesis, not a commitment. It will be tested in Phase 3.

## Open Questions
[Any unresolved questions about the problem definition, logged from this phase]
```

---

## Advancing to Phase 2

Gate check before advancing:

1. Can the developer state the problem independently of the solution? If not, stay.
2. Is the segment specific enough to identify early adopters? If not, stay.
3. Is the root cause identified (via 5 Whys)? If not, stay.
4. Are all blocking OQs from this phase resolved? If not, resolve or convert to ACCEPTED-AMBIGUITY.

5. If a mechanism was described: was the mechanism feasibility check run? If flagged as a hypothesis (technical or market precondition), is there an OQ logged blocking Phase 3? If a market precondition hypothesis, does STATE.md note that Phase 3 should apply the bifurcated v1/v2 pattern?

When all five are satisfied: *"Problem statement closed. Moving to Phase 2 — Landscape & Analogues, where we map who's tried this before and what we can learn from them."*
