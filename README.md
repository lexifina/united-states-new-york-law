# United States (New York): law history in git

Part of [lexifina/global-law](https://github.com/lexifina/global-law), one git history for every country's law: this is the law of New York, United States.

The law of New York as a git history: one file per provision, with `git blame` and `git log` working line by line. It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

**Current coverage**

| Folder | What | Sections | Versions (in force from) | Source |
| --- | --- | ---: | --- | --- |
| `constitution/` | Constitution of the State of New York: preamble and 20 articles | 206 | 2022-01-01, 2025-01-01, 2026-01-01 | Department of State editions |
| `business-corporation-law/` | New York Business Corporation Law | 109 | 2024-07-26 | Internet Archive copy of nysenate.gov, 2025-04-05 to 2026-10-27 |
| `limited-liability-company-law/` | New York Limited Liability Company Law | 124 | 2024-06-14 | Internet Archive copy of nysenate.gov, 2025-02-20 to 2026-10-26 |

`constitution/art-01-sec-011.md` is N.Y. Const. art. I, § 11; a lettered section such as art. VI, § 36-a is `art-06-sec-036-a.md`; the preamble is `preamble.md`. In a Consolidated Law, `limited-liability-company-law/sec-1101.md` is LLC Law § 1101 (numbers zero-padded to four digits, so `sec-0010-0000.md` is § 10.00 and `sec-0001-a.md` is § 1-a). Each file starts with the section heading line as printed, then one paragraph per line.

## Sources

**Constitution.** The New York State Constitution as published by the Department of State, Division of Administrative Rules ([dos.ny.gov](https://dos.ny.gov/new-york-state-constitution-0)): the editions "as amended and in force" January 1, 2025 and January 1, 2026, and the January 1, 2022 edition as hosted by the State Board of Elections ([elections.ny.gov](https://elections.ny.gov)). The edition says its bracketed section headings, annotations and footnotes are not part of the official text; the headings and amendment notes are kept, footnotes are not.

So each Consolidated Law here is read from the Internet Archive's captures of the Senate's own pages (dates in the table). A law is included only when every page of it (index, parts, titles, articles, sections) has a capture, every section page states the date of its most recent revision, and every page was captured on or after the newest of those dates. Its one version is dated by that newest revision date, never by a capture date: each section's text was then the newest revision the Senate published. Each commit says so, and its `Consolidated:` trailer links the archive copy.

## Dates

Constitution: each edition is one version, dated by the in-force date on its cover (N.Y. Const. art. XIX, § 1: an amendment approved by the people takes effect on the first day of January after its approval). Editions before 2022 are not included yet. Consolidated Laws: one version each, dated as above. Earlier wording is not reconstructed, so each act's first version is credited to its publisher as the oldest version available.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist. No change is credited to an amendment yet: changes between Constitution editions are committed as unexplained, by the publisher (`publisher@dos.ny.gov.invalid`); the Consolidated Laws are authored by `New York State Senate (Internet Archive copy of nysenate.gov) <laws@nysenate.gov.invalid>`. The committer is always Lexifina.

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; the results are in `REPRODUCE.md`. The Constitution's words were compared with an independent text extraction of the same PDFs; each Consolidated Law section's words equal, in order, those of the archived page it was read from.
