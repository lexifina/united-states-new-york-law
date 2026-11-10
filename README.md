# United States (New York): law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of New York, United States.

The law of New York as a git history: one file per provision, with `git blame` and `git log` working line by line. It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

**Current coverage**

| Folder | What | Sections | Versions (in force from) |
| --- | --- | ---: | --- |
| `constitution/` | Constitution of the State of New York: preamble and 20 articles | 206 | 2022-01-01, 2025-01-01, 2026-01-01 |

`constitution/art-01-sec-011.md` is N.Y. Const. art. I, § 11; a lettered section such as art. VI, § 36-a is `art-06-sec-036-a.md`; the preamble is `preamble.md`. Each file starts with the section number and its bracketed heading, then one paragraph per line, as the edition prints them.

**Source.** The New York State Constitution as published by the Department of State, Division of Administrative Rules ([dos.ny.gov](https://dos.ny.gov/new-york-state-constitution-0)): the editions "as amended and in force" January 1, 2025 and January 1, 2026, and the January 1, 2022 edition as hosted by the State Board of Elections ([elections.ny.gov](https://elections.ny.gov)). The edition says its bracketed section headings, annotations and footnotes are not part of the official text; the headings and amendment notes are kept, footnotes are not.

The Consolidated Laws are not here yet.

## Dates

Each edition is one version, dated by the in-force date on its cover (N.Y. Const. art. XIX, § 1: an amendment approved by the people takes effect on the first day of January after its approval). Editions before 2022 are not included yet, so the first version is credited to the publisher as the oldest version available.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist. No change between editions is credited to an amendment yet: the editions' notes name the votes, but the changes are committed as unexplained, by the publisher (`publisher@dos.ny.gov.invalid`). The committer is always Lexifina.

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; the results are in `REPRODUCE.md`. The words of each edition were compared with an independent text extraction of the same PDF.
