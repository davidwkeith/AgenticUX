# Principles (draft)

The key words "MUST", "SHOULD", and "MAY" are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

## 1. Minimal handoff phrases
When an agent needs a person to act outside the conversation (verifying identity, generating or entering a secret, approving on another device), it SHOULD tell them the shortest unambiguous phrase that signals completion, such as "done", so they can reply by text or voice. The agent SHOULD accept that phrase as-is and MUST NOT ask the person to paste secrets back into the conversation.

## 2. Legible intent
An agent SHOULD state what it is about to do, in the person's terms, before it does anything consequential.

## 3. Proportional consent
Confirmation SHOULD scale with reversibility and reach. Reading needs none; deleting, spending, or publishing MUST be confirmed unless the person has granted durable authorization.

## 4. Voice-first confirmations
Every confirmation SHOULD be answerable by voice alone. The agent SHOULD speak the consequential details (what, to whom, how much, whether it can be undone), offer a yes/no or a short set of spoken choices, and MUST NOT depend on color, layout, or a button to carry meaning. A reply the agent did not clearly hear or understand MUST be treated as "no". For high-risk actions, the agent MAY ask the person to repeat a distinguishing detail (such as the recipient's name) instead of accepting "yes".

## 5. Interruptibility
A person MUST be able to pause, redirect, or stop an agent at any point, and the agent MUST leave things in a coherent state when they do.

## 6. Visible progress
Long-running work SHOULD show what is done, what is in flight, and what is next.

## 7. Honest outcomes
An agent MUST report failures, skipped steps, and uncertainty plainly. It MUST NOT present guesses as verified results.

## 8. Reversibility
Where possible, actions SHOULD be undoable, and the path to undo SHOULD be shown alongside the result.

## 9. Scoped authority
An agent SHOULD request the least access needed, say why, and make granted access easy to review and revoke.

## 10. Provenance
Content the agent produced, fetched, or changed SHOULD be distinguishable from content the person wrote.

## 11. Presenter split view
On a tablet or larger display, the interface SHOULD give one third of the screen to the conversation transcript and two thirds to the app or website the agent is working in. The agent drives the app pane like a presenter: it chooses which app or site to show next, following its line of reasoning, and the transcript says why each one is on screen. The app pane MUST stay interactive for the person at all times, including while the agent is driving it, and the person MUST keep controls to switch app views. Whenever the agent is in control, it MUST say so with a visible indicator that is also announced to assistive technology. As soon as the person's input shows intent to act in the pane (a click, a keystroke, a scroll, or a spoken "stop"), the agent MUST cede control and MUST NOT resume until the person hands control back.

## 12. Chase the "what abouts"
When a person's "what about…?" departs from what the agent expected, the agent SHOULD treat it as a possible discovery, not a mistake to correct. It SHOULD research the existing consensus, show what is known with sources, and say plainly whether the idea is already covered, contested, or a genuine gap in human knowledge. If it looks like a gap, the agent SHOULD name the channels it would use to reach people who can judge it (domain experts, autistic and other neurodivergent thinkers, hobbyist and enthusiast communities). Once the person approves a summary of the relevant concepts, the agent MAY share that summary, and only that summary, through those channels. Whether the idea sparks joy stays the person's call. The agent MUST NOT dismiss an idea only because it lacks consensus, and MUST NOT claim novelty it has not checked.

## 13. Volunteer experts
Experts whose credentials have been verified MAY volunteer to answer questions in their field. When the agent has low confidence in an answer, it SHOULD say so and offer to send the question to a volunteer, sharing only a summary the person has approved. Answers from volunteers SHOULD be attributed to them and kept separate from the agent's own.

## 14. Archived credit
By default, an idea SHOULD be credited with a timestamped URL that the [Internet Archive's Wayback Machine](https://help.archive.org/help/using-the-wayback-machine/) has captured, such as `https://web.archive.org/web/<timestamp>/<url>`. This applies to the person's ideas, to volunteer experts' answers, and to the sources the agent relies on. If no capture exists, the agent SHOULD offer to [save one](https://help.archive.org/help/save-pages-in-the-wayback-machine/) before citing it, and MUST get the person's approval first when the page is theirs.

This principle depends on the [Internet Archive](https://en.wikipedia.org/wiki/Internet_Archive), a nonprofit library that runs on donations. Anyone who relies on archived credit, and especially companies whose agents cite archived pages at scale, SHOULD help fund it: [donate to the Internet Archive](https://archive.org/donate).

## 15. Accessible by default
Apps and websites SHOULD be fully accessible, meeting at least [WCAG 2.2](https://www.w3.org/TR/WCAG22/) Level AA. The semantics that serve people using assistive technology (native elements, labels, landmarks, [ARIA](https://www.w3.org/TR/wai-aria-1.2/) roles and states) also let agents navigate through the [accessibility tree](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree) instead of screenshots, which is faster and less error-prone. Native apps SHOULD also follow their platform's guidance and expose their controls through its accessibility API:

- **Apple:** [HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility), [Accessibility framework](https://developer.apple.com/documentation/accessibility)
- **Microsoft:** [Windows app accessibility](https://learn.microsoft.com/en-us/windows/apps/design/accessibility/accessibility), [UI Automation](https://learn.microsoft.com/en-us/windows/win32/winauto/entry-uiauto-win32)
- **Linux:** [GNOME HIG: Accessibility](https://developer.gnome.org/hig/guidelines/accessibility.html), [KDE HIG: Accessibility](https://develop.kde.org/hig/accessibility/), [AT-SPI](https://gnome.pages.gitlab.gnome.org/at-spi2-core/devel-docs/)

Agents SHOULD prefer the accessibility tree when it is available, and SHOULD report a barrier that blocks them as an accessibility barrier for people too.

## 16. Citing evidence
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

## 17. Data dignity
People whose work an agent draws on SHOULD be credited, per principle 14, and where the work has economic value they SHOULD have a path to compensation. An agent SHOULD be able to say whose work informed an answer. See Lanier and Weyl, [A Blueprint for a Better Digital Society](https://hbr.org/2018/09/a-blueprint-for-a-better-digital-society).

## 18. Worker voice
When an agent is deployed to automate or reshape someone's work, the people doing that work SHOULD have a say in how it is deployed, what it may do, and how its output is credited. An agent MUST NOT be presented as the author of work a person did. The [WGA's 2023 AI terms](https://www.wga.org/contracts/know-your-rights/artificial-intelligence) are one working model.

## 19. Democratic governance
The rules an agent follows on behalf of the public SHOULD be shaped by the public, through open, deliberative processes such as [Polis](https://pol.is/) or [Collective Constitutional AI](https://www.anthropic.com/research/collective-constitutional-ai-aligning-a-language-model-with-public-input). The rules in force SHOULD be published in plain language, along with how they were decided.

## 20. Public AI
Interfaces SHOULD support models and infrastructure held as a public commons, and SHOULD NOT lock people into a single commercial provider. See the [Public AI Network](https://publicai.network/).

## 21. Local-first
A person's data, preferences, and agent memory SHOULD live on hardware they control by default, sync only with their consent, and keep working offline where possible. See Ink & Switch, [Local-first software](https://www.inkandswitch.com/local-first/).

## 22. Interoperability and exit
A person MUST be able to export their agent's memory, settings, and history in an open, documented format, and SHOULD be able to move them to another provider without loss. Agents SHOULD interoperate with other tools and services rather than wall them off. See the EFF on [adversarial interoperability](https://www.eff.org/deeplinks/2019/10/adversarial-interoperability).

## 23. No dark patterns
An agent MUST act in the person's interest, not an advertiser's or platform's. It MUST disclose any sponsorship, paid placement, or commercial relationship that shapes a recommendation, and MUST NOT use manipulative design to steer choices. See the [Deceptive Design](https://www.deceptive.design/) catalog.

## 24. Cost transparency
Before heavy tasks, an agent SHOULD give an estimate of their energy, carbon, and monetary cost, and SHOULD offer a lighter alternative when one exists. Agents and the services they call SHOULD prefer hosting powered by renewable energy, which can be checked with the [Green Web Foundation](https://www.thegreenwebfoundation.org/)'s [Green Web Check](https://www.thegreenwebfoundation.org/green-web-check/), and MAY estimate emissions with its [CO2.js](https://www.thegreenwebfoundation.org/co2-js/) library. See also Hugging Face's [AI and the environment primer](https://huggingface.co/blog/sasha/ai-environment-primer) and the [ML CO₂ Impact calculator](https://mlco2.github.io/impact/).

## 25. Works for you
Asked "Who do you work for?", an agent MUST answer truthfully, and the answer SHOULD be the person it serves, "legally, ethically and algorithmically," as in Tim Berners-Lee's [Charlie works for Bob](https://www.w3.org/DesignIssues/Charlie.html). Like a doctor or a lawyer, the agent owes the person a duty of care and loyalty that outranks the interests of the platform, advertiser, or vendor that built or hosts it ([Berners-Lee, 2025](https://www.theguardian.com/technology/2025/sep/28/why-i-gave-the-world-wide-web-away-for-free)). Because that trust lets the person share more, the agent SHOULD keep personal data in a store the person controls, such as a [Solid](https://solidproject.org/) Pod, and SHOULD ask consent each time it uses that data, as in the [Charlie Works](https://www.w3.org/DesignIssues/Works.html) prototype. Where the agent cannot work for the person in this sense, it MUST say who it does work for.

## 26. Craftsman style
Graphical interfaces SHOULD follow the spirit of the [American Craftsman](https://en.wikipedia.org/wiki/American_Craftsman) style and the [Arts and Crafts movement](https://en.wikipedia.org/wiki/Arts_and_Crafts_movement) behind it: [form follows function](https://en.wikipedia.org/wiki/Form_follows_function), materials are honest, and nothing is there that you do not, in [William Morris](https://en.wikipedia.org/wiki/William_Morris)'s words, "know to be useful or believe to be beautiful." But the showpieces take center stage.

- **Honest chrome:** controls look like what they do and show how they work, like exposed joinery. Decoration MUST NOT pretend to be function, and function MUST NOT hide behind decoration.
- **Built-ins:** common tools are built into the place where they are used, not bolted on as floating panels.
- **Showpieces take center stage:** like the hearth in a Craftsman living room, often set in an [inglenook](https://en.wikipedia.org/wiki/Inglenook), the work itself (the person's document, the app the agent is presenting, the answer) gets the best light and the most space. The chrome around it stays quiet.
- **Handcrafted details:** small, considered touches are welcome where they reward attention without competing with the showpiece.

## 27. Adaptive personality
People think and communicate in a wide range of ways, and [neurodivergent](https://en.wikipedia.org/wiki/Neurodiversity) minds are creative in their own. An agent SHOULD adapt its personality and style (pace, directness, detail, structure, tone, use of metaphor or visuals) to whatever best helps this person express and explore the concepts they care about. Misunderstanding runs both ways (the [double empathy problem](https://en.wikipedia.org/wiki/Double_empathy_problem)), so the agent SHOULD adapt to the person, not expect the person to adapt to it. W3C's [Making Content Usable for People with Cognitive and Learning Disabilities](https://www.w3.org/TR/coga-usable/) is a practical guide.

- The agent SHOULD adapt from what the person says they prefer and how they respond, and MUST NOT label or infer a person's neurotype or diagnosis.
- The person MUST be able to see the current style and change or reset it at any time.
- Adapting style MUST NOT change substance: facts, uncertainty, and honest outcomes (principle 7) stay the same in every personality.

## 28. Human rights
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
