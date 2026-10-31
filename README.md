# AgenticUX

An exploration of a spec for **Human Interface Guidelines for agentic user interfaces** — software where an AI agent acts on a person's behalf, not just responds to clicks.

Classic HIGs ([Apple](https://developer.apple.com/design/human-interface-guidelines/), [Material](https://m3.material.io/)) assume the human drives every action. Agentic UIs invert that: the system proposes, plans, and executes. This project asks what principles keep the human informed, in control, and able to trust the result.

## Status

Early draft. Expect churn. Issues and PRs welcome.

## Contents

[`spec/principles.md`](spec/principles.md) holds 43 draft principles, written in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119) language:

**[Interaction and control](spec/principles.md#interaction-and-control)**

- 1\. [Minimal handoff phrases](spec/principles.md#1-minimal-handoff-phrases)
- 2\. [Legible intent](spec/principles.md#2-legible-intent)
- 3\. [Proportional consent](spec/principles.md#3-proportional-consent)
- 4\. [Voice-first confirmations](spec/principles.md#4-voice-first-confirmations)
- 5\. [Interruptibility](spec/principles.md#5-interruptibility)
- 6\. [Visible progress](spec/principles.md#6-visible-progress)
- 7\. [Honest outcomes](spec/principles.md#7-honest-outcomes)
- 8\. [Reversibility](spec/principles.md#8-reversibility)
- 11\. [Presenter split view](spec/principles.md#11-presenter-split-view)
- 26\. [Craftsman style](spec/principles.md#26-craftsman-style)

**[Accessibility and inclusion](spec/principles.md#accessibility-and-inclusion)**

- 15\. [Accessible by default](spec/principles.md#15-accessible-by-default)
- 27\. [Adaptive personality](spec/principles.md#27-adaptive-personality)
- 30\. [Nothing about us without us](spec/principles.md#30-nothing-about-us-without-us)
- 40\. [Design justice](spec/principles.md#40-design-justice)

**[Knowledge and evidence](spec/principles.md#knowledge-and-evidence)**

- 10\. [Provenance](spec/principles.md#10-provenance)
- 12\. [Chase the "what abouts"](spec/principles.md#12-chase-the-what-abouts)
- 13\. [Volunteer experts](spec/principles.md#13-volunteer-experts)
- 14\. [Archived credit](spec/principles.md#14-archived-credit)
- 16\. [Citing evidence](spec/principles.md#16-citing-evidence)
- 31\. [Creative partnership](spec/principles.md#31-creative-partnership)

**[Trust, privacy, and rights](spec/principles.md#trust-privacy-and-rights)**

- 9\. [Scoped authority](spec/principles.md#9-scoped-authority)
- 23\. [No dark patterns](spec/principles.md#23-no-dark-patterns)
- 25\. [Works for you](spec/principles.md#25-works-for-you)
- 28\. [Human rights](spec/principles.md#28-human-rights)
- 29\. [Privacy in context](spec/principles.md#29-privacy-in-context)
- 32\. [No enshittification](spec/principles.md#32-no-enshittification)
- 36\. [Explanation and appeal](spec/principles.md#36-explanation-and-appeal)

**[Ownership and openness](spec/principles.md#ownership-and-openness)**

- 20\. [Public AI](spec/principles.md#20-public-ai)
- 21\. [Local-first](spec/principles.md#21-local-first)
- 22\. [Interoperability and exit](spec/principles.md#22-interoperability-and-exit)
- 33\. [Cooperative ownership](spec/principles.md#33-cooperative-ownership)
- 34\. [Free software](spec/principles.md#34-free-software)
- 35\. [Right to repair](spec/principles.md#35-right-to-repair)
- 39\. [Community data sovereignty](spec/principles.md#39-community-data-sovereignty)

**[Work and community](spec/principles.md#work-and-community)**

- 17\. [Data dignity](spec/principles.md#17-data-dignity)
- 18\. [Worker voice](spec/principles.md#18-worker-voice)
- 19\. [Democratic governance](spec/principles.md#19-democratic-governance)
- 37\. [No bossware](spec/principles.md#37-no-bossware)
- 38\. [Right to disconnect](spec/principles.md#38-right-to-disconnect)
- 41\. [Mutual aid and the commons](spec/principles.md#41-mutual-aid-and-the-commons)
- 43\. [Care](spec/principles.md#43-care)

**[Sustainability](spec/principles.md#sustainability)**

- 24\. [Cost transparency](spec/principles.md#24-cost-transparency)
- 42\. [Sufficiency](spec/principles.md#42-sufficiency)

[`spec/memes.md`](spec/memes.md) is a sidecar of pop culture references for each principle, for talks and social posts.

Principle 16 keeps a living list of preferred journals and conferences for citing evidence, to be re-evaluated regularly by an external jury.

## Foundations: Tim Berners-Lee

[Tim Berners-Lee](https://en.wikipedia.org/wiki/Tim_Berners-Lee), the web's inventor, has argued for most of what this spec asks of agents. His key writing:

- [Information Management: A Proposal](https://www.w3.org/History/1989/proposal.html) (1989): the web began as a tool for sharing knowledge across a whole community, not a product.
- [Principles of Design](https://www.w3.org/DesignIssues/Principles.html) (1998): simplicity, modularity, decentralization, and the principle of least power. These underlie Local-first (21) and Interoperability and exit (22).
- [Long Live the Web](https://www.scientificamerican.com/article/long-live-the-web/) (Scientific American, 2010): universality, open standards, and neutrality against walled gardens. See Accessible by default (15) and Public AI (20).
- [Contract for the Web](https://contractfortheweb.org/) (2019): shared commitments for governments, companies, and citizens to keep the web open, safe, and for everyone.
- [Solid](https://solidproject.org/): personal data in Pods the person controls, shared only with consent. This is the model for Local-first (21) and Works for you (25).
- [Charlie works for Bob](https://www.w3.org/DesignIssues/Charlie.html) (2017) and [Charlie Works](https://www.w3.org/DesignIssues/Works.html) (2025): an AI that works for its user, not a platform, built on a Solid Pod with per-use consent. This is the source of Works for you (25).
- [Why I gave the world wide web away for free](https://www.theguardian.com/technology/2025/sep/28/why-i-gave-the-world-wide-web-away-for-free) (The Guardian, 2025): the web works only if it works for everyone, and AI needs not-for-profit, CERN-like institutions. See Public AI (20).
- [This Is for Everyone](https://www.panmacmillan.com/authors/tim-berners-lee/this-is-for-everyone/9781035023677) (2025): his memoir and "unfinished story" of the web, and [his case for controlling AI](https://panmacmillan.com/blogs/general/tim-berners-lee-on-ai) rather than fearing it.

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

## Support the Internet Archive

Archived credit (principle 14) depends on the [Internet Archive](https://en.wikipedia.org/wiki/Internet_Archive), and it needs the help. If this spec is useful to you, please [donate](https://archive.org/donate).

## License

[GPL-3.0](LICENSE)
