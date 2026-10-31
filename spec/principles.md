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
