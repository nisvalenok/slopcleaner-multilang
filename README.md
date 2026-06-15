# SlopCleaner Multilingual

A skill for removing AI writing patterns ("slop") from prose in **English, German, and Russian** — built around a principle most de-slop tools don't state.

## The problem with the usual approach

There are good English de-slop skills, and a few that cover Asian languages. Most share one blind spot: they treat AI tells as a single list to translate across languages. That breaks, because **a rule in one language is correct typography in another**:

- The **em-dash** is a strong English tell. In German (Gedankenstrich) and Russian (тире) it is normal punctuation that carries real weight — the тире even replaces the verb "to be" ("Москва — столица").
- **Long subordinate clauses** read as heavy in English but are native to German and Russian.
- **Participial phrases, colons, impersonal constructions** — each sits differently in each language.

Strip an English checklist across all three and you flatten the very things that make German and Russian prose read as human.

## What SlopCleaner does differently

Each language is handled on its own terms. A shared **structural core** (false agency, vague declaratives, no standpoint, filler intros and conclusions — things that are tells in any language) plus a **per-language file** that lists two things:

1. the tells specific to that language, and
2. its **exceptions** — constructions that look like tells but are native, and must be left alone.

That exceptions section is the part other skills skip. It's the difference between an editor who knows the language and a find-and-replace script. (Concrete example: stripping every dash from German copy makes it stiffer, not more human, because the Gedankenstrich is normal German typography. That kind of mistake is what the exceptions encode.)

## Honest scope

This is one of many de-slop skills, not a category of one. Where it stands apart:

- **German + Russian** in one multilingual skill — a language pair the existing tools don't cover.
- **Per-language exceptions as a stated design principle**, not an afterthought.
- **Honest evidence labelling.** English tells are backed by corpus-linguistics studies; German and Russian rest mostly on practitioner observation, and the skill says so (`[STUDY]` vs `[PRACTITIONER]` throughout `sources.md`).
- **Not a detector-bypass tool.** Many skills in this space sell "bypass GPTZero / Turnitin." This one doesn't. AI-text detectors score below ~40% on non-English prose; these lists are for a human editor's judgment, not for certifying — or hiding — a text's origin.

If you only write English, a focused English-only skill may serve you better. SlopCleaner earns its keep when you work across these languages and need each one respected.

## Structure

```
slopcleaner-multilang/
├── SKILL.md              # router: detect language → core → language file
├── README.md
├── LICENSE
└── references/
    ├── core.md           # language-invariant structural tells
    ├── en.md             # English (corpus-study backed)
    ├── de.md             # German + exceptions
    ├── ru.md             # Russian + exceptions
    └── sources.md        # citations + per-item confidence
```

## How it works

1. Detect the language of the text being edited (not the language of the conversation).
2. Apply the structural core.
3. Apply the matching language file, obeying its EXCEPTIONS section.
4. Read aloud and judge by ear — the checklist serves the reading, never the reverse.

## How to add a language

The architecture is additive: a new language is a new file plus one router line. It does not touch existing languages. To add one well:

1. **Research first, don't translate.** Do not machine-translate the English list. Find documented observations of AI tells *in that language* (linguistics papers, editor write-ups, detector studies). Cite them.
2. **Create `references/<lang>.md`** with two sections:
   - **Tells** specific to the language (phrases, punctuation habits, structural patterns).
   - **EXCEPTIONS** — the constructions that look like tells but are native norm. This section is mandatory and is the most important part. Without it, the file will damage good prose.
3. **Add one line to `SKILL.md`** routing that language to its file.
4. **Append sources to `references/sources.md`**, each marked `[STUDY]`, `[COMPENDIUM]`, or `[PRACTITIONER]` by strength of evidence.
5. **Don't carry rules across languages.** If a rule (e.g. "remove em-dashes") is English-only, it stays in `en.md`. The core file holds only what is genuinely language-invariant.

A language with little documented research can still get an EXCEPTIONS file and lean on the structural core; that's better than a translated checklist that flattens the language.

## Installation

Drop the `slopcleaner-multilang/` folder into your skills directory (a Claude skills folder, or wherever your agent loads skills from). Reference files load on demand.

## Contributing

Issues and pull requests welcome — especially new-language files that follow the "research first, don't translate" rule above, and better-sourced tells for German and Russian (the two thinnest evidence bases). Keep each language's EXCEPTIONS section intact; that is the core of the design.

## Author and license

By **Denis Kovalenko** ([@nisvalenok](https://github.com/nisvalenok)). Released under the **MIT License** (see `LICENSE`).

The idea of cleaning AI patterns from prose is common to many tools and predates any single one; this implementation — the multilingual router with per-language exceptions — and its wording are original, built from the primary sources cited in `references/sources.md` (Kobak et al., *Science Advances* 2025; Juzek & Ward, ICCL 2025; Wikipedia "Signs of AI Writing"; GPTZero; and practitioner sources for each language).
