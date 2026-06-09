# defi-protocol-discovery

A structured discovery skill for DeFi protocols. Guides you from raw idea (or no idea at all) to a go/no-go decision, producing a Protocol Brief that feeds directly into [`defi-spec-driven`](../defi-spec-driven/README.md).

## What it does

Runs a structured process across six phases:

0. **Opportunity Discovery** *(optional)* — Systematic scan to generate protocol candidates when you don't have a specific idea yet
1. **Idea Sharpening** — Jobs-to-be-Done, 5 Whys, problem/solution separation
2. **Landscape & Analogues** — Competitive map, analogue successes, antilog failures, early adopters
3. **DeFi Lean Canvas** — Value proposition, unique mechanism, channels, revenue, bootstrapping
4. **Economic Viability** — Sustainable yield audit, TVL scenarios, unit economics, bootstrapping cost
5. **Risk & Assumptions** — Ranked assumptions, death spiral mapping, validation plan
6. **Go / No-Go** — Kill criteria first, synthesis, verdict, Protocol Brief

## Usage

Works for any starting point:

```
/defi-protocol-discovery                    — open exploration (no idea yet)
/defi-protocol-discovery something for LPs  — focused on a space
/defi-protocol-discovery A fixed-rate lending vault for protocol treasuries  — concrete idea
```

Or start a session and let the skill detect your starting point from context.

## Outputs

All discovery documents are written to `.discovery/` in your project:

```
.discovery/
├── project/STATE.md
├── opportunities/OPPORTUNITIES.md    (if Phase 0 ran)
├── problem/PROBLEM.md
├── landscape/LANDSCAPE.md
├── canvas/CANVAS.md
├── economics/ECONOMICS.md
├── risks/RISKS.md
└── decision/DECISION.md             ← includes Protocol Brief if go
```

## Handoff to defi-spec-driven

If the verdict is GO or CONDITIONAL GO, `DECISION.md` includes a Protocol Brief with a ready-made init prompt for `defi-spec-driven`.

## Installation

Install via the [`defi-builder-skills`](https://github.com/melanke/defi-builder-skills) marketplace:

```
/plugin marketplace add melanke/defi-builder-skills
/plugin install defi-protocol-discovery@melanke
```

## License

CC-BY-4.0
