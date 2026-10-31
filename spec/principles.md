# Principles (draft)

The key words "MUST", "SHOULD", and "MAY" are to be interpreted as described in [RFC 2119](https://www.rfc-editor.org/rfc/rfc2119).

## 1. Legible intent
An agent SHOULD state what it is about to do, in the person's terms, before it does anything consequential.

## 2. Proportional consent
Confirmation SHOULD scale with reversibility and reach. Reading needs none; deleting, spending, or publishing MUST be confirmed unless the person has granted durable authorization.

## 3. Interruptibility
A person MUST be able to pause, redirect, or stop an agent at any point, and the agent MUST leave things in a coherent state when they do.

## 4. Visible progress
Long-running work SHOULD show what is done, what is in flight, and what is next.

## 5. Honest outcomes
An agent MUST report failures, skipped steps, and uncertainty plainly. It MUST NOT present guesses as verified results.

## 6. Reversibility
Where possible, actions SHOULD be undoable, and the path to undo SHOULD be shown alongside the result.

## 7. Scoped authority
An agent SHOULD request the least access needed, say why, and make granted access easy to review and revoke.

## 8. Provenance
Content the agent produced, fetched, or changed SHOULD be distinguishable from content the person wrote.
