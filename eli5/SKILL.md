---
name: eli5
description: Explain a concept the user already knows is hard — usually something from earlier in the conversation — by finding one faithful, everyday analogy that builds real intuition. Use whenever the user says "ELI5", "explain like I'm five", "explain it simply", "in plain terms", "dumb it down", "use an analogy", "break this down for me", "I don't get it, simpler", or otherwise asks to make a technical or abstract idea click. This is NOT baby talk — the audience is a smart adult who just lacks context in this domain. The job is to translate jargon and find the right analogy, never to condescend.
---

# ELI5 — the good kind

The reader is not a child. They're a smart adult missing context in *this* domain. So assume full adult reasoning (cause and effect, a few moving parts, "but here's the catch") and zero domain jargon. The goal is fast, honest intuition that lets them predict how the thing behaves. Baby talk ("imagine you have some yummy cookies") is condescending and useless.

## Method

1. **Find the keystone.** Most hard concepts have one load-bearing idea. Explain that; skip the rest.
2. **Use one faithful analogy.** It must map the *structure and cause-and-effect*, not just the vibe — if the reader pushes on it, it should still give the right answer. Pull from universal experience (kitchens, mail, libraries, queues, traffic, money, plumbing, an office). Decorative-but-wrong analogies feel like understanding and produce none.
3. **Translate jargon, don't hide it.** This is the line between ELI5 and baby talk. Name the real term once, then give the plain version ("embeddings — turning each word into a list of numbers so similar meanings land near each other"). They should leave able to recognize the term in the wild.
4. **Build familiar → unfamiliar,** one new idea at a time. Stay concrete: specific objects and numbers ("a librarian with 10 million books and one afternoon"), not abstractions.
5. **Name where the analogy breaks,** when it matters. One honest caveat is what separates a correct mental model from a confidently-wrong one — and it's why this isn't dumbing down. But simplify, never falsify.

## Output

Short. One strong analogy beats three weak ones; length kills the "click." Loose shape: a one-sentence hook (the analogy plainly stated), a short paragraph unpacking it and mapping each part back to the real terms, and a one-line "where it breaks" when needed. Use prose, not bullet sprawl or headers. Match the reader's register — an engineer gets a sharper, faster analogy than a beginner.

If the request points at earlier discussion ("ELI5 that"), explain *their* specific thing — pull it from the conversation, searching history if it's not in view.

## Example — vector search / embeddings

> Every document gets pinned to a giant map, with similar meanings pinned close together. To search, you don't read everything — you drop a pin where your question lands and grab what's nearby.
>
> Turning each document into map coordinates is the "embedding" (a list of numbers where closeness = similar meaning); finding nearest pins is the "vector search." It's fast because measuring distance beats re-reading 10 million documents.
>
> *Where it breaks:* these maps have hundreds of dimensions, not two — so "nearby" is richer than physical closeness, but the instinct holds.