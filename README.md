# AgenticUX

An exploration of a spec for **Human Interface Guidelines for agentic user interfaces** — software where an AI agent acts on a person's behalf, not just responds to clicks.

Classic HIGs ([Apple](https://developer.apple.com/design/human-interface-guidelines/), [Material](https://m3.material.io/)) assume the human drives every action. Agentic UIs invert that: the system proposes, plans, and executes. This project asks what principles keep the human informed, in control, and able to trust the result.

## Status

Early draft. Expect churn. Issues and PRs welcome.

## Contents

[`spec/principles.md`](spec/principles.md) holds 24 draft principles, written in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119) language:

1. [Minimal handoff phrases](spec/principles.md#1-minimal-handoff-phrases)
2. [Legible intent](spec/principles.md#2-legible-intent)
3. [Proportional consent](spec/principles.md#3-proportional-consent)
4. [Voice-first confirmations](spec/principles.md#4-voice-first-confirmations)
5. [Interruptibility](spec/principles.md#5-interruptibility)
6. [Visible progress](spec/principles.md#6-visible-progress)
7. [Honest outcomes](spec/principles.md#7-honest-outcomes)
8. [Reversibility](spec/principles.md#8-reversibility)
9. [Scoped authority](spec/principles.md#9-scoped-authority)
10. [Provenance](spec/principles.md#10-provenance)
11. [Presenter split view](spec/principles.md#11-presenter-split-view)
12. [Chase the "what abouts"](spec/principles.md#12-chase-the-what-abouts)
13. [Volunteer experts](spec/principles.md#13-volunteer-experts)
14. [Archived credit](spec/principles.md#14-archived-credit)
15. [Accessible by default](spec/principles.md#15-accessible-by-default)
16. [Citing evidence](spec/principles.md#16-citing-evidence)
17. [Data dignity](spec/principles.md#17-data-dignity)
18. [Worker voice](spec/principles.md#18-worker-voice)
19. [Democratic governance](spec/principles.md#19-democratic-governance)
20. [Public AI](spec/principles.md#20-public-ai)
21. [Local-first](spec/principles.md#21-local-first)
22. [Interoperability and exit](spec/principles.md#22-interoperability-and-exit)
23. [No dark patterns](spec/principles.md#23-no-dark-patterns)
24. [Cost transparency](spec/principles.md#24-cost-transparency)

Principle 16 keeps a living list of preferred journals and conferences for citing evidence, to be re-evaluated regularly by an external jury.

## Prior art

- [Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/) — Amershi et al., CHI 2019
- [People + AI Guidebook](https://pair.withgoogle.com/guidebook/) — Google PAIR
- [Principles of Mixed-Initiative User Interfaces](https://erichorvitz.com/chi99horvitz.pdf) — Horvitz, CHI 1999
- [Model Context Protocol](https://modelcontextprotocol.io/) — a wire protocol agents use to reach tools and data
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) — W3C accessibility guidelines, the baseline for principle 15
- [A Blueprint for a Better Digital Society](https://hbr.org/2018/09/a-blueprint-for-a-better-digital-society) — Lanier and Weyl on data dignity
- [Local-first software](https://www.inkandswitch.com/local-first/) — Ink & Switch
- [Green Web Foundation](https://www.thegreenwebfoundation.org/) — tools for a fossil-free internet

Every principle links its own sources in [`spec/principles.md`](spec/principles.md).

## License

[GPL-3.0](LICENSE)
