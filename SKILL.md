---
name: slopcleaner-multilang
description: Strip AI writing patterns ("slop") from prose in English, German, or Russian. Use when the user explicitly asks to remove AI tells, humanize text, make a draft sound less generic or more human, or runs an editing pass over prose ("make this sound human", "remove AI tells", "clean up this draft", "humanize", "проверь на нейросетевость", "klingt das nach KI?"). Also applies when reviewing a draft the user has handed over for polishing. Holds back when another skill owns the writing task (brand voice, copy generation) unless the user specifically asks for de-slop. Works per language — each has its own tells AND its own list of constructions that are normal and must NOT be touched — so never carry a rule from one language into another.
metadata:
  authors: built from primary research (linguistics papers, public compendia, editor observations); see references/sources.md
  languages: en, de, ru
---

# SlopCleaner Multilingual

Remove the predictable patterns of LLM-generated prose — "slop" — across **English, German, and Russian**. The point is not a clean checklist pass; it is prose a human reads to the end without once thinking "a machine wrote this."

## The one principle that makes this multilingual

A tell in one language is correct typography in another. The em-dash is a strong English signal; the German Gedankenstrich and the Russian тире are normal punctuation that carry real weight. Strip every dash and you damage German and Russian while only helping English. The same asymmetry holds for long subordinate clauses (normal in German and Russian, heavier in English), participial phrases, and colons.

So this skill never translates one language's rule list into another. It applies a shared structural core, then the specific language's list — including that language's **exceptions**, the things that look like tells but are native and must be left alone.

There is also an evidence gap worth knowing: English AI-tells are documented in peer-reviewed corpus studies; German and Russian rest mostly on practitioner observation, with thinner backing. Treat the English lists as firmer and the others as strong leads, not law.

## Workflow

1. **Detect the language of the text** under edit — not the language of the conversation. For mixed-language text, handle each passage in its own language.
2. **Apply `references/core.md`** — structural tells that hold in every language (false agency, vague declaratives, no standpoint, filler intros/conclusions, glossy impersonality).
3. **Load and apply the matching language file**: `references/en.md`, `references/de.md`, or `references/ru.md`.
4. **Obey the EXCEPTIONS section** of that file. When a core rule collides with a language exception, the exception wins for that language. A construction listed as native is not "fixed" into something flatter.
5. **Read the result aloud and judge by ear.** The checklist serves the reading, not the reverse. If a fix makes a sentence stumble, revert it. A correct-but-lifeless sentence is a failure, not a pass.

## What this is not

This is an editor's instrument, not a tribunal. No single pattern proves a text was machine-written — humans write tricolons, say "delve", use em-dashes. The signal is **density and clustering**, not any one item. AI-text detectors score below ~40% on non-English prose (lower with typos), so these lists guide a human's judgment; they do not certify origin. Never tell a user a text "is AI" on the strength of these patterns.

## Scoring (optional)

Rate 1–10 per dimension; below 35/50 means revise.

| Dimension | Question |
|-----------|----------|
| Directness | States things, or announces them? |
| Rhythm | Varied sentence lengths, or metronomic? |
| Trust | Respects the reader's intelligence? |
| Authenticity | Sounds like a human writing in THIS language? |
| Density | Anything left to cut? |

## Provenance

Built from primary sources: corpus-linguistics papers (Kobak et al. 2025; Juzek & Ward 2025), the public Wikipedia "Signs of AI Writing" compendium, detector research (GPTZero), and editor/practitioner observations for all three languages. Full citations and confidence levels in `references/sources.md`. The idea of cleaning AI patterns from prose is common to many tools; this implementation — the multilingual router with per-language exceptions — and its wording are original.
