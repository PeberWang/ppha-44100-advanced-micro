# PPHA 44100 · Advanced Microeconomics — Open Collaboration

Shared repository for **PPHA 44100 Advanced Microeconomics for Public Policy I**, Fall 2026
(MACRM, Harris School of Public Policy, University of Chicago).

A place to build up, over the quarter, a systematic body of work: rigorous proofs,
problem-set solutions, and any related code.

> **Scope & copyright.** This repository contains only original, publicly shareable
> material. Instructor lecture notes, slides, the syllabus, and textbook PDFs (e.g. MWG)
> are **not** included here — they live outside this repo and may be copyrighted. Please
> do not add them.

## Layout

| Path | What goes here |
|---|---|
| `proofs/` | Theorem / proposition proofs, cleaned up and cross-referenced |
| `problem-sets/` | Solutions, organized as `ps01/`, `ps02/`, … |
| `data/` | Datasets you are allowed to share, plus data dictionaries |
| `code/` | Cleaning and analysis code (Python / R) |

## How to contribute

1. **Branch** — `git checkout -b ps03/alice` (or `proof/slutsky`, `code/pset02-cleaning`).
2. **Commit** — small, focused commits. Suggested messages: `ps03: solve exercise 2`,
   `proof: add envelope theorem`.
3. **Pull request** — open a PR into `main` and tag a maintainer. Keep each PR scoped to
   one problem set, one proof, or one code change.
4. **Math** — write math in LaTeX. Use separate `.tex` files for long derivations,
   Markdown for short write-ups.

### Conventions

- One theorem or proposition per file in `proofs/`.
- Always state your sources (MWG chapter, lecture-note page) so others can verify.
- **Never** commit copyrighted course material — problem-set PDFs, slides, textbook
  scans. Paraphrase problems and write solutions in your own words.

## Maintainers

- Mingpei Wang ([@PeberWang](https://github.com/PeberWang)) — *add co-maintainers here as needed*

## License

- **Code** (`code/`, scripts, notebooks): MIT — see [`LICENSE`](LICENSE).
- **Prose** (proofs, solutions, this README): CC BY 4.0 — see
  [`LICENSE-CC-BY-4.0.md`](LICENSE-CC-BY-4.0.md).
