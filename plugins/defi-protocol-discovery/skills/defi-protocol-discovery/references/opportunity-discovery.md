# Phase 0 — Opportunity Discovery

This phase is optional. Run it for Profile B (vague direction) and Profile C (open exploration). Skip it for Profile A (concrete idea).

## Goal

Produce a shortlist of 3–5 protocol concepts, each with a problem hypothesis. The developer selects one — that selected concept becomes the input to Phase 1.

A concept that survives Phase 0 has a named problem, a named segment with that problem, and a rough sense of why now. Nothing more is required at this stage.

## Focused Mode (Profile B)

The developer has named a space or segment (e.g., "something for LPs", "lending on a new chain", "yield for DAOs").

**Step 1 — Anchor**

Confirm the stated space precisely. Ask one clarifying question if the space is ambiguous:
*"When you say [X], do you mean [interpretation A] or [interpretation B]? — This determines which user problems and competitors we map."*

**Step 2 — Pain scan within the space**

Walk through the named space systematically using the User Segment → Pain Map technique:

For the target segment, identify their current friction points across three categories:
- **Execution friction**: things that are hard, slow, or expensive to do
- **Risk exposure**: risks they carry that they'd rather not
- **Opportunity cost**: value they're leaving on the table

Produce 5–8 pain points. For each, note: who has it, how acute it is (frequent vs rare, high-stakes vs low-stakes), and what current workarounds exist (if any).

**Step 3 — Filter to protocol-shaped problems**

Not every pain point maps to a DeFi protocol. Apply two filters:

1. *Is this a coordination problem that smart contracts can solve?* (If the solution requires trust, counterparty matching, or rule enforcement, it's a candidate.)
2. *Is there a sustainable economic model?* (If no one would pay fees, or the only revenue is token inflation, flag it now — this is a weak candidate.)

Keep 3–5 candidates after filtering.

**Step 4 — Shortlist with hypotheses**

For each surviving candidate, write a two-sentence hypothesis:
- *[Segment] has a problem with [pain]. A protocol that [mechanism] would solve this because [reason this is better than existing alternatives].*

Output `OPPORTUNITIES.md` with the shortlist.

---

## Open Mode (Profile C)

The developer has no stated direction. Run a systematic opportunity scan across DeFi.

**Step 1 — Establish starting point**

Ask one question to find a constraint to anchor on:
*"Is there a type of user you care most about building for, or a DeFi domain you find most interesting? — Even a loose preference lets us focus the scan. If truly open, say so and we'll cover the landscape."*

Use their answer to prioritize the scan — but cover all categories if they're genuinely open.

**Step 2 — Opportunity scan**

Work through the following lenses systematically. For each lens, generate 2–3 candidate opportunities before moving to the next.

**Lens A — TradFi/CeFi gaps**
What financial instruments or mechanisms exist in traditional finance that have no good DeFi equivalent?
Examples: fixed-rate lending, credit scoring, RWA collateral, structured products, insurance.
For each gap: ask why it hasn't been built yet (technical barrier? regulatory? liquidity problem?) and whether those barriers are now lower.

**Lens B — Composability gaps**
What combinations of existing protocols create friction, require manual steps, or leave value on the table?
Look at: liquidity routing inefficiencies, yield aggregation that requires too much gas, cross-protocol liquidations, vault strategies that need rebalancing.

**Lens C — Post-mortem opportunities**
What protocols failed and left an unmet need? Failure doesn't invalidate a market — it may just mean the prior attempt had a specific flaw that's now avoidable.
Scan: Iron Finance, Euler, Nomad bridge, algorithmic stablecoins, early AMM designs.

**Lens D — Segment-specific gaps**
Pick 2–3 underserved segments and map their unmet needs:
- Protocol treasuries (idle USDC, yield without governance risk)
- LPs in concentrated liquidity (IL management, position rebalancing)
- Cross-chain users (bridging UX, fragmented liquidity)
- Institutional on-chain participants (compliance-aware DeFi, KYC pools)

**Lens E — Trend riding**
What infrastructure or user behavior is growing that creates new protocol opportunities?
Current relevant trends: EigenLayer restaking, account abstraction, intent-based architectures, RWA tokenization, onchain AI agents needing DeFi primitives.
For each: what protocol would be most useful in a world where this trend continues?

**Step 3 — Shortlist**

From all lenses combined, select 3–5 candidates applying the same two filters as Focused Mode (coordination problem shape + sustainable economics).

Write two-sentence hypotheses for each. Output `OPPORTUNITIES.md`.

---

## OPPORTUNITIES.md Template

```markdown
# Protocol Opportunities

Discovery mode: [Focused / Open]
Starting point: [stated space or "open exploration"]

## Candidates

### OPP-1: [Working name]
**Problem**: [one sentence — who has what problem]
**Hypothesis**: [two sentences — mechanism + why better than existing]
**Why now**: [one sentence — what changed that makes this viable today]
**Weak point**: [one sentence — the most dangerous assumption in this hypothesis]

### OPP-2: [Working name]
...

### OPP-3: [Working name]
...

## Selected Concept
[OPP-N] — [Working name]
Reason for selection: [one sentence]

## Eliminated Candidates
- [OPP-N]: [one-sentence reason for elimination]
```

---

## Advancing to Phase 1

Present the shortlist to the developer. Ask them to select one concept — or to say what's missing if none of the candidates feel right (which triggers another iteration within Phase 0).

After selection, confirm: *"[OPP-N] selected. Moving to Phase 1 — Idea Sharpening, where we'll challenge the problem hypothesis and find the real problem beneath it."*

If the developer came from Profile B or C, remind them that Phase 1 will treat the selected hypothesis as a starting point to challenge, not a conclusion to document.
