# Research Base — SlopCleaner Multilingual (EN · DE · RU)

Stand: 2026-06-15. Confidence per item: **[STUDY]** peer-reviewed / large corpus · **[COMPENDIUM]** maintained public reference (Wikipedia) · **[PRACTITIONER]** editor/blog observation, single or few sources.

Detector caveat (all languages): AI-text detectors score low, especially non-English (Singapore/Vietnam 2024 study: ~39.5% avg, down to 22% with typos). These lists are for a human editor, not automated proof. One pattern proves nothing; clustering is the signal.

---

## ENGLISH

### Lexical [STUDY — strongest evidence base]
- **Kobak et al., Science Advances 2025** — 15M+ PubMed abstracts 2010–2024. "Excess vocabulary" method (modeled on excess-mortality). At least 13.5% of 2024 abstracts LLM-processed, up to 40% in some journals. Measured frequency ratios vs pre-LLM baseline: **delves r=28.0, underscores r=13.8, showcasing r=10.7**. Full 900-word annotated list public: github.com/berenslab/llm-excess-vocab. Strongest markers (style not content): delve(s/ing), underscore(s/ing), showcase(s/ing), pivotal, intricate, meticulous(ly), realm, align(s), underpin(s), garnered, bolstering, notably.
- **Juzek & Ward, "Why Does ChatGPT Delve So Much?", ICCL 2025** (arxiv 2412.11385) — 21 focal words: delve, intricate, commendable, meticulous, surpass, elevate, foster, tapestry, realm, navigate, landscape, pivotal, resonate, testament, underscore, showcasing, compelling, paramount, crucial, unwavering, alignment. Argues RLHF as source of overrepresentation.
- "Tapestry" prestige-nouns: tapestry, landscape, realm, mosaic, ecosystem, symphony, labyrinth, beacon, cornerstone, bedrock, testament, kaleidoscope, odyssey.
- Corporate-inflation adjectives: robust, seamless, vibrant, dynamic, comprehensive, multifaceted, nuanced, holistic, cutting-edge, state-of-the-art, transformative, groundbreaking, unparalleled, profound, innovative, ever-evolving.
- Inflated verbs: leverage, utilize, harness, streamline, facilitate, optimize, empower, illuminate, bolster, foster, elevate, unlock.

### Signposting / filler phrases [PRACTITIONER, widely confirmed]
"It's important/worth noting that", "That being said", "In today's fast-paced world", "In an ever-evolving landscape", "Navigating the complexities of", "At its core", "At the heart of", "When it comes to", "In the realm of", "Play a vital/pivotal role in", "Stands as a testament to", "Delve into the intricacies of", "Let's unpack/break it down".

### Closing rituals [PRACTITIONER + OpenAI dev forum confirms "preachy conclusions"]
"In conclusion", "In summary", "Overall", "Ultimately", "As we navigate X…", "The journey doesn't end here".

### Syntactic / structural [COMPENDIUM — Wikipedia Signs of AI Writing]
- **Negative parallelism / negated contrast**: "It's not X, it's Y", "no X, no Y, just Z", "Not only… but…". Wikipedia gives it its own section. Multiple independent sources call it the single most diagnostic move. Scales fractally, stacks in threes.
- **Rule of three / tricolon**: three parallel items, equal length. NOTE from Wikipedia talk archive: R3 is legitimately used by human writers (marketing, speeches: "education, education, education"); the AI-specific aspect is using it to make *superficial analysis appear comprehensive*. So flag clustering + superficiality, don't condemn R3 itself.
- **Participial tail**: floating participle restating the main clause ("…, marking a pivotal moment in…", "…, underscoring its importance for…").
- **Bad-subject problem** (Shreya Shankar): grammatical subject ≠ actual topic; orphaned demonstratives (this/that/these) with no referent.
- **Low burstiness / low perplexity** (GPTZero): metronomic 14–22-word sentences, little variance; predictable next token. Human prose bursts (short then long).
- **Hypotactic smoothness**: no fragments, no comma splices, everything resolves. Neil Clarke (Clarkesworld): AI submissions "boring, flat, no subtext or layers".

### Rhetorical / tonal [COMPENDIUM + PRACTITIONER]
- **Five-paragraph-essay shape** scaled to any length (intro + 3 body + recap), section summaries closing every subsection.
- **Puffed-up significance** (Wikipedia): mean-ward regression — a minor thing becomes "pivotal moment in the evolution of…". Subject becomes simultaneously less specific and more exaggerated.
- **Promotional register** for non-promotional subjects: "rich cultural heritage", "breathtaking landscapes", "vibrant community".
- **Both-sides hedge / false concession**: "While critics argue X, supporters maintain Y. The truth lies somewhere in between."
- **Aphoristic closure**: paragraph ends on pseudo-profound kicker shaped like a pull-quote.
- **Strategic vagueness** (Vauhini Vara): "polite, predictable, inoffensive, upbeat"; no concrete particulars, no last names, no specific dates.
- **Sycophancy** (OpenAI conceded GPT-4o sycophancy, April 2025): "Great question!", "You're absolutely right".
- **Missing concrete particular**: no Tuesday, no laundromat, no brand names. Abstraction over specificity.

### Punctuation [STUDY-adjacent + contested]
- **Em-dash**: most famous, most contested. Reddit-API analysis (Artificial Ignorance): em-dash usage ~tripled in tech subreddits 2023–2024. Model-dependent (Plagiarism Today six-model test: ChatGPT/Copilot/Deepseek heavy; Claude light; Gemini/Meta none). Fine-grain: not presence but **distribution** — humans use em-dash for sharp asides/interruptions; LLMs for additive qualifying segments (breath-cycle clauses). Model vendors have reportedly tried to suppress it in newer versions (secondary report via Wikipedia; version-specific, treat as soft).
- Oxford commas + zero contractions + near-perfect grammar = machine cleanliness.
- Curly/smart quotes in contexts that normally use straight (Reddit, code, plain email).
- Title-case headers, excessive boldface, emojis in headers/lists (Wikipedia).

### EN EXCEPTIONS (not a tell)
- Em-dash itself is "the most human punctuation mark" (Brian Phillips, The Ringer) — flag distribution/clustering, not presence.
- Contractions, deliberate fragments in voice, "you" address — all natural; absence reads stiffer.
- R3 used sparingly and substantively — legitimate (per Wikipedia's own editors).

---

## GERMAN [PRACTITIONER — t3n explicitly: English phrase-evidence exists, German largely lacks it]

### Floskeln / openers
"In der heutigen Zeit / digitalen Welt ist es wichtiger denn je", "In einer Welt, in der", "Immer mehr Menschen fragen sich", "Es ist allgemein bekannt, dass", "Es ist wichtig zu beachten/betonen, dass", "Viele Experten sind sich einig, dass", "Ein guter Weg, dies zu erreichen, ist", "Dies könnte hilfreich sein, um".

### Fazit-Floskeln
"Abschließend/Zusammenfassend lässt sich sagen, dass", "Denken Sie daran: Jeder kleine Schritt zählt!".

### Inflationäre Einzelwörter (ContentConsultants)
präzise, sauber, eintauchen, umfassend, ganzheitlich, nahtlos, maßgeschneidert, zukunftsorientiert, skalierbar, "aufs nächste Level heben".

### "Die 3 Adjektive" — sharpest German tell (ContentConsultants)
Gedankenstrich + three comma-separated adjectives at sentence end = strong signal of uneditiert KI per ContentConsultants (single source, not proof). "– sicher, garantiert und zweifellos."

### Antithese
"Es ist nicht dies. Es ist das." — bedeutungsschwanger, Punkt statt Komma. (= German form of EN negative parallelism.)

### Passiv-Floskeln (Lightweb)
"es wird empfohlen, dass", "es ist anzumerken, dass", "es lässt sich festhalten, dass".

### Struktur
Absätze ohne Übergänge; striktes Einleitung/Hauptteil/Fazit; Listicle-Fetisch; lange schematische Überschriften.

### Gedankenstrich — reduce, NOT eliminate (t3n, ContentConsultants)
ChatGPT overuses it, BUT it is correct normal German typography. Tell only when (a) clustered AND/OR (b) followed by 3 adjectives. Rule: reduce clustering to 1–2/paragraph; keep dashes carrying a real pause. Blanket removal of all dashes is an error — it flattens normal German prose.

### GERMAN EXCEPTIONS (not a tell)
- Gedankenstrich itself — normal typography.
- Schachtelsatz / multiple subordinate clauses — legitimate, often elegant; not "too long" or passive-error.
- Komposita (long compounds) — language norm.
- Konjunktiv, Partizipialkonstruktionen — normal.
- Direct address (Sie/du) + rhetorical questions in narrative/ad registers — wanted.

---

## RUSSIAN [PRACTITIONER — ADPASS most detailed; base thinner than EN]

### Пунктуация — most specific RU tells (ADPASS), absent from English guides
- Лишняя запятая "для интонации" (машина ставит паузу, которой не слышит).
- "такие как" вместо двоеточия перед однородными после обобщающего слова. Человек: "инструменты: X, Y, Z". ИИ: "инструменты, такие как X, Y, Z".
- Двоеточие после первого слова каждого пункта списка + дубль смысла с заглавной (схема прямой речи А: "П").
- Запятая после оборотов с "благодаря".
- Обособление "однако" в начале предложения.
- Отсутствие скобок и многоточий в первой итерации ("не размышляет, а знает").

### Лексика — канцелярит (ADPASS, Эльдоблог, Unisender)
- Отглагольные существительные: "Уточните свои маркетинговые усилия" вместо "уточните, кого хотите привлечь".
- "включает в себя", "является", "осуществляется", "представляет собой" — наполнители.
- "Данный" вместо "этот"; "в целях", "в рамках", "касаемо".
- Страдательный залог где естественнее активный.

### Структура (несколько источников)
- Введение/заключение как "вода" (школьное увеличение объёма).
- Повторы без отсылки к себе (ИИ не пишет "как уже было сказано", "вернусь к…").
- Нет связок между абзацами (связь внутри предложений есть, между — нет).
- Нет сторителлинга/метафор/ситуативных шуток по умолчанию.

### Русские эквиваленты throat-clearing (англ. переводить буквально нельзя)
"Стоит отметить, что", "Важно понимать, что", "Давайте разберёмся", "В современном мире", "Не секрет, что", "Как известно", "Подведём итог".

### RUSSIAN EXCEPTIONS (это НЕ tell)
- Тире — несёт больше нагрузки, чем в немецком (заменяет связку и "это": "Москва — столица"). Английское "no em dashes" к русскому НЕ применять.
- Деепричастные/причастные обороты — норма синтаксиса, не passive-tell. (Скопление — да, перебор; единичный — норма.)
- Безличные конструкции ("хочется", "стоит") — норма.
- Длинные сложноподчинённые — норма.
- Двоеточие как таковое — нормальный знак; tell в схеме "двоеточие+первое слово пункта+дубль", не в двоеточии вообще.

---

## INVARIANT CORE (all languages — structural, word-independent)
1. False agency — inanimate doing human action ("the decision emerges", "die Entscheidung entsteht", "решение возникает"). Name the actor. (Caveat: deliberate literary personification ≠ this tell.)
2. Vague declaratives — importance without specifics ("The implications are significant" / "Es ist von Bedeutung" / "Это имеет значение").
3. Unearned triads — three-by-reflex (but R3 used substantively is legit per Wikipedia editors).
4. Manufactured profundity — fragments for weight.
5. No own perspective — summary without standpoint/experience. Deepest tell.
6. Intro/conclusion as filler.
7. Glossy impersonality — too smooth, no friction, no concrete particular.

---

## SOURCES

EN (studies):
- Kobak et al., "Delving into LLM-assisted writing in biomedical publications", Science Advances 2025 / arxiv 2406.07016. GitHub: berenslab/llm-excess-vocab
- Juzek & Ward, "Why Does ChatGPT Delve So Much?", ICCL 2025 / arxiv 2412.11385
- Desaire et al., "Almost Nobody Is Using ChatGPT to Write Academic Science Papers (Yet)", 2024 (counterpoint: 1–3% in MDPI intros)
EN (compendium/practitioner):
- Wikipedia: Signs of AI Writing (en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) + talk archives
- Field guide, M. Vollmer / Claude (matthewvollmer.substack.com) — aggregator with citations
- GPTZero (perplexity/burstiness); Shreya Shankar (sh-reya.com/blog/ai-writing)
- Vauhini Vara (Searches); Neil Clarke (Clarkesworld/Post Alley 2024)

DE:
- t3n 2026 (ki-texte-erkennen-gedankenstrich-floskeln-struktur) — key: EN has evidence, DE lacks
- ContentConsultants / Udo Raaf 2026 — phrase list, 3 Adjektive, Antithese, Gedankenstrich
- eology; ki-im-marketing.at; Lightweb Media; Golem Karrierewelt

RU:
- ADPASS / LZ.Media 2023 — detailed punctuation analysis
- Unisender 2026; Хабр/Altcraft; Эльдоблог; Грамота.ру

Detectors: Singapore/Vietnam 2024 (~39.5%, 22% w/ typos). Low on non-English → human-editor lists, not auto-detection.
