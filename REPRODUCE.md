# How this repository was made (United States (New York))

This file is written by the build on 2026-11-10, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| New York Department of State, Division of Administrative Rules: New York State Constitution (editions in force January 1, 2025 and January 1, 2026) | <https://dos.ny.gov/new-york-state-constitution-0> | 2026-11-10 | No copyright in the text of the law (Georgia v. Public.Resource.Org, Inc., 590 U.S. 255 (2020)). |
| New York State Board of Elections: copy of the Department of State edition in force January 1, 2022 | <https://elections.ny.gov/system/files/documents/2023/10/constitution-january-1-2022.pdf> | 2026-11-10 | No copyright in the text of the law (Georgia v. Public.Resource.Org, Inc., 590 U.S. 255 (2020)). |
| New York State Senate: Laws of New York (nysenate.gov/legislation/laws) | <https://www.nysenate.gov/legislation/laws/CONSOLIDATED> | 2026-11-10 | No copyright in the text of the law. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitution` | Constitution of the State of New York | 3 | 2022-01-01 to 2026-01-01 |

The build made 3 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 2 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-10.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 0 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (America/New_York) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each version is dated by the in-force date the official edition states on its cover ("As Amended and in Force January 1, 2026"); N.Y. Const. art. XIX, § 1: an amendment approved by the people takes effect on the first day of January next after its approval. https://dos.ny.gov/system/files/documents/2025/12/constitution-january-1-2026.pdf

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `d5b1d336e6e38fee4ae504604e31c22b10ee8fd6a7ee68e424271c5278060b8f` (1162622 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `3024ff164c261807dfc4d5b7b1b4a2cde4357da1`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

On GitHub this history follows the repository's first commit ("sources, before any law"), so each commit there has that parent and a committer time of its own; `tools/build.py` rebuilds the same files in the same commits, with the hashes quoted above.

## Decisions made by hand

- The Constitution comes from the Department of State's PDF editions; each edition is one version, dated by the in-force date on its cover (2022-01-01, 2025-01-01, 2026-01-01). Editions before 2022 are not included yet.
- No change between editions is credited to an amendment: the editions say which vote amended a section, but not every change between two editions maps to one vote without judgment, so changes are committed as unexplained, by the publisher.
- One file per section of each article (art-NN-sec-NNN), plus the preamble; a repealed section is kept as the bracketed note the edition prints in its place.
- Text is read column by column from the PDF; footnotes and footnote markers are dropped; a word broken at a line end is joined, keeping the hyphen only when the hyphenated form appears elsewhere in the same edition or both parts are number words; curly quotes made straight; no other change to the words.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text, dates and structure come from the source PDFs by rule.
