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

## Presenting the Shortlist

Present the shortlist and give a recommendation — don't leave selection as an open menu:

*"My recommendation is [OPP-N]: the weak point ([weak point text]) is the most addressable of the batch, and the problem is the most specific. If [OPP-M] resonates more strongly with you, tell me why — that's useful signal about the direction you want to go."*

Give a recommendation even when the choice is close. The developer can override; what matters is that the reasoning is visible.

**If the developer asks for more detail on a candidate before selecting:**
Expand that candidate's problem, mechanism, and weak point in 2–3 focused paragraphs. Do not enter JTBD or 5 Whys — those are Phase 1. If they ask "but how would the mechanism work exactly?", redirect: *"The mechanism detail is Phase 1's job — we need to confirm the problem is worth solving before designing the solution. Right now the question is whether this problem is worth exploring."*

---

## Gate Before Advancing to Phase 1

Before loading the Phase 1 reference, confirm all four:

1. The selected concept has a named problem, a named segment, and at least one mechanism hypothesis. If not: iterate within Phase 0.
2. The concept's primary weak point has been articulated and the developer has acknowledged it as a hypothesis to challenge in Phase 1. If the developer hasn't acknowledged the weakness, surface it explicitly before advancing.
3. All eliminated candidates are documented with a one-sentence reason in OPPORTUNITIES.md. If not: complete the file.
4. The developer understands Phase 1 will treat the selected hypothesis as a target to challenge, not a conclusion to document. State this explicitly before advancing: *"[OPP-N] selected. In Phase 1 we'll treat this as a hypothesis to challenge — the goal is to find the real problem beneath it, which may look different from what we've written here."*

When all four are satisfied, load the Phase 1 reference and begin.
