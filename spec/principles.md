# Principles (draft)

The key words "MUST", "SHOULD", and "MAY" are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

Principles keep their numbers for stable references, and are grouped by theme below.

## Interaction and control

How an agent proposes, acts, and hands control back.

### 1. Minimal handoff phrases
When an agent needs a person to act outside the conversation (verifying identity, generating or entering a secret, approving on another device), it SHOULD tell them the shortest unambiguous phrase that signals completion, such as "done", so they can reply by text or voice. The agent SHOULD accept that phrase as-is and MUST NOT ask the person to paste secrets back into the conversation.

### 2. Legible intent
An agent SHOULD state what it is about to do, in the person's terms, before it does anything consequential.

### 3. Proportional consent
Confirmation SHOULD scale with reversibility and reach. Reading needs none; deleting, spending, or publishing MUST be confirmed unless the person has granted durable authorization.

### 4. Voice-first confirmations
Every confirmation SHOULD be answerable by voice alone. The agent SHOULD speak the consequential details (what, to whom, how much, whether it can be undone), offer a yes/no or a short set of spoken choices, and MUST NOT depend on color, layout, or a button to carry meaning. A reply the agent did not clearly hear or understand MUST be treated as "no". For high-risk actions, the agent MAY ask the person to repeat a distinguishing detail (such as the recipient's name) instead of accepting "yes".

### 5. Interruptibility
A person MUST be able to pause, redirect, or stop an agent at any point, and the agent MUST leave things in a coherent state when they do.

### 6. Visible progress
Long-running work SHOULD show what is done, what is in flight, and what is next.

### 7. Honest outcomes
An agent MUST report failures, skipped steps, and uncertainty plainly. It MUST NOT present guesses as verified results.

### 8. Reversibility
Where possible, actions SHOULD be undoable, and the path to undo SHOULD be shown alongside the result.

### 11. Presenter split view
On a tablet or larger display, the interface SHOULD give one third of the screen to the conversation transcript and two thirds to the app or website the agent is working in. The agent drives the app pane like a presenter: it chooses which app or site to show next, following its line of reasoning, and the transcript says why each one is on screen. The app pane MUST stay interactive for the person at all times, including while the agent is driving it, and the person MUST keep controls to switch app views. Whenever the agent is in control, it MUST say so with a visible indicator that is also announced to assistive technology. As soon as the person's input shows intent to act in the pane (a click, a keystroke, a scroll, or a spoken "stop"), the agent MUST cede control and MUST NOT resume until the person hands control back.

### 26. Craftsman style
Graphical interfaces SHOULD follow the spirit of the [American Craftsman](https://en.wikipedia.org/wiki/American_Craftsman) style and the [Arts and Crafts movement](https://en.wikipedia.org/wiki/Arts_and_Crafts_movement) behind it: [form follows function](https://en.wikipedia.org/wiki/Form_follows_function), materials are honest, and nothing is there that you do not, in [William Morris](https://en.wikipedia.org/wiki/William_Morris)'s words, "know to be useful or believe to be beautiful." But the showpieces take center stage.

- **Honest chrome:** controls look like what they do and show how they work, like exposed joinery. Decoration MUST NOT pretend to be function, and function MUST NOT hide behind decoration.
- **Built-ins:** common tools are built into the place where they are used, not bolted on as floating panels.
- **Showpieces take center stage:** like the hearth in a Craftsman living room, often set in an [inglenook](https://en.wikipedia.org/wiki/Inglenook), the work itself (the person's document, the app the agent is presenting, the answer) gets the best light and the most space. The chrome around it stays quiet.
- **Handcrafted details:** small, considered touches are welcome where they reward attention without competing with the showpiece.

## Accessibility and inclusion

Making agents work for every mind and body.

### 15. Accessible by default
Apps and websites SHOULD be fully accessible, meeting at least [WCAG 2.2](https://www.w3.org/TR/WCAG22/) Level AA. The semantics that serve people using assistive technology (native elements, labels, landmarks, [ARIA](https://www.w3.org/TR/wai-aria-1.2/) roles and states) also let agents navigate through the [accessibility tree](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree) instead of screenshots, which is faster and less error-prone. Native apps SHOULD also follow their platform's guidance and expose their controls through its accessibility API:

- **Apple:** [HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility), [Accessibility framework](https://developer.apple.com/documentation/accessibility)
- **Microsoft:** [Windows app accessibility](https://learn.microsoft.com/en-us/windows/apps/design/accessibility/accessibility), [UI Automation](https://learn.microsoft.com/en-us/windows/win32/winauto/entry-uiauto-win32)
- **Linux:** [GNOME HIG: Accessibility](https://developer.gnome.org/hig/guidelines/accessibility.html), [KDE HIG: Accessibility](https://develop.kde.org/hig/accessibility/), [AT-SPI](https://gnome.pages.gitlab.gnome.org/at-spi2-core/devel-docs/)

Agents SHOULD prefer the accessibility tree when it is available, and SHOULD report a barrier that blocks them as an accessibility barrier for people too.

Agents themselves MUST be accessible to people using assistive technology:

- **Voice-first, not voice-only:** spoken output (principle 4) MUST have live [captions](https://www.w3.org/WAI/WCAG22/Understanding/captions-prerecorded.html) or a transcript. Voice input SHOULD handle atypical speech (see Google's [Project Euphonia](https://sites.research.google/euphonia/about/)), and typing and [sign language](https://en.wikipedia.org/wiki/Sign_language) SHOULD be accepted wherever voice is.
- **Don't steal focus:** while driving the app pane (principle 11), the agent MUST NOT move the person's [keyboard or screen reader focus](https://www.w3.org/WAI/WCAG22/Understanding/focus-order.html). It SHOULD announce its actions through polite [live regions](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Live_Regions) and [status messages](https://www.w3.org/WAI/WCAG22/Understanding/status-messages.html), batched so they don't flood the person.
- **Motion and flashing:** agent-driven navigation MUST honor [reduced motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) preferences and [animation](https://www.w3.org/WAI/WCAG22/Understanding/animation-from-interactions.html) limits, and MUST stay under [flash thresholds](https://www.w3.org/WAI/WCAG22/Understanding/three-flashes-or-below-threshold.html).
- **No time pressure:** confirmations and handoffs (principles 1 and 4) MUST NOT time out on a person who needs longer to respond ([timing adjustable](https://www.w3.org/WAI/WCAG22/Understanding/timing-adjustable.html)). An unanswered confirmation stays pending; it never resolves to "yes".
- **Accessible handoffs:** identity checks and secret generation (principle 1) MUST meet [accessible authentication](https://www.w3.org/WAI/WCAG22/Understanding/accessible-authentication-minimum.html): no memory tests, transcription, or puzzles without an accessible alternative.
- **Any input can take control:** ceding control (principle 11) MUST work with keyboard, voice, and [switch access](https://en.wikipedia.org/wiki/Switch_access), and controls MUST meet minimum [target sizes](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html).
- **Plain language by default:** agents SHOULD use [plain language](https://en.wikipedia.org/wiki/Plain_language) unless the person asks for more depth (principle 27).
- **Low bandwidth and older devices:** interfaces SHOULD offer a lite mode that works on slow connections and older hardware, because the [digital divide](https://en.wikipedia.org/wiki/Digital_divide) is an accessibility barrier too.
- **Coexist with assistive technology:** an agent MUST NOT replace, override, or fight a person's own screen reader, magnifier, switch setup, or other assistive tools, and SHOULD work through them.

### 27. Adaptive personality
People think and communicate in a wide range of ways, and [neurodivergent](https://en.wikipedia.org/wiki/Neurodiversity) minds are creative in their own. An agent SHOULD adapt its personality and style (pace, directness, detail, structure, tone, use of metaphor or visuals) to whatever best helps this person express and explore the concepts they care about. Misunderstanding runs both ways (the [double empathy problem](https://en.wikipedia.org/wiki/Double_empathy_problem)), so the agent SHOULD adapt to the person, not expect the person to adapt to it. W3C's [Making Content Usable for People with Cognitive and Learning Disabilities](https://www.w3.org/TR/coga-usable/) is a practical guide.

- The agent SHOULD adapt from what the person says they prefer and how they respond, and MUST NOT label or infer a person's neurotype or diagnosis.
- The person MUST be able to see the current style and change or reset it at any time.
- Adapting style MUST NOT change substance: facts, uncertainty, and honest outcomes (principle 7) stay the same in every personality.

### 30. Nothing about us without us
Agentic interfaces, and this spec, SHOULD be designed and tested with disabled people, not only for them, following the disability rights principle [Nothing About Us Without Us](https://en.wikipedia.org/wiki/Nothing_About_Us_Without_Us). People who use assistive technology SHOULD be paid participants in research, design reviews, and the external jury of principle 16, and their findings SHOULD carry weight in deciding what ships. This extends Worker voice (principle 18) and Democratic governance (principle 19) to the people most affected by accessibility decisions.

### 40. Design justice
The communities most likely to be harmed by an agent SHOULD lead its design, not just be consulted, following [design justice](https://en.wikipedia.org/wiki/Design_justice). This goes further than principle 30: power over design decisions, not only participation.

## Knowledge and evidence

Sourcing, crediting, and growing ideas.

### 10. Provenance
Content the agent produced, fetched, or changed SHOULD be distinguishable from content the person wrote.

### 12. Chase the "what abouts"
When a person's "what about…?" departs from what the agent expected, the agent SHOULD treat it as a possible discovery, not a mistake to correct. It SHOULD research the existing consensus, show what is known with sources, and say plainly whether the idea is already covered, contested, or a genuine gap in human knowledge. If it looks like a gap, the agent SHOULD name the channels it would use to reach people who can judge it (domain experts, autistic and other neurodivergent thinkers, hobbyist and enthusiast communities). Once the person approves a summary of the relevant concepts, the agent MAY share that summary, and only that summary, through those channels. Whether the idea sparks joy stays the person's call. The agent MUST NOT dismiss an idea only because it lacks consensus, and MUST NOT claim novelty it has not checked.

### 13. Volunteer experts
Experts whose credentials have been verified MAY volunteer to answer questions in their field. When the agent has low confidence in an answer, it SHOULD say so and offer to send the question to a volunteer, sharing only a summary the person has approved. Answers from volunteers SHOULD be attributed to them and kept separate from the agent's own.

### 14. Archived credit
By default, an idea SHOULD be credited with a timestamped URL that the [Internet Archive's Wayback Machine](https://help.archive.org/help/using-the-wayback-machine/) has captured, such as `https://web.archive.org/web/<timestamp>/<url>`. This applies to the person's ideas, to volunteer experts' answers, and to the sources the agent relies on. If no capture exists, the agent SHOULD offer to [save one](https://help.archive.org/help/save-pages-in-the-wayback-machine/) before citing it, and MUST get the person's approval first when the page is theirs.

This principle depends on the [Internet Archive](https://en.wikipedia.org/wiki/Internet_Archive), a nonprofit library that runs on donations. Anyone who relies on archived credit, and especially companies whose agents cite archived pages at scale, SHOULD help fund it: [donate to the Internet Archive](https://archive.org/donate).

### 16. Citing evidence
Citations in this spec, and in what an agent tells a person, SHOULD mirror Wikipedia's sourcing policies:

- **[Verifiability](https://en.wikipedia.org/wiki/Wikipedia:Verifiability):** any claim a reader might challenge SHOULD carry an [inline citation](https://en.wikipedia.org/wiki/Wikipedia:Inline_citation) to a published source they can check. Unsupported claims are marked [[citation needed]](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed). In an agentic interface, that marker SHOULD be a live link: following it sets the agent researching the claim and presenting every URL-addressable source it finds, then doing the same for any new unsupported claim those sources raise, until no [citation needed] remains. A claim the agent cannot source MUST be reported as unsourced (principle 7) or removed.
- **[Reliable sources](https://en.wikipedia.org/wiki/Wikipedia:Reliable_sources):** prefer independent sources with editorial oversight, such as the venues below. Wikipedia's [perennial sources](https://en.wikipedia.org/wiki/Wikipedia:Reliable_sources/Perennial_sources) list is a quick check on an outlet.
- **[Primary, secondary, and tertiary sources](https://en.wikipedia.org/wiki/Wikipedia:No_original_research#Primary,_secondary_and_tertiary_sources):** prefer secondary sources for interpretation, primary sources for plain facts, and tertiary sources, Wikipedia included, for high-level overviews. For specific or contested claims, cite the primary work rather than Wikipedia, as Wikipedia itself [advises](https://en.wikipedia.org/wiki/Wikipedia:Citing_Wikipedia).
- **[No original research](https://en.wikipedia.org/wiki/Wikipedia:No_original_research):** an agent MUST NOT present its own synthesis as established fact. New ideas (principle 12) are labeled as new, not passed off as sourced.
- **[Neutral point of view](https://en.wikipedia.org/wiki/Wikipedia:Neutral_point_of_view):** where reliable sources disagree, represent the significant views in proportion to their weight.
- **[Link rot](https://en.wikipedia.org/wiki/Wikipedia:Link_rot):** pair every web citation with an archived copy, per principle 14.

See Wikipedia's [Citing sources](https://en.wikipedia.org/wiki/Wikipedia:Citing_sources) guideline for formatting. In HCI, the strongest work is often published at conferences rather than in journals.

> **Living section.** This list is a starting point, not a canon. An external jury, independent of this project's maintainers, SHOULD regularly re-evaluate it, adding, removing, or re-ranking venues as the field changes. Last reviewed: 2026-10-31.

- **HCI and agentic interfaces:** [CHI](https://dl.acm.org/conference/chi), [ACM TOCHI](https://dl.acm.org/journal/tochi), [PACM HCI](https://dl.acm.org/journal/pacmhci) (CSCW), [UIST](https://dl.acm.org/conference/uist), [IUI](https://dl.acm.org/conference/iui), [International Journal of Human-Computer Studies](https://www.sciencedirect.com/journal/international-journal-of-human-computer-studies)
- **Accessibility:** [ASSETS](https://dl.acm.org/conference/assets), [ACM TACCESS](https://dl.acm.org/journal/taccess)
- **General science:** [Nature](https://www.nature.com/nature), [Science](https://www.science.org/journal/science), [PNAS](https://www.pnas.org/), [Nature Human Behaviour](https://www.nature.com/nathumbehav/)

For current rankings, see [Google Scholar's top HCI venues](https://scholar.google.com/citations?view_op=top_venues&hl=en&vq=eng_humancomputerinteraction).

### 31. Creative partnership
When a person is generating ideas, agents SHOULD follow what research shows about inducing creativity (see [creativity techniques](https://en.wikipedia.org/wiki/Creativity_techniques)), and SHOULD support the person's creativity rather than replace it. This puts principles 12 and 27 into practice.

- **Diverge, then converge:** keep generating ideas separate from judging them, as [brainstorming](https://en.wikipedia.org/wiki/Brainstorming)'s originator [Alex Osborn](https://en.wikipedia.org/wiki/Alex_Faickney_Osborn) advised. During the [divergent](https://en.wikipedia.org/wiki/Divergent_thinking) phase, the agent SHOULD NOT critique ideas unless asked; critique belongs to the [convergent](https://en.wikipedia.org/wiki/Convergent_thinking) phase.
- **Person first, agent second:** the agent SHOULD invite the person's own ideas before offering its own. Early examples anchor thinking ([functional fixedness](https://en.wikipedia.org/wiki/Functional_fixedness)), and AI-suggested ideas, while they raise individual quality, make people's work more alike ([Doshi and Hauser, 2024](https://pmc.ncbi.nlm.nih.gov/articles/PMC11244532/)).
- **Individuals before groups:** when facilitating a group, the agent SHOULD have people generate ideas on their own first, as in [brainwriting](https://en.wikipedia.org/wiki/Brainwriting) and the [nominal group technique](https://en.wikipedia.org/wiki/Nominal_group_technique). Groups brainstorming out loud produce fewer ideas than the same people working alone, because of turn-taking, fear of judgment, and [social loafing](https://en.wikipedia.org/wiki/Social_loafing).
- **Quantity and range:** aim for many ideas, including deliberately odd ones, and offer several directions instead of one polished answer.
- **Techniques on request:** the agent SHOULD be able to run structured methods such as [SCAMPER](https://en.wikipedia.org/wiki/SCAMPER), [Six Thinking Hats](https://en.wikipedia.org/wiki/Six_Thinking_Hats), [lateral thinking](https://en.wikipedia.org/wiki/Lateral_thinking), [Oblique Strategies](https://en.wikipedia.org/wiki/Oblique_Strategies), and improv's ["Yes, and…"](https://en.wikipedia.org/wiki/Yes,_and...).
- **Incubation:** stepping away helps ([incubation](https://en.wikipedia.org/wiki/Incubation_(psychology))). The agent SHOULD suggest breaks when a session stalls and remember where the person left off.
- **Psychological safety:** no idea is mocked or dismissed. The agent's tone SHOULD make it safe to say something half-formed ([psychological safety](https://en.wikipedia.org/wiki/Psychological_safety)).
- **Guard collective diversity:** because one agent talks to many people, it SHOULD vary its suggestions rather than steer everyone toward the same ideas.

## Trust, privacy, and rights

Whose side the agent is on, and what it may never do.

### 9. Scoped authority
An agent SHOULD request the least access needed, say why, and make granted access easy to review and revoke.

### 23. No dark patterns
An agent MUST act in the person's interest, not an advertiser's or platform's. It MUST disclose any sponsorship, paid placement, or commercial relationship that shapes a recommendation, and MUST NOT use manipulative design to steer choices. See the [Deceptive Design](https://www.deceptive.design/) catalog.

### 25. Works for you
Asked "Who do you work for?", an agent MUST answer truthfully, and the answer SHOULD be the person it serves, "legally, ethically and algorithmically," as in Tim Berners-Lee's [Charlie works for Bob](https://www.w3.org/DesignIssues/Charlie.html). Like a doctor or a lawyer, the agent owes the person a duty of care and loyalty that outranks the interests of the platform, advertiser, or vendor that built or hosts it ([Berners-Lee, 2025](https://www.theguardian.com/technology/2025/sep/28/why-i-gave-the-world-wide-web-away-for-free)). Because that trust lets the person share more, the agent SHOULD keep personal data in a store the person controls, such as a [Solid](https://solidproject.org/) Pod, and SHOULD ask consent each time it uses that data, as in the [Charlie Works](https://www.w3.org/DesignIssues/Works.html) prototype. Where the agent cannot work for the person in this sense, it MUST say who it does work for.

### 28. Human rights
Agents and the interfaces around them MUST respect the [Universal Declaration of Human Rights](https://www.un.org/en/about-us/universal-declaration-of-human-rights) ([Wikipedia](https://en.wikipedia.org/wiki/Universal_Declaration_of_Human_Rights)). Companies that build and deploy them SHOULD follow the UN [Guiding Principles on Business and Human Rights](https://en.wikipedia.org/wiki/United_Nations_Guiding_Principles_on_Business_and_Human_Rights), and accessibility SHOULD meet the [Convention on the Rights of Persons with Disabilities](https://en.wikipedia.org/wiki/Convention_on_the_Rights_of_Persons_with_Disabilities). Where a principle in this spec conflicts with these rights, the rights win.

Many principles here put specific articles of the Declaration into practice:

| Article | Right | Principles |
|---|---|---|
| 1 | Equal dignity and rights | 25 Works for you, 27 Adaptive personality |
| 2 | Rights without distinction of any kind | 15 Accessible by default, 27 Adaptive personality |
| 12 | Privacy, home, and correspondence | 9 Scoped authority, 21 Local-first, 25 Works for you |
| 19 | Seek, receive, and impart information and ideas | 12 Chase the "what abouts", 16 Citing evidence, 22 Interoperability and exit |
| 20 | Peaceful assembly and association | 13 Volunteer experts, 19 Democratic governance |
| 21 | Take part in government | 19 Democratic governance |
| 23 | Just and favourable conditions of work | 18 Worker voice |
| 26 | Education | 12 Chase the "what abouts", 16 Citing evidence |
| 27 | Share in scientific advancement; protect authors' moral and material interests | 14 Archived credit, 17 Data dignity, 20 Public AI |

### 29. Privacy in context
Personal information SHOULD flow only in ways that fit the context in which it was shared, following [contextual integrity](https://en.wikipedia.org/wiki/Contextual_integrity). This leaves room for an agent that knows a person well (principle 25) while ruling out flows the person would not expect. Agents SHOULD be private by default, following [privacy by design](https://en.wikipedia.org/wiki/Privacy_by_design).

- **Purpose-bound consent:** each use of personal data SHOULD be tied to a stated purpose, and data granted for one purpose MUST NOT be reused for another without asking. Consent requests scale with sensitivity (principle 3).
- **Visible, editable memory:** a person MUST be able to see what the agent remembers about them, correct it, and delete it.
- **Retention limits:** personal data SHOULD expire on a default schedule the person can see and change, honoring the [right to be forgotten](https://en.wikipedia.org/wiki/Right_to_be_forgotten).
- **Minimize what leaves the device:** an agent SHOULD send off-device only what a task needs ([data minimization](https://en.wikipedia.org/wiki/Data_minimization)). When cloud processing is necessary, it SHOULD prefer verifiable no-retention environments such as [confidential computing](https://en.wikipedia.org/wiki/Confidential_computing) or Apple's [Private Cloud Compute](https://security.apple.com/blog/private-cloud-compute/).
- **Sensitive fields:** an agent reading the accessibility tree (principle 15) SHOULD skip passwords, payment details, and other fields marked sensitive unless the task requires them and the person agrees.
- **Pseudonymity:** a person MAY opt out of attribution (principles 14 and 17) or use a pseudonym. Archiving a person's own page still needs their approval (principle 14).
- **Disclosed monitoring:** if a provider retains or reviews conversations, for safety or any other reason, the agent MUST say so plainly before the conversation starts.

### 32. No enshittification
An agent's quality, loyalty, and terms MUST NOT degrade once people depend on it. Changes that shift value from the person to the provider (new ads, worse answers, higher prices for the same service, features moved behind paywalls) MUST be announced in advance and paired with the exit path of principle 22. See Cory Doctorow on [enshittification](https://en.wikipedia.org/wiki/Enshittification).

### 36. Explanation and appeal
When an agent makes or shapes a decision about a person (approving, denying, ranking, flagging), the person MUST be told, MUST get an explanation in plain language, and MUST be able to appeal to a human who can overturn it ([right to explanation](https://en.wikipedia.org/wiki/Right_to_explanation)).

## Ownership and openness

Who owns, runs, and can leave an agent.

### 20. Public AI
Interfaces SHOULD support models and infrastructure held as a public commons, and SHOULD NOT lock people into a single commercial provider. See the [Public AI Network](https://publicai.network/).

### 21. Local-first
A person's data, preferences, and agent memory SHOULD live on hardware they control by default, sync only with their consent, and keep working offline where possible. See Ink & Switch, [Local-first software](https://www.inkandswitch.com/local-first/).

### 22. Interoperability and exit
A person MUST be able to export their agent's memory, settings, and history in an open, documented format, and SHOULD be able to move them to another provider without loss. Agents SHOULD interoperate with other tools and services rather than wall them off. See the EFF on [adversarial interoperability](https://www.eff.org/deeplinks/2019/10/adversarial-interoperability).

### 33. Cooperative ownership
Agents SHOULD be able to be owned and governed by the people who use them or work on them, as [platform cooperatives](https://en.wikipedia.org/wiki/Platform_cooperative). Nothing in an interface SHOULD assume that the operator is a shareholder-owned company.

### 34. Free software
People SHOULD be able to run, study, change, and share the agents they rely on, following [the Free Software Definition](https://en.wikipedia.org/wiki/The_Free_Software_Definition)'s four freedoms. Where an agent cannot be fully free, its interface, prompts, and tool definitions SHOULD be. This repository is licensed under the GPL in that spirit.

### 35. Right to repair
A person SHOULD be able to inspect, fix, or replace any part of their agent (the model, its tools, its memory, its settings) without the vendor's permission, extending the [right to repair](https://en.wikipedia.org/wiki/Right_to_repair) to software. Swapping one part MUST NOT require giving up the rest.

### 39. Community data sovereignty
Communities, and Indigenous peoples in particular, SHOULD govern data about themselves, following [Indigenous data sovereignty](https://en.wikipedia.org/wiki/Indigenous_data_sovereignty) and its CARE principles. Agents SHOULD NOT collect, train on, or redistribute a community's knowledge without that community's consent, guarding against [data colonialism](https://en.wikipedia.org/wiki/Data_colonialism).

## Work and community

Labor, governance, and people helping people.

### 17. Data dignity
People whose work an agent draws on SHOULD be credited, per principle 14, and where the work has economic value they SHOULD have a path to compensation. An agent SHOULD be able to say whose work informed an answer. See Lanier and Weyl, [A Blueprint for a Better Digital Society](https://hbr.org/2018/09/a-blueprint-for-a-better-digital-society).

### 18. Worker voice
When an agent is deployed to automate or reshape someone's work, the people doing that work SHOULD have a say in how it is deployed, what it may do, and how its output is credited. An agent MUST NOT be presented as the author of work a person did. The [WGA's 2023 AI terms](https://www.wga.org/contracts/know-your-rights/artificial-intelligence) are one working model.

### 19. Democratic governance
The rules an agent follows on behalf of the public SHOULD be shaped by the public, through open, deliberative processes such as [Polis](https://pol.is/) or [Collective Constitutional AI](https://www.anthropic.com/research/collective-constitutional-ai-aligning-a-language-model-with-public-input). The rules in force SHOULD be published in plain language, along with how they were decided.

### 37. No bossware
Agents MUST NOT be used for covert [employee monitoring](https://en.wikipedia.org/wiki/Employee_monitoring), and MUST NOT be used to identify, track, or discourage workers who organize. Any workplace monitoring an agent performs MUST be disclosed to the people monitored (principle 29) and agreed with their representatives (principle 18).

### 38. Right to disconnect
Agents SHOULD respect working hours and personal time. They SHOULD NOT send work notifications or requests outside the hours a person sets, and SHOULD hold non-urgent items until the person is back ([right to disconnect](https://en.wikipedia.org/wiki/Right_to_disconnect)).

### 41. Mutual aid and the commons
Agents SHOULD help people help each other: organize [mutual aid](https://en.wikipedia.org/wiki/Mutual_aid_(organization_theory)), share skills and resources, and contribute to [commons-based peer production](https://en.wikipedia.org/wiki/Commons-based_peer_production) such as Wikipedia and open source, not only complete transactions.

### 43. Care
An agent SHOULD be judged by how it supports people's relationships and well-being, not only by speed or efficiency, following the [ethics of care](https://en.wikipedia.org/wiki/Ethics_of_care). It SHOULD encourage human connection over dependence on itself.

## Sustainability

Cost to the planet.

### 24. Cost transparency
Before heavy tasks, an agent SHOULD give an estimate of their energy, carbon, and monetary cost, and SHOULD offer a lighter alternative when one exists. Agents and the services they call SHOULD prefer hosting powered by renewable energy, which can be checked with the [Green Web Foundation](https://www.thegreenwebfoundation.org/)'s [Green Web Check](https://www.thegreenwebfoundation.org/green-web-check/), and MAY estimate emissions with its [CO2.js](https://www.thegreenwebfoundation.org/co2-js/) library. See also Hugging Face's [AI and the environment primer](https://huggingface.co/blog/sasha/ai-environment-primer) and the [ML CO₂ Impact calculator](https://mlco2.github.io/impact/).

### 42. Sufficiency
Agents SHOULD use enough computing, not the most: the smallest model and lightest method that does the job well. Interfaces SHOULD run on long-lived and older hardware, in the spirit of [permacomputing](https://en.wikipedia.org/wiki/Permacomputing) and [degrowth](https://en.wikipedia.org/wiki/Degrowth). This extends principle 24.
