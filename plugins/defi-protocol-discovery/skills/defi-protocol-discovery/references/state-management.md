# State Management

Reference for maintaining STATE.md throughout the discovery process.

## STATE.md Structure

Create `.discovery/project/STATE.md` at initialization with this template:

```markdown
# Discovery State

## Protocol
Name: [TBD or working name]
Profile: [A / B / C]
Phase: [current phase]

## Phase History
- [ ] Phase 0 — Opportunity Discovery
- [ ] Phase 1 — Idea Sharpening
- [ ] Phase 2 — Landscape & Analogues
- [ ] Phase 3 — DeFi Lean Canvas
- [ ] Phase 4 — Economic Viability
- [ ] Phase 5 — Risk & Assumptions
- [ ] Phase 6 — Go / No-Go

## Current Phase Notes
[Active working notes for the current phase]

## Open Questions
[OQ-1]: [question] | Blocking phase: [N] | Status: OPEN
[OQ-2]: ...

## Decisions
[DEC-1]: [decision made] | Phase: [N] | Rationale: [why]
[DEC-2]: ...

## Expansion Queue
- [item] — queued from Phase [N]

## Pivot Log
[Only if a pivot occurred from Phase 2 onward]
- Phase [N] pivot: [what changed and why]
```

## Updating STATE.md

### When to update

- **Open question logged**: add to Open Questions with blocking phase
- **Decision made**: add to Decisions with rationale
- **Phase boundary reached**: check off phase in Phase History, update current phase
- **Tangent parked**: add to Expansion Queue
- **OQ resolved**: update status to CLOSED, add resolution note
- **Pivot from Phase 2+**: add to Pivot Log with rationale

### Open Question lifecycle

```
OPEN → (resolved) → CLOSED [resolution text]
OPEN → (unresolvable) → ACCEPTED-AMBIGUITY [assumption made, risk level: low/medium/high]
```

No OQ survives Phase 6 as silently OPEN. Every one must be CLOSED or ACCEPTED-AMBIGUITY before the go/no-go verdict is written.

### Decision format

Decisions are facts — not aspirations. If the answer is "we don't know yet", that's an OQ, not a decision.

Good: `DEC-3: Target segment is protocol treasuries, not retail LPs. Rationale: retail already served by existing yield aggregators; treasuries have unmet idle capital problem.`

Bad: `DEC-3: We'll target protocols probably.`

## Session Handoff

When pausing work, add a handoff block at the top of STATE.md:

```markdown
## Last Session — [date]
Phase when paused: [N]
Last item worked: [specific item]
Next step: [exactly what to do on resume]
Active OQs that need attention: [OQ-N, OQ-M]
```

On resume: read STATE.md, load the reference file for the current phase, and load the current phase's output file. Don't re-read earlier phases unless an OQ requires it.
