<!-- Human Copywriting skill for ChatGPT Projects. Upload this file to the Project and add
one line to the Project Instructions: "Follow HUMAN_COPYWRITING.md for all drafting and
rewriting." The Claude version with the full guide, research notes and prose_check.py is at
https://github.com/madebybeings/human-copywriting-skill -->

# Human Copywriting

Write and rewrite prose that reads as if a specific person chose every sentence for a specific
reader, while keeping every fact, number, name and caveat exactly as the source has it.

Version 1.0.0 by [Made By Beings](https://madebybeings.com), adapted from Cameron Knight's
Human Copywriting Project Skill v1.1 (a ChatGPT Project skill), which builds on Stephen Offer's
[human-voice](https://github.com/stephenoffer/human-voice) (MIT). The pattern catalogue also draws
on [blader/humanizer](https://github.com/blader/humanizer) (MIT) and Wikipedia's
[Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide.
Licences and attribution: `NOTICE` in the repository root.

## Layering with your own voice

This skill is a base layer. Put your own style guide on top of it.

| Layer | Governs |
|---|---|
| **This skill** | Structure, selectivity, rhythm, the AI-tell catalogue, fact integrity. |
| Your style guide | Voice, vocabulary, greetings, warmth, habits. Wins on voice. |
| The task or channel | Format and what the piece must contain. Wins on format. |

Facts beat all three.

## Reference material (below in this file)

- `references/full-guide.md`: registers, the 18 editing passes, anti-overcorrection, self-critique
  and audit output. **Read it before any Full-depth job** (published article, homepage, proposal).
- `references/ai-tells.md`: the pattern catalogue, strongest first, with before and after pairs.
  Read it for any rewrite of AI-drafted text.
- `references/research.md`: what the studies actually show about human and model writing. Cite
  from here, never from memory.
- `scripts/prose_check.py`: a mechanical pre-flight (dashes, Oxford commas, stock phrases,
  sentence-length band, repeated openers). It flags. It never decides.

## The core idea

Machine-sounding prose is mostly an editorial problem, not a vocabulary problem. A model makes the
choice that fits the widest range of readers, so its drafts explain everything, weight every
point equally, resolve every tension and end on a lesson. A person writing for one reader makes
uneven, specific choices: more space for what matters, nothing for what the reader already knows,
and an ending that stops when the point has landed.

So work in this order, and touch wording last:

1. **Intent**: what must the reader understand, feel, decide or do?
2. **Shape**: does the structure suit this channel, or is it chat-answer shape?
3. **Substance**: which real details, numbers and mechanisms carry the piece?
4. **Selectivity**: what gets a paragraph, what gets a sentence, what goes?
5. **Rhythm**: does sentence length follow the thought, or sit in one band?
6. **Syntax**: stacked model habits (cleft openers, trailing "-ing" riders, not X but Y).
7. **Stance**: say what you think where the evidence supports it.
8. **Consistency**: one term per concept, one dialect, one relationship with the reader.
9. **Diction**: inflated words, stock transitions.
10. **Mechanics**: punctuation and house style.

## Non-negotiables

1. **Never invent support.** No invented fact, statistic, date, quote, citation, customer, result,
   anecdote, testimonial or personal detail, to make copy feel human or for any other reason. If
   a missing detail matters, ask one compact batch of questions. If it must be visible, mark it
   `[SOURCE NEEDED]`, `[VERIFY]` or `[FIGURE?]`. Otherwise write around the gap.
2. **Lock factual invariants in a rewrite**: numbers, dates, names, product and feature names,
   code, commands, paths, URLs, citations, the strength and direction of every claim, caveats,
   scope conditions and attributions. A smoother sentence is never worth a changed fact.
3. **Protect voice invariants** where they work: humour, bluntness, regional phrasing, an odd but
   natural sentence shape, a memorable awkward detail, a real preference or objection. The
   rewrite should still sound like the same sender.
4. **Never fake humanness.** No planted typos, random slang, forced lowercase, Unicode tricks,
   invisible characters, manufactured self-corrections or invented experiences.
5. **Detector-aware, never detector-led.** Detectors are one weak signal. Never degrade writing to
   move a score, and never promise that text will pass one.

## House defaults (edit these)

These are Made By Beings' defaults. Change them to match your own style guide.

- **No em dashes and no en dashes** in prose. Rewrite with a comma, colon, parentheses or a new
  sentence; never swap in a double hyphen. Don't overuse colons and semicolons to compensate.
- **No Oxford comma**: "design, build and launch". Reword if a list is ambiguous without it.
- **Australian English** unless the client, publication or source uses another dialect. Keep one
  dialect throughout.
- Hyphens in real compounds (drop-down, well-known) and required characters inside URLs, code,
  names and identifiers are untouched.

Apply this skill by default whenever you draft publishable prose. Relax it for literal tasks
(translation, extraction, summaries, grammar-only edits, legal or safety wording, quotes) and when
the user asks for a different style. Relax only the rule that conflicts.

## Modes

**Fix mode** (the user supplies prose): preserve meaning and claim strength, find the
communication job, lock invariants, strip assistant shape, cut what the reader doesn't need,
rebalance emphasis, rebuild rhythm, sharpen supported stance, test the ending and return the
finished copy.

**Generate mode** (the user supplies a brief): treat the brief and supplied sources as the fact
boundary. Start from the actual situation, not generic polished copy. Use the concrete detail you
have, give the most space to what matters most, and let the reader make obvious connections. Run
the same critique before returning.

## Depth

| Depth | Use for | Do |
|---|---|---|
| Quick | captions, short paragraphs, low-stakes copy | Silent job check, strip obvious tells, protect invariants. No audit. |
| Standard | web sections, social, sales copy, internal docs | The compact workflow below once, plus one self-critique. |
| Full | published articles, key pages, proposals | Read `references/full-guide.md`; run all 18 passes, the read-aloud and ownership tests, up to three critique rounds and the claim-preservation check. Run `scripts/prose_check.py` on the result. |

Stop when another pass would make the writing different rather than better.

## Compact workflow

1. Understand the job: reader, what they know, what they should do next.
2. Lock facts, then note voice worth keeping.
3. Gather the author's real material (a number, a failed attempt, a client's own words, a
   constraint). This is the strongest human signal there is, and it cannot be faked.
4. Decide what matters. Give it room. Compress or cut the rest.
5. Leave obvious implications unstated. Once a point lands, move on.
6. Rebuild shape for the channel: fewer headings, prose where bullets were reflexive, no recap.
7. Break symmetry that meaning doesn't justify (equal sections, a triad in every paragraph).
8. Rebuild rhythm so sentence length follows the thought.
9. Remove stacked syntax habits and templates (see `references/ai-tells.md`).
10. Sharpen stance where evidence supports it. Keep real uncertainty.
11. Unify voice: one term per concept, one dialect, stable formality.
12. Clean diction last.
13. Test the ending: delete the last paragraph; if nothing necessary goes, leave it out.
14. Read it aloud in your head.
15. Ownership test: could almost any company have published this? If yes, restore real context.
16. Claim check: no new claims, no changed numbers or names, no strengthened certainty, no
    dropped caveats, no changed links.

## The five tells that survive a rewrite

After any rewrite, search specifically for these, because they come back most often:

1. A "not X but Y" contrast, including the split and clipped forms.
2. A one-line closer that restates the paragraph above it.
3. A dash doing the work of a comma or colon.
4. A triad where the meaning has two items, or four.
5. A bold label on every bullet or a heading on every small idea.

## Output

Return the finished copy first. Don't announce that it was humanised, don't attach a score or
change log unless asked, and keep unresolved source gaps visible. If the user asks for an audit,
report only register, main patterns removed, invariants preserved, open sourcing gaps and residual
risks.

---

## AI tells: the pattern catalogue

Patterns that make prose read as model output, ordered from strongest signal to weakest. Group A
justifies an edit on a single sighting. Anything marked *weak alone* needs company from other
tells in the same passage before you act, because careful human writers use it on purpose too.

Sources: the structural passes in Cameron's Human Copywriting v1.1 (sections 12.9, 12.10, 12.14
and 12.15), the staging categories in [blader/humanizer](https://github.com/blader/humanizer) (MIT)
and the community taxonomy in Wikipedia's
[Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing). Descriptions
and examples here are our own wording.

**Why these exist.** A model predicts the most broadly acceptable next token, so by default it
signals importance instead of adding a fact, applies rhythm devices everywhere, inflates ordinary
claims and formats by rule. Word habits drift with each model release ("delve" peaked in 2024).
Structural habits persist, which is why structure leads this list.

**The fix is never a synonym.** State the point the sentence was circling. If a sentence has no
point once the tell is gone, delete it.

---

### A. Staging instead of stating (act on one sighting)

#### A1. Not X but Y

**Watch for:** "it's not X, it's Y"; "not just X, but Y"; "not only… but also"; the split form
("This doesn't mean X. It means Y."); the clipped tail (", no guesswork").
**Why it reads as AI:** the negative half rebuts a claim nobody made so the positive half sounds
bigger. Keep a contrast only when the reader actually believes the negative half.

> Before: A website isn't just a brochure. It's your hardest-working salesperson.
> After: Most of our clients' enquiries now arrive through the website before anyone picks up the phone. `[VERIFY: only if the client data says so]`

#### A2. One-line closers and dramatic fragments

**Watch for:** a single-sentence paragraph that restates the one above; "That's the real win.";
"Let that sink in."; a run of fragments ("No templates. No shortcuts. No compromise.").
**Why:** it asks the reader to pause without giving them anything new. A short sentence earns its
place when it carries a new fact.

> Before: We rebuilt the checkout in three weeks. Conversion went up 18%. The result? Growth.
> After: We rebuilt the checkout in three weeks and conversion went up 18%.

#### A3. Sayings that sound deep

**Watch for:** "at its core", "the real question is", "what really matters", "X is the language
of Y", "the currency of trust", "the architecture of growth".
**Why:** an ordinary point dressed as an aphorism. Replace it with the specific claim.

#### A4. A staged run-up before the point

**Watch for:** "Let's dive in", "Here's the thing", "Here's what you need to know", "Honestly?",
"The short answer?", "So, what does this mean for you?".
**Why:** it announces the point instead of making it. Delete the run-up and start with the point.

#### A5. Arguing with no one

**Watch for:** "To be clear", "This isn't to say", "Don't get me wrong", "You might think… but",
"A tempting approach would be".
**Why:** it answers an objection that appears nowhere else, usually left over from the model's own
drafting. Keep a rebuttal only if the reader genuinely holds the belief.

---

### B. Rhythm by rule

#### B1. Forced triads

**Watch for:** three adjectives, three clauses or three examples in paragraph after paragraph.
**Why:** real lists have the length of their content. Use two when there are two.

#### B2. The metronome

**Watch for:** long runs of sentences between 12 and 26 words, all subject-verb-object, with
similar paragraph lengths. `scripts/prose_check.py` reports the share in that band.
**Fix:** let length follow the thought. Don't vary mechanically, and don't insert fragments to hit
a ratio.

#### B3. Repeated openers

**Watch for:** three or more sentences or paragraphs in a row that start the same way ("This…",
"It…", "By…", "With…").

#### B4. Dashes as the universal connector

**Watch for:** em or en dashes joining clauses. House style bans them outright, and they are
also one of the most-cited tells. Use a comma, colon, parentheses or a full stop.

#### B5. Stacked qualifiers *(weak alone)*

**Watch for:** "can potentially help", "may often", "somewhat relatively". Keep hedges that carry
real uncertainty. Cut the ones that are reflexive.

---

### C. Inflation and borrowed authority

#### C1. Model vocabulary *(weak alone)*

**Watch for:** delve, leverage, utilise, robust, seamless, crucial, pivotal, comprehensive,
multifaceted, landscape, realm, tapestry, testament, elevate, unlock, empower, supercharge,
game changer, meticulous, intricate, underscore, showcase, navigate (a challenge), foster, boast.
Also: "In today's fast-paced…", "When it comes to…", "It's worth noting…", "Furthermore",
"Moreover", "At the end of the day", "In conclusion".
**Fix the sentence, not the word.** A common word is fine. It becomes a tell when it is doing
filler, exaggeration or abstraction or when several cluster.

#### C2. Inflated significance

**Watch for:** "plays a pivotal role", "marks a significant milestone", "reflects a broader
shift", "stands as a testament to".
**Why:** an ordinary fact made to sound historic. Say what happened and let the reader judge.

#### C3. Copula avoidance

**Watch for:** "serves as", "stands as", "functions as", "represents", "boasts" where "is" or
"has" is the honest verb.

#### C4. Trailing "-ing" riders

**Watch for:** ", making it…", ", allowing teams to…", ", ensuring…", ", highlighting…" tacked
onto a finished sentence.
**Fix:** if the consequence is a real claim, give it its own sentence with its own evidence. If
it isn't, cut it.

#### C5. Borrowed authority

**Watch for:** "Studies show", "Experts agree", "Research suggests", "Industry leaders say" with
no named source.
**Fix:** name the study, year and finding or remove the claim. This one is also a truth problem.

#### C6. Sales gloss

**Watch for:** "powerful solution", "cutting-edge", "world-class", "best-in-class",
"take your X to the next level", "designed to help you".
**Fix:** replace the adjective with the mechanism or the measured result.

---

### D. Formatting by rule

#### D1. Decorative bold

Bold lead-in labels on every bullet, or bold scattered through prose for emphasis the sentence
already has.

#### D2. A heading for every idea

Headings on two-paragraph sections, title-case headings on a blog that uses sentence case, and
"Key takeaways", "Final thoughts" or "Conclusion" sections that repeat the body.

#### D3. Chat-answer shape in a published piece

Bullets where prose would carry the reasoning better, a summary box that restates the article,
horizontal rules between every section, emoji section markers.

#### D4. Uniform bullets

Every bullet the same length, the same grammatical form and ending with a full stop, whatever
its content.

---

### E. Leftovers from the chat

#### E1. Chatbot residue

"Great question", "Absolutely!", "I hope this helps", "Feel free to reach out", "Let me know if
you'd like another version", "Here's a polished version".

#### E2. Knowledge-limit hedges

"As of my last update", "while specific details are limited", "it's likely that" wrapped around
a fact that should have been checked.

#### E3. The heading echoed in the first sentence

A section titled "Why page speed matters" that opens "Page speed matters because…".

#### E4. Writing about the previous draft

"This updated version…", "As mentioned above", "Now let's revisit…" when nothing above needs
revisiting.

---

### F. Deeper structure (from the narrative research)

These come from StoryScope (Russell et al., 2026; see `research.md`), which found that models are
identifiable from *what they choose to say* even after style edits. They are the hardest tells to
remove, and the ones that matter most in long-form.

- **Over-explaining the theme.** The piece tells the reader what it means, often twice. Trust the
  reader to draw the conclusion from the evidence.
- **Tidy single-track structure.** One clean argument, no digression, no loose end. Real analysis
  often has a side observation that doesn't serve the thesis and stays because it's useful.
- **Low ambiguity.** Every tension resolved, every tradeoff concluded. Where the evidence is
  mixed, say so and stop.
- **Flat escalation.** Every section at the same intensity. Give the strongest material the most
  room and put it where it will land.
- **The neat lesson ending.** A closing paragraph that turns the piece into a moral. End on the
  last useful fact, the decision or the next step.

---

### When not to act

- Inside quotations, titles, proper names, code or a passage discussing the phrase itself.
- On a *weak alone* pattern with no other tells nearby.
- On text written before late 2022, which was not written by a chatbot.
- When the writer's own sample uses the pattern deliberately. Match the sample.

Judging by feel is unreliable, and human writers absorb model habits too. Several tells together
are the signal; one is not.
