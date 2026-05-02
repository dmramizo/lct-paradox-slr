# The Low-Carbon Transition Paradox: A Systematic Review

A systematic review of two literatures — sustainability-oriented trade,
and critical minerals as inputs to clean energy technologies — and
their cross-engagement.

This review forms a chapter of a doctoral dissertation at Curtin
University. It is intended for journal submission as an Analysis
article in *Ecological Economics* following dissertation completion.

## Status

In progress. Search execution: late May 2026. First complete draft:
30 September 2026.

## Repository structure

| Path | Contents |
|------|----------|
| `protocol/` | Review protocol, methodology, deviations log |
| `search/` | Boolean search strings, raw exports from databases |
| `screening/` | Deduplication, ASReview projects, screening decisions |
| `extraction/` | Coding rubric, coded data |
| `analysis/` | R scripts for bibliometric and synthesis analyses |
| `outputs/` | PRISMA flow diagram, tables, figures for the manuscript |
| `figures/` | Generated figures for the chapter |
| `docs/` | Chapter outline, supplementary materials, working notes |

## How to navigate this repository

If you are reviewing this work, the entry points are:

1. `protocol/methodology.md` — the finalized review protocol
2. `search/search_strings.yaml` — the Boolean search strings used
3. `extraction/coding_rubric.md` — the rules used to code each study
4. `outputs/` — generated tables, figures, and the PRISMA flow diagram
5. `analysis/` — R scripts that reproduce the analyses

## Reproducibility

Code is licensed MIT (see `LICENSE-CODE`).
Processed data are licensed CC BY 4.0 (see `LICENSE-DATA`).

R package versions are pinned via `renv` (`renv.lock`). To reproduce
the analyses, install R, clone this repository, open the `.Rproj`
file, and run `renv::restore()`.

Source articles are not redistributed in this repository (copyright).
Bibliographic metadata, citation graphs, screening decisions, and
coding outcomes are public.

## Citation

Ramizo, D. (in progress). The low-carbon transition paradox: A
systematic review of sustainability-oriented trade and critical
minerals in clean energy technologies. PhD dissertation chapter,
Curtin University.

## Contact

Dorothea Ramizo — [dorothea.ramizo@postgrad.curtin.edu.au]