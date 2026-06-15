# English Tells

The best-documented language. Lexical claims here trace to corpus studies (Kobak et al., Science Advances 2025; Juzek & Ward, ICCL 2025); structural claims to the Wikipedia "Signs of AI Writing" compendium and detector research. Citations in `sources.md`. Structural core is in `core.md`.

## Overused vocabulary [corpus-measured]

Kobak et al. measured frequency spikes in 15M+ scientific abstracts after late 2022. Strongest single markers (ratio over pre-LLM baseline): **delve(s)** ~28×, **underscores** ~14×, **showcasing** ~11×. These are style words, not content words.

- **Synthetic-erudition verbs:** delve, underscore, showcase, foster, elevate, surpass, leverage, harness, streamline, facilitate, bolster, illuminate, navigate (figurative), unlock.
- **Prestige nouns** (borrowed grandeur for flat subjects): tapestry, landscape, realm, mosaic, ecosystem, symphony, beacon, cornerstone, bedrock, testament, odyssey.
- **Inflation adjectives:** robust, seamless, pivotal, vibrant, dynamic, comprehensive, multifaceted, nuanced, holistic, cutting-edge, transformative, groundbreaking, profound, ever-evolving.

None of these is forbidden on its own — humans use every one. Flag them when they cluster or when the subject doesn't earn the grandeur. Fix: the plain word. "Use" not "utilize"; "shows" not "underscores".

## Signposting and filler phrases

"It's important/worth noting that", "That being said", "In today's fast-paced world", "In an ever-evolving landscape", "At its core", "At the heart of", "When it comes to", "In the realm of", "plays a vital/pivotal role in", "stands as a testament to", "let's unpack / break it down". Cut and state the point.

## Closing rituals

"In conclusion", "In summary", "Overall", "Ultimately", "The journey doesn't end here". (OpenAI's own developers have complained their models won't stop producing these.) End on something real instead.

## Negative parallelism — the most diagnostic move

"It's not X, it's Y." / "No X, no Y, just Z." / "Not only X but Y." Wikipedia gives this its own section; multiple independent editors call it the strongest single tell. It stacks fractally — whole posts built from it, often three deep. Fix: state Y directly, drop the negation. "This is a revolution," not "This isn't a product, it's a revolution."

## Participial tail

A floating participial phrase that merely restates the main clause: "…, marking a pivotal moment in the evolution of…", "…, underscoring its importance for future research." Fix: delete the tail or make it carry new information.

## The bad-subject problem

The grammatical subject isn't the actual topic; orphaned demonstratives ("this", "that", "these") point at nothing specific. Fix: make the subject the thing the sentence is about.

## Puffed-up significance

Mean-ward regression: a small thing inflated to "a pivotal moment in the evolution of…". The subject becomes simultaneously vaguer and louder. Fix: state the actual, modest fact.

## Other tonal tells

Promotional register for non-promotional subjects ("rich cultural heritage", "vibrant community"); both-sides hedge ("the truth lies somewhere in between"); aphoristic closure (paragraph ending on a pull-quote-shaped kicker); sycophancy ("Great question!", "You're absolutely right"); cheap warmth ("Hope this helps!", "Let's dive in!").

## Rhythm — English-specific

Low burstiness is a measured signal (GPTZero): LLM sentences cluster at 14–22 words with little variance. Human prose bursts — a short declarative after a long clausal one. English also tolerates fragments and the occasional comma splice; LLM prose resolves every sentence cleanly, and that flawlessness reads as machine. Fix: vary length deliberately; let one sentence be four words.

## Punctuation — English-specific

**Em-dash:** a real English signal when clustered — one Reddit-API analysis found em-dash use roughly tripled in tech forums 2023–2024 (Artificial Ignorance) — but contested and model-dependent (a six-model comparison at Plagiarism Today found ChatGPT/Copilot heavy, Claude light, Gemini/Meta none). The fine-grained tell is **distribution, not presence**: humans use the em-dash for a sharp aside or interruption; LLMs use it to bolt on additive, explanatory clauses that read like breath cycles. Fix: thin the additive ones to commas or periods; keep the sharp asides.

Also: Oxford comma + zero contractions + immaculate grammar together signal machine cleanliness. Curly quotes in plain-text contexts (Reddit, code, email). Title-case headers and emoji in headings.

---

## EXCEPTIONS — not a tell in English

- **The em-dash itself.** "The most human punctuation mark there is" (Brian Phillips, The Ringer). Flag clustering and the additive-clause pattern, never mere presence.
- **Contractions and deliberate fragments** in a real voice — natural; their absence reads stiffer.
- **"You" address** — wanted; it puts the reader in the room.
- **Rule of three used sparingly and substantively** — legitimate, per Wikipedia's own editors. Only reflexive or padding triads are the tell.
