# Phase 2 — Landscape & Analogues

## Goal

Map who has tried to solve this problem (or a closely related one) and what happened. Identify competitors, differentiation axes, and the early adopters most likely to move first.

A landscape that only lists competitors is incomplete. The most useful part is the analogue/antilog analysis — learning from protocols that succeeded or failed in adjacent space before writing a single line of spec.

---

## Step 1 — Direct competitors

List protocols that are solving the same problem for the same segment today. For each:

- Name, chain(s), TVL (current or peak)
- Core mechanism (one sentence)
- Fee structure and revenue
- Primary differentiation from each other

If there are no direct competitors: this is a signal worth examining. Ask: *"Is this space empty because the problem isn't real, because timing was wrong before, or because no one has tried yet? Each has a different implication."*

---

## Step 2 — Indirect competitors

Protocols that solve the same problem differently, or solve an adjacent problem that competes for the same user budget or mindshare.

Also include: manual solutions (doing it with scripts, keeper bots, or just accepting the loss), and CeFi alternatives (if a CeFi version exists and is good enough, it's competition).

---

## Step 3 — Analogue analysis

Analogues are protocols that solved a *different* problem using a *similar mechanism* — and succeeded. The value is in understanding what made the mechanism work, independently of the specific problem.

For each analogue:
- What mechanism did they use?
- What were the conditions that made it succeed? (timing, liquidity environment, team, first-mover)
- What did they get wrong initially that they had to fix?
- What's transferable to the current concept?

Look for 2–3 strong analogues. If none come to mind, ask: *"What's the closest thing to this mechanism that exists in DeFi or TradFi, even if the domain is different?"*

---

## Step 4 — Antilog analysis

Antilogs are protocols that tried something similar and failed — or succeeded but in a way you explicitly don't want to replicate (e.g., Olympus-style growth that was unsustainable).

For each antilog:
- What did they build?
- What specifically broke? (not "market conditions" — the specific mechanism failure)
- Was the failure inherent to the mechanism, or contingent on choices that can be made differently?
- What does this tell you about risks in the current concept?

DeFi has rich post-mortem material. Prioritize: Iron Finance (reflexive collateral), Anchor Protocol (unsustainable yield), Euler Finance (flash loan attack on donation mechanism), Nomad bridge (improper validation), LUNA/UST (undercollateralized algorithmic stablecoin).

If the current concept shares any structural similarity with a known failure mode, surface it explicitly as an `ASM-*` entry in Phase 5. Don't wait.

---

## Step 5 — Differentiation map

Build a differentiation map: for each dimension that matters in this space, place the current concept and each competitor.

Common dimensions in DeFi:
- Decentralization level (permissionless vs curated vs centralized)
- Capital efficiency
- Risk profile for LPs/users
- Fee structure (flat / percentage / dynamic)
- Chain coverage (single-chain vs multichain vs chain-agnostic)
- Composability (pluggable vs standalone)
- Governance model

Pick the 3–4 dimensions most relevant to this segment. Place every actor on each. The current concept's position should be intentional — not "we're in the middle of everything."

---

## Step 6 — Early adopters

Early adopters are the first ~100 users or protocols that would move to this protocol before it has a proven track record. They need the protocol to exist more urgently than the average user.

Ask:
- *"Who is most underserved by the current alternatives — not just 'has the problem' but 'can't solve it well today'?"*
- *"Who would take on smart contract risk of a v1 protocol to get access to this?"*
- *"Are there protocols (DAOs, treasuries, yield strategies) that would integrate this from day one if it existed?"*

Early adopters are not the eventual TAM. They are the people who make bootstrapping possible.

---

## LANDSCAPE.md Template

```markdown
# Competitive Landscape

## Direct Competitors
| Protocol | Chain | TVL | Mechanism | Fee | Key strength |
|---|---|---|---|---|---|
| [name] | [chain] | [$] | [one sentence] | [structure] | [what they do best] |

## Indirect Competitors
[List with brief note on why each competes for the same user]

## Differentiation Map
Dimensions: [D1], [D2], [D3]

| Protocol | D1 | D2 | D3 |
|---|---|---|---|
| Current concept | [position] | [position] | [position] |
| [Competitor A] | ... | ... | ... |

## Analogue Analysis
### [Analogue 1 name]
Mechanism: [what they did]
Success conditions: [what made it work]
Transferable insight: [what applies here]

### [Analogue 2 name]
...

## Antilog Analysis
### [Antilog 1 name]
What broke: [specific mechanism failure]
Inherent or contingent: [inherent to mechanism / contingent on choices]
Implication for current concept: [what to avoid or watch for]

### [Antilog 2 name]
...

## Early Adopters
[Specific segment or named protocols/DAOs that would move first, and why]

## Key Findings
[2–3 sentences: what the landscape tells you about where to position and what to avoid]
```

---

## Advancing to Phase 3

Gate check before advancing:

1. Are direct and indirect competitors mapped? If not, stay.
2. Are at least 1 analogue and 1 antilog analyzed? If not, stay (if no analogues exist, document why and advance with that noted).
3. Is the early adopter segment identified specifically? If not, stay.
4. Did the antilog analysis surface any structural similarities to known failure modes? If yes, ensure they're queued for Phase 5 (`QUEUED [Phase 5]: ASM-* entry for [failure mode similarity]`).

When satisfied: *"Landscape closed. Moving to Phase 3 — DeFi Lean Canvas, where we build the value proposition and unique mechanism."*
