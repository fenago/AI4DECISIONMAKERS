# AI4DECISIONMAKERS — GES M&A Advisory Agents

Ten Claude Code agents, scoped to this project, that advise GES (Global Experience Specialists) senior leadership on acquisitions. See `CLAUDE.md` for shared context and rules.

## Agents (`.claude/agents/`)
`ges-ma-lead` (orchestrator) · `ges-corporate-strategist` · `ges-ic-skeptic` · `ges-exhibitions-industry-analyst` · `ges-show-organizer-expert` · `ges-labor-union-specialist` · `ges-target-sourcing-analyst` · `ges-valuation-analyst` · `ges-financial-dd-specialist` · `ges-antitrust-counsel`

## Use
Start the lead as the main agent so it can brief the others and relay their answers:

```bash
claude --agent ges-ma-lead
```

Or, in a normal Claude Code session in this folder, call one directly: `@ges-ic-skeptic stress-test this thesis...`

Each conversation between agents is logged in `deals/<topic>/deal-room.md`, and the final recommendation goes in `deals/<topic>/decision-memo.md`.
