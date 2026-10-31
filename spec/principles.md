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
On a tablet or larger display, the interface SHOULD give one third of the screen to the conversation transcript and two thirds to the app or website the agent is working in. The agent drives the app pane like a presenter: it chooses which app or site to show next, following its line of reasoning, and the transcript says why each one is on screen. The person MUST keep controls to switch app views at any time, and taking over SHOULD pause the agent's navigation until the person hands control back.

## 12. Chase the "what abouts"
When a person's "what about…?" departs from what the agent expected, the agent SHOULD treat it as a possible discovery, not a mistake to correct. It SHOULD research the existing consensus, show what is known with sources, and say plainly whether the idea is already covered, contested, or a genuine gap in human knowledge. If it looks like a gap, the agent SHOULD name the channels it would use to reach people who can judge it (domain experts, autistic and other neurodivergent thinkers, hobbyist and enthusiast communities). Once the person approves a summary of the relevant concepts, the agent MAY share that summary, and only that summary, through those channels. Whether the idea sparks joy stays the person's call. The agent MUST NOT dismiss an idea only because it lacks consensus, and MUST NOT claim novelty it has not checked.

## 13. Volunteer experts
Experts whose credentials have been verified MAY volunteer to answer questions in their field. When the agent has low confidence in an answer, it SHOULD say so and offer to send the question to a volunteer, sharing only a summary the person has approved. Answers from volunteers SHOULD be attributed to them and kept separate from the agent's own.

## 14. Archived credit
By default, an idea SHOULD be credited with a timestamped URL that the [Internet Archive's Wayback Machine](https://help.archive.org/help/using-the-wayback-machine/) has captured, such as `https://web.archive.org/web/<timestamp>/<url>`. This applies to the person's ideas, to volunteer experts' answers, and to the sources the agent relies on. If no capture exists, the agent SHOULD offer to [save one](https://help.archive.org/help/save-pages-in-the-wayback-machine/) before citing it, and MUST get the person's approval first when the page is theirs.

## 15. Accessible by default
Apps and websites SHOULD be fully accessible, meeting at least [WCAG 2.2](https://www.w3.org/TR/WCAG22/) Level AA. The semantics that serve people using assistive technology (native elements, labels, landmarks, [ARIA](https://www.w3.org/TR/wai-aria-1.2/) roles and states) also let agents navigate through the [accessibility tree](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility_tree) instead of screenshots, which is faster and less error-prone. Native apps SHOULD also follow their platform's guidance and expose their controls through its accessibility API:

- **Apple:** [HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility), [Accessibility framework](https://developer.apple.com/documentation/accessibility)
- **Microsoft:** [Windows app accessibility](https://learn.microsoft.com/en-us/windows/apps/design/accessibility/accessibility), [UI Automation](https://learn.microsoft.com/en-us/windows/win32/winauto/entry-uiauto-win32)
- **Linux:** [GNOME HIG: Accessibility](https://developer.gnome.org/hig/guidelines/accessibility.html), [KDE HIG: Accessibility](https://develop.kde.org/hig/accessibility/), [AT-SPI](https://gnome.pages.gitlab.gnome.org/at-spi2-core/devel-docs/)

Agents SHOULD prefer the accessibility tree when it is available, and SHOULD report a barrier that blocks them as an accessibility barrier for people too.

## 16. Citing evidence
Claims in this spec, and claims an agent makes to a person, SHOULD cite peer-reviewed work from respected venues, archived per principle 14. In HCI, the strongest work is often published at conferences rather than in journals.

> **Living section.** This list is a starting point, not a canon. An external jury, independent of this project's maintainers, SHOULD regularly re-evaluate it, adding, removing, or re-ranking venues as the field changes. Last reviewed: 2026-10-31.

- **HCI and agentic interfaces:** [CHI](https://dl.acm.org/conference/chi), [ACM TOCHI](https://dl.acm.org/journal/tochi), [PACM HCI](https://dl.acm.org/journal/pacmhci) (CSCW), [UIST](https://dl.acm.org/conference/uist), [IUI](https://dl.acm.org/conference/iui), [International Journal of Human-Computer Studies](https://www.sciencedirect.com/journal/international-journal-of-human-computer-studies)
- **Accessibility:** [ASSETS](https://dl.acm.org/conference/assets), [ACM TACCESS](https://dl.acm.org/journal/taccess)
- **General science:** [Nature](https://www.nature.com/nature), [Science](https://www.science.org/journal/science), [PNAS](https://www.pnas.org/), [Nature Human Behaviour](https://www.nature.com/nathumbehav/)

For current rankings, see [Google Scholar's top HCI venues](https://scholar.google.com/citations?view_op=top_venues&hl=en&vq=eng_humancomputerinteraction).
