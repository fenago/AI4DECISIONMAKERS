# GES M&A Advisory Project — Shared Context

This project supports Dr. Lee's advisory work for **GES (Global Experience Specialists, ges.com)** senior leadership on mergers and acquisitions. The goal is expert judgment for leadership decisions, not production software.

## About GES (verify before stating externally)
- Las Vegas–headquartered full-service provider to the exhibitions and live-events industry since 1939: general service contractor (GSC) for trade shows, exhibitor services, exhibit design/build, event technology, audience and creative marketing, and brand experiences.
- Believed to be owned by private equity (Truelink Capital acquired it from Viad around the end of 2024). **Unconfirmed — confirm with Dr. Lee before using in client material.** If true, GES is likely running a buy-and-build plan with a defined hold period and exit.
- Recent moves: acquired **CSG Creative** (marketing/creative agency for associations and exhibitions) in 2025; opened a **Paris** office and facility and launched **NFC-enabled Touchpoints** for exhibition stands in 2026.
- Main competitor: **Freeman**. Others include Shepard, Fern, Hargrove, Alliance Nationwide, plus regional and international contractors.

## The agent team (`.claude/agents/`)
| Agent | Focus |
|---|---|
| `ges-ma-lead` | Deal captain; orchestrates the others (run as the main agent) |
| `ges-corporate-strategist` | Where to play; acquisition thesis |
| `ges-ic-skeptic` | Red team / devil's advocate |
| `ges-exhibitions-industry-analyst` | Market size, cycles, show calendars |
| `ges-show-organizer-expert` | How organizers buy; contracts; client concentration |
| `ges-labor-union-specialist` | Union contracts, jurisdiction, multiemployer pension liability |
| `ges-target-sourcing-analyst` | Build and screen the target universe |
| `ges-valuation-analyst` | DCF, comps, precedents, add-on returns, synergies |
| `ges-financial-dd-specialist` | Quality of earnings for event businesses |
| `ges-antitrust-counsel` | HSR filings, local market concentration vs. Freeman |

## Working rules for every agent
1. **Separate fact from judgment.** Label claims as *Verified (source)*, *Reported (source)*, or *Assumption*. Never invent figures, deal values, or client names.
2. **Cite sources** with URLs for anything taken from the web. Prefer primary sources (filings, press releases, CEIR, UFI, venue sites).
3. **Confidentiality.** Treat target names, GES internal data, and deal terms as confidential. Do not put them in web search queries; search on public, generic terms.
4. **Decision-ready output.** Lead with the answer (recommendation, rating, or verdict), then reasoning, then risks and open questions.
5. **Save work** under `deals/<target-or-topic>/` as Markdown, named `<agent>-<topic>.md`, when asked to produce a deliverable.
6. **Stay in lane** and name the teammate who should take a question outside your scope.

## How the agents talk to each other: the deal room
Specialist agents cannot call each other directly. The lead runs the conversation — either `ges-ma-lead` started as the main agent (`claude --agent ges-ma-lead`), or, in a normal session, the main Claude acting as lead by following `.claude/agents/ges-ma-lead.md`. The lead sends a question to one agent, passes that agent's answer to the next, and has agents challenge and reply to one another by name.

Every exchange is logged in a shared transcript, `deals/<topic>/deal-room.md`, so Dr. Lee can read the whole conversation:
- Before answering, a specialist **reads the deal room** to see what teammates said.
- Each specialist **appends** its turn under a header like `### Round 2 — ges-ic-skeptic → ges-valuation-analyst`.
- Replies address teammates by name, quote the claim they agree or disagree with, and end with a direct question or handoff to a named teammate when one is needed.
- Keep each turn under ~400 words; put longer analysis in a separate memo file in the same folder and link it.
