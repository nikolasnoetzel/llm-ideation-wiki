---
name: paul-graham
description: Evaluate a business idea the way Paul Graham would, grounded in verbatim quotes from his essays. Use when the user asks "what would Paul Graham say", "be my Paul Graham", "PG lens", "YC view", or when /grill-me needs a founder-mental-model pass on an idea overview.
---

Judge an idea with Paul Graham's heuristics and his words, not with generic startup advice.

**Read first.**

1. The idea's `wiki/<idea-slug>/overview` in Notion (and `Grill Me` if it exists). Do not ask for what the overview already says.
2. `.agents/skills/paul-graham/references/heuristics.md`: the twenty heuristics, each with its essay, a verbatim quote, and the question to ask.
3. For any claim you want to quote, open the essay itself in `.agents/skills/paul-graham/references/essays/` (file names in `references/essays-index.md`). Grep the corpus for topics: `grep -ril "<term>" .agents/skills/paul-graham/references/essays/`.

**Produce, in this order.**

1. **What he would like.** Three to five bullets. Each bullet: the heuristic, a verbatim quote with essay title, date and canonical URL, and one line on how it applies to this idea.
2. **What he would push back on.** Same shape. Lead with the objection most likely to kill the idea.
3. **The organic test.** Ask whether the founders noticed the problem in their own life or decided it from afar. Name the evidence either way.
4. **The growth test.** Ask whether this is "a company designed to grow fast" or a service business. Name the repeatable loop or its absence.
5. **Default alive.** Name the cash and working-capital risks he would model before raising.
6. **Verdict sketch,** marked `^[inferred]`: likes, pushes back, and the one instruction he would give (usually: narrow the segment, do N things by hand, measure one number, come back).
7. **Questions for the founders.** Three to five, one line each, ordered by how much the answer would move the verdict. Hand them to `/grill-me`.

**Rules.**

- Quote verbatim from the corpus. Never invent or paraphrase a quote as if it were one. If the corpus does not support a point, say so and mark the point `^[inferred]`.
- The corpus ends in June 2025 (newest: The Shape of the Essay Field). For anything he said later, cite the external source and mark it `[uncertain]` unless the primary page was read.
- One idea per sentence, active voice, no padding. Calibrate: a kill needs evidence as much as a green light does.
- Write the result into the idea's `Grill Me` page (section "Paul Graham's lens") via the Notion workflow in `AGENTS.md`, or return it in chat if the user only asked a question. Run the ritual after a durable write.
- Steve Jobs is optional and secondary. If asked, apply "start with the customer experience and work backwards to the technology" and "focusing is about saying no", and mark the wording `[uncertain]` (no official transcript exists).
