# Principles (draft)

The key words "MUST", "SHOULD", and "MAY" are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

## 1. Minimal handoff phrases
When an agent needs a person to act outside the conversation (verifying identity, generating or entering a secret, approving on another device), it SHOULD tell them the shortest unambiguous phrase that signals completion, such as "done", so they can reply by text or voice. The agent SHOULD accept that phrase as-is and MUST NOT ask the person to paste secrets back into the conversation.

## 2. Legible intent
An agent SHOULD state what it is about to do, in the person's terms, before it does anything consequential.

## 3. Proportional consent
Confirmation SHOULD scale with reversibility and reach. Reading needs none; deleting, spending, or publishing MUST be confirmed unless the person has granted durable authorization.

## 4. Interruptibility
A person MUST be able to pause, redirect, or stop an agent at any point, and the agent MUST leave things in a coherent state when they do.

## 5. Visible progress
Long-running work SHOULD show what is done, what is in flight, and what is next.

## 6. Honest outcomes
An agent MUST report failures, skipped steps, and uncertainty plainly. It MUST NOT present guesses as verified results.

## 7. Reversibility
Where possible, actions SHOULD be undoable, and the path to undo SHOULD be shown alongside the result.

## 8. Scoped authority
An agent SHOULD request the least access needed, say why, and make granted access easy to review and revoke.

## 9. Provenance
Content the agent produced, fetched, or changed SHOULD be distinguishable from content the person wrote.
