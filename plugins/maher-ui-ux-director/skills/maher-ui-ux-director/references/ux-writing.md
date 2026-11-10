# UX writing and human microcopy

## Purpose

Words help users understand, decide, act, recover, and confirm. They are not decoration and should not sound like a chatbot, a generic marketing template, or a translation of implementation terminology.

## Core rules

- Write from the user's perspective and use the words users know.
- Prefer plain, concrete language and active voice.
- Give each text element one job.
- Name actions by their result: “Save changes,” “Send invitation,” or “Request return.”
- Keep the same term through the flow. If the button says “Publish,” the success state says “Published.”
- State what the system did, what remains, and what the user can do next.
- Use specific evidence and measured facts. Delete vague claims, fake proof, and empty superlatives.
- Match tone to the brand, audience, risk, and moment. Transactional errors should be calm and precise.

## Remove writing patterns that reveal generic AI output

Rewrite or delete:

- filler such as “It is important to note,” “in order to,” and generic conclusions;
- vague attribution such as “experts believe” without a named source;
- forced groups of three and false “from X to Y” ranges;
- “not only X, but also Y” framing when a direct statement works;
- synonym cycling that renames the same object repeatedly;
- abstract hype such as “revolutionize,” “seamless,” “cutting-edge,” “empower,” “elevate,” or “unlock” without a concrete mechanism;
- excessive participial phrases such as “ensuring,” “showcasing,” and “fostering” when they add no fact;
- unnecessary em dashes, colons, bold lead-ins, title-case headings, decorative emojis, and exclamation marks;
- chatbot filler such as “Of course,” “Great question,” “I hope this helps,” and “Let us know if…” inside product copy;
- figurative technical jargon when a concrete word exists;
- dense sentences that require rereading;
- claims that could be pasted unchanged into another product.

Do not remove brand character or natural conversational language merely to make copy short.

## Interface patterns

### Buttons

- Use a verb plus the real object or result.
- Avoid “Submit,” “Continue,” “Yes,” and “OK” when a more specific outcome is known.
- For destructive actions, name the action exactly: “Delete account,” not “Confirm.”
- Keep labels short without making them ambiguous.

### Labels and helper text

- Keep labels persistent and concise.
- Use helper text only for format, consequence, or information required before input.
- Do not repeat the label in the placeholder.
- Use examples that resemble real data but do not expose private information.

### Loading and progress

- Describe the actual operation: “Saving changes…” or “Generating invoice…”
- Do not promise completion while the authoritative operation is pending.
- For long operations, explain whether the user may leave and how completion will be communicated.

### Empty states

- Explain why the state is empty when that is not obvious.
- Offer the next relevant action.
- Avoid mood-only copy, jokes, and generic illustrations that obscure the task.

### Errors

- State what failed in user terms.
- State whether input or progress was preserved.
- Explain the next action or retry path.
- Do not apologize repeatedly or blame the user.
- Avoid raw server messages, codes, stack traces, and vague “Something went wrong” when a more specific explanation is available.

### Success

- Confirm the completed operation and important effect.
- Avoid celebratory banners for routine saves.
- Offer the next relevant action only when useful.

### Confirmation and destructive actions

- Name the affected object and scope.
- State irreversible or downstream consequences.
- Use the exact destructive verb on the confirmation action.
- Prefer undo for low-risk reversible actions; require confirmation for material irreversible actions.

## Arabic and mixed-language UI

- Write natural Modern Standard Arabic or the approved brand dialect; do not translate English structure word for word.
- Keep terminology consistent across Arabic and English versions.
- Use RTL for Arabic content and isolate English identifiers, email addresses, SKUs, codes, URLs, and numbers when needed.
- Format dates, numbers, currencies, units, and plural forms with locale-aware APIs.
- Test punctuation and icon direction in mixed strings. Do not mirror universally; mirror only directional icons and layouts that require it.
- Keep English product or technical names intact when translation would confuse users, and provide an Arabic explanation when necessary.
- Avoid long formal constructions when a direct sentence is clearer.

## Microcopy review

For every important string, ask:

1. Does it tell the user what they need to know or do?
2. Is it specific to this product and state?
3. Does it use the same term as the control and destination?
4. Does it remain accurate for loading, failure, retry, and permission conditions?
5. Can it be shorter without losing meaning?
6. Does the Arabic version sound written in Arabic rather than translated?

Use the linked `unslop` reference as a writing influence only. It does not replace visual UI, interaction, accessibility, or product-flow review.
