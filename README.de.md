# SlopCleaner Multilingual

[English](README.md) · **Deutsch** · [Русский](README.ru.md)

Ein Skill, der KI-Schreibmuster („Slop") aus Prosa in **Englisch, Deutsch und Russisch** entfernt — gebaut um ein Prinzip, das die meisten De-Slop-Werkzeuge nicht aussprechen.

## Das Problem am ueblichen Ansatz

Es gibt brauchbare englische De-Slop-Skills und ein paar fuer asiatische Sprachen. Fast alle teilen einen blinden Fleck: Sie behandeln KI-Marker als eine Liste, die man von Sprache zu Sprache uebersetzt. Das geht schief, denn **was in einer Sprache ein Marker ist, ist in der anderen korrekte Typografie**:

- Der **Gedankenstrich** ist im Englischen ein starkes Signal (em-dash). Im Deutschen und im Russischen (тире) ist er normale Interpunktion mit echtem Gewicht — das russische тире ersetzt sogar das Verb „sein" („Москва — столица").
- **Lange Schachtelsaetze** wirken im Englischen schwer, sind im Deutschen und Russischen aber Norm.
- **Partizipialkonstruktionen, Doppelpunkte, unpersoenliche Wendungen** — jedes liegt in jeder Sprache anders.

Zieht man eine englische Checkliste ueber alle drei, glaettet man genau das weg, was deutsche und russische Prosa menschlich klingen laesst.

## Was SlopCleaner anders macht

Jede Sprache wird auf ihren eigenen Begriffen behandelt. Ein gemeinsamer **struktureller Kern** (falsche Handlungstraeger, leere Behauptungen, fehlender Standpunkt, Fueller-Einleitungen und -Fazits — Marker in jeder Sprache) plus eine **Datei pro Sprache**, die zwei Dinge auflistet:

1. die Marker, die fuer diese Sprache typisch sind, und
2. ihre **Ausnahmen** — Konstruktionen, die wie Marker aussehen, aber muttersprachliche Norm sind und unangetastet bleiben.

Dieser Ausnahmen-Teil ist das, was andere Skills auslassen. Er ist der Unterschied zwischen einem Lektor, der die Sprache kennt, und einem Suchen-und-Ersetzen-Skript. (Konkret: Streicht man jeden Gedankenstrich aus deutschem Text, wird er steifer statt menschlicher, weil der Gedankenstrich normale deutsche Typografie ist. Genau solche Fehler kodieren die Ausnahmen.)

### ß oder ss

Deutsch hat drei Standardvarietaeten. DE-DE und DE-AT setzen das ß nach langem Vokal (Straße, groß); DE-CH und Liechtenstein kennen kein ß und schreiben immer ss (Strasse, gross). Der Skill behandelt das als Norm, nicht als Marker.

Er **erkennt die Varietaet automatisch am Text**: taucht irgendwo ein ß auf, ist es DE-DE/AT; fehlt das ß genau dort, wo Standarddeutsch eines setzte (Strasse statt Straße, gross statt groß), ist es Schweizer Hochdeutsch. Laesst sich beides nicht entscheiden, fragt der Skill nach, statt zu raten. Die gewaehlte Varietaet haelt er dann durch — ein ß zu ss zu wandeln ist sicher, der umgekehrte Weg nicht (dass, muss bleiben ueberall ss). Dieses Detail zeigt sofort, ob jemand die Norm kennt.

## Ehrlicher Geltungsbereich

Dies ist einer von vielen De-Slop-Skills, keine Kategorie fuer sich. Wo er sich abhebt:

- **Deutsch und Russisch** in einem mehrsprachigen Skill — ein Sprachpaar, das die bestehenden Werkzeuge nicht abdecken.
- **Ausnahmen pro Sprache als erklaertes Designprinzip**, nicht als Nachgedanke.
- **Ehrliche Quellenkennzeichnung.** Englische Marker stuetzen sich auf korpuslinguistische Studien; Deutsch und Russisch ruhen groesstenteils auf Praktiker-Beobachtung — und der Skill sagt das (`[STUDY]` vs. `[PRACTITIONER]` durchgaengig in `sources.md`).
- **Kein Detektor-Umgehungs-Werkzeug.** Viele Skills in diesem Feld verkaufen „GPTZero / Turnitin umgehen". Dieser nicht. KI-Detektoren liegen bei nicht-englischer Prosa unter ~40 %; diese Listen dienen dem Urteil eines menschlichen Lektors, nicht dem Zertifizieren — oder Verbergen — der Herkunft eines Textes.

Wer nur Englisch schreibt, faehrt mit einem reinen Englisch-Skill vielleicht besser. SlopCleaner verdient sich seinen Platz, wenn man ueber diese Sprachen hinweg arbeitet und jede einzeln respektiert wissen will.

## Aufbau

```
slopcleaner-multilang/
├── SKILL.md              # Router: Sprache erkennen → Kern → Sprachdatei
├── README.md
├── LICENSE
└── references/
    ├── core.md           # sprachunabhaengige strukturelle Marker
    ├── en.md             # Englisch (korpusgestuetzt)
    ├── de.md             # Deutsch + Ausnahmen
    ├── ru.md             # Russisch + Ausnahmen
    └── sources.md        # Quellen + Konfidenz pro Punkt
```

## Wie es funktioniert

1. Die Sprache des bearbeiteten Textes erkennen (nicht die Sprache des Gespraechs).
2. Den strukturellen Kern anwenden.
3. Die passende Sprachdatei anwenden und ihren AUSNAHMEN-Teil befolgen.
4. Laut lesen und nach Gehoer urteilen — die Checkliste dient dem Lesen, nie umgekehrt.

## Eine Sprache hinzufuegen

Die Architektur ist additiv: Eine neue Sprache ist eine neue Datei plus eine Router-Zeile. Bestehende Sprachen bleiben unberuehrt. So macht man es richtig:

1. **Zuerst recherchieren, nicht uebersetzen.** Die englische Liste nicht maschinell uebertragen. Dokumentierte Beobachtungen von KI-Markern *in dieser Sprache* suchen (linguistische Arbeiten, Lektorats-Berichte, Detektor-Studien). Belegen.
2. **`references/<lang>.md` anlegen** mit zwei Abschnitten:
   - **Marker** dieser Sprache (Phrasen, Interpunktions-Gewohnheiten, strukturelle Muster).
   - **AUSNAHMEN** — die Konstruktionen, die wie Marker aussehen, aber muttersprachliche Norm sind. Dieser Abschnitt ist Pflicht und der wichtigste Teil. Ohne ihn beschaedigt die Datei gute Prosa.
3. **Eine Zeile in `SKILL.md`** ergaenzen, die die Sprache auf ihre Datei leitet.
4. **Quellen in `references/sources.md` anhaengen**, jede mit `[STUDY]`, `[COMPENDIUM]` oder `[PRACTITIONER]` nach Belegstaerke.
5. **Keine Regeln zwischen Sprachen tragen.** Ist eine Regel (z. B. „Gedankenstriche entfernen") nur englisch, bleibt sie in `en.md`. Der Kern enthaelt nur, was wirklich sprachunabhaengig ist.

Eine Sprache mit wenig Forschung kann trotzdem eine AUSNAHMEN-Datei bekommen und sich auf den Kern stuetzen; das ist besser als eine uebersetzte Checkliste, die die Sprache plattmacht.

## Installation

Den Ordner `slopcleaner-multilang/` in das Skills-Verzeichnis legen (ein Claude-Skills-Ordner oder wo immer der Agent Skills laedt). Die Referenzdateien laden bei Bedarf.

## Mitwirken

Issues und Pull Requests sind willkommen — besonders neue Sprachdateien nach der Regel „zuerst recherchieren, nicht uebersetzen" und besser belegte Marker fuer Deutsch und Russisch (die zwei duennsten Belegbasen). Den AUSNAHMEN-Teil jeder Sprache intakt lassen; er ist der Kern des Entwurfs.

## Autor und Lizenz

Von **Denis Kovalenko** ([@nisvalenok](https://github.com/nisvalenok)). Veroeffentlicht unter der **MIT-Lizenz** (siehe `LICENSE`).

Die Idee, KI-Muster aus Prosa zu entfernen, ist vielen Werkzeugen gemein und aelter als jedes einzelne; diese Umsetzung — der mehrsprachige Router mit Ausnahmen pro Sprache — und ihr Wortlaut sind original, gebaut aus den in `references/sources.md` zitierten Primaerquellen (Kobak et al., *Science Advances* 2025; Juzek & Ward, ICCL 2025; Wikipedia „Signs of AI Writing"; GPTZero; sowie Praktiker-Quellen je Sprache).
