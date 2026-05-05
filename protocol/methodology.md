# Review Protocol and Methodology

**Project:** The low-carbon transition paradox — a systematic review
of sustainability-oriented trade and critical minerals in clean energy
technologies

**Author:** Dorothea Ramizo, Curtin University

**Protocol finalized:** 03 May 2026

**Repository commit:** This file's commit hash on this date is the
authoritative timestamp of the finalized protocol. Any modification
after the commit date is recorded in `protocol/deviations.md`.

This protocol is committed to a public repository before screening
begins and follows PRISMA 2020 reporting standards. The decision to
document the protocol in the repository rather than register it on
OSF reflects discussion with the doctoral supervisor and is consistent
with practice in published systematic reviews in *Ecological
Economics* (e.g., Toikka et al., 2026).

---

## 1. Background

The doctoral dissertation of which this review forms a chapter argues
that the low-carbon transition's central trade-based mechanisms —
green and circular trade — deliver their environmental and
developmental promises asymmetrically across country contexts, and
that the one mechanism (green exports) that could deliver both
promises depends on processed critical minerals concentrated in
midstream processing. This review precedes the dissertation's three
empirical essays and establishes the state of two relevant
literatures: sustainability-oriented trade, and critical minerals
processing for clean energy technologies.

## 2. Research questions

**RQ1.** How does the sustainability-oriented trade literature
conceptualize green and circular trade, and what outcome-by-context
cells (environmental / capability; developed / developing) does that
literature cover?

**RQ2.** How does the literature on critical minerals as inputs to
clean energy technologies characterize processing concentration and
its linkages to downstream technology manufacturing?

**RQ3.** At what depth, if at all, do these two literatures engage
with each other on the question of input constraints to
sustainability-oriented trade?

## 3. Review type

Systematic mapping review with bibliometric analysis, conducted under
PRISMA 2020. The review's purpose is to map coverage and engagement
patterns across two literatures, not to synthesize effect estimates
or generate causal claims.

## 4. Two-corpus design

Two parallel corpora are constructed:

- **Corpus A — Sustainability-oriented trade**
- **Corpus B — Critical minerals in clean energy technologies**

Each corpus has its own inclusion criteria, screening protocol, and
coding rubric. RQ1 is answered by Corpus A. RQ2 is answered by Corpus
B. RQ3 is answered by analysis of cross-corpus citations and a
stratified-sample citation-context coding exercise drawing on both
corpora.

## 5. Eligibility criteria

### Corpus A — Sustainability-oriented trade

**Include** if all of the following:

- Peer-reviewed journal article
- Published 2000–2026
- English language
- Examines green trade, circular trade, environmental goods trade,
  or trade in secondary materials/recycling, in relation to at least
  one of: environmental outcomes, productive capability, economic
  complexity, growth, or development outcomes

**Exclude** if any of the following:

- Editorial, book review, conference abstract without full text
- Focused exclusively on domestic production or domestic policy
  without trade dimension
- Focused exclusively on consumer-side circular economy without
  trade dimension
- Retracted

### Corpus B — Critical minerals in clean energy technologies

**Include** if all of the following:

- Peer-reviewed journal article
- Published 2000–2026
- English language
- Engages substantively with economics, industrial organization,
  policy, or trade dimensions of processed critical minerals (REE,
  lithium, cobalt, nickel, graphite, manganese, PGMs, or comparable)

**Exclude** if any of the following:

- Editorial, book review, conference abstract without full text
- Focused exclusively on geological, chemical, or metallurgical
  aspects without economic, policy, or trade analysis
- Focused exclusively on demand forecasting without engagement with
  supply or processing structure
- Retracted

## 6. Search strategy

**Databases:** Web of Science Core Collection and Scopus.

**Search dates:** Initial execution targeted for late May 2026. The
search will be re-run in late August 2026 to capture records added
during the review period; both datasets will be retained, and any
records added in the re-run will be processed identically.

**Boolean strings:** finalized in `search/search_strings.yaml` after
pilot searches in mid-May 2026. The committed strings constitute the
locked search strategy; any modification after the locked date is
recorded in the deviations log.

**Grey literature:** excluded from the systematic search. Selected
grey literature (IEA, USGS, World Bank, IRENA, EU JRC, Geoscience
Australia) is cited in introduction and discussion as policy and
empirical context. A supplementary grey literature search may be
conducted if requested during journal peer review; the candidate
sources are listed in `docs/grey_literature_sources.md`.

## 7. Screening protocol

**Deduplication:** by DOI (primary) and fuzzy title match (fallback),
implemented in R using the `revtools` package.

**Title/abstract screening:** in ASReview using active learning. Seed
set of 25 known-relevant papers per corpus to train the initial
classifier. Stopping rule: 50 consecutive irrelevant records after
the most recent inclusion.

**Reviewer:** solo (D. Ramizo). The review is conducted as part of a
doctoral dissertation, and a co-screener is not available. This is
declared as a methodological limitation.

**Reliability check:** 15% random sample of title/abstract decisions
re-screened by the same reviewer after a 10-day washout period.
Cohen's κ for intra-rater agreement is computed and reported.
Intra-rater reliability is acknowledged to be a weaker check than
inter-rater reliability.

**Full-text screening:** solo, with documented exclusion reasons for
every excluded paper, recorded in `screening/decisions.csv`.

**PRISMA 2020 Item 9 deviation declared.** PRISMA 2020 Item 9
recommends that data extraction and screening decisions be
conducted independently in duplicate by two reviewers to mitigate
single-reviewer error. This review is conducted by a sole reviewer
(D. Ramizo) due to the doctoral dissertation context, in which a
co-screener is not available. The intra-rater reliability check
described above (15% sample re-screened after a 10-day washout
period, with Cohen's κ reported) is used as a partial substitute
for inter-rater agreement. This deviation from PRISMA-preferred
practice is acknowledged here and declared as a methodological
limitation in §12.

## 8. Risk of bias assessment

Risk of bias assessment is not conducted at the individual study
level. The review's purpose is to map coverage and engagement
patterns across the included literature, not to synthesize
empirical findings or generate effect estimates. Individual study
bias does not affect mapping outcomes in the way it affects pooled
estimates in meta-analytic syntheses. Methodological quality of
included studies is, however, captured indirectly through the
`methodology_category` coding variable (Corpus A) and the
`concentration_treatment` coding variable (Corpus B), both of
which document the analytical depth at which each study addresses
its subject matter.

This decision corresponds to PRISMA 2020 Item 11 and is declared
explicitly to satisfy that item's reporting requirement.

## 9. Coding rubric

The coding rubric is documented in `extraction/coding_rubric.md` with
worked examples for each variable and engagement category.

### Corpus A — coded variables

- `trade_treatment` ∈ {unified, green-circular distinct, further
  differentiated}
- `outcome_examined` ∈ {environmental, capability, both, other}
- `country_context` ∈ {developed, developing, mixed, global}
- `methodology_category` ∈ {empirical-econometric, theoretical, case
  study, mixed, review}

### Corpus B — coded variables

- `concentration_treatment` ∈ {descriptive, theorized, formally
  modeled}
- `downstream_linkage` ∈ {none, mentioned, analyzed}
- `mineral_focus` ∈ {REE, lithium, cobalt, nickel, multiple, general}
- `jurisdictional_focus` ∈ {China, US, EU, Japan, Australia, other,
  multiple, global}

### Cross-corpus citation-context coding (RQ3)

A stratified random sample is drawn from each corpus. Stratification
is by publication-year quartile and by methodology category. Sample
size is calibrated post-screening to be sufficient to detect a
15-percentage-point difference in cross-corpus citation rates with
80% power.

For each sample paper that cites at least one work from the other
corpus, the citation is coded for depth of engagement:

- `passing_reference` — citation appears in introduction or related
  work without analytical use
- `supporting_fact` — citation supports a specific factual or
  empirical claim
- `substantive_analytical_use` — citation is integrated into the
  citing paper's argument, framework, or evidence base

Worked examples of each engagement category are committed to
`extraction/coding_rubric.md` before coding begins. The rubric is
not modified after coding starts.

## 10. Bibliometric analysis

**Software:** R, primarily the `bibliometrix` package (Aria &
Cuccurullo) for co-citation, bibliographic coupling, and keyword
co-occurrence within each corpus. Cross-corpus citation flow is
computed from merged reference lists.

**PRISMA 2020 flow diagram:** generated from final counts using the
`PRISMA2020` R package (Haddaway et al.).

**Missing data handling.** Where bibliographic metadata are
incomplete (missing DOI, abstract, author affiliations, keywords,
or reference lists), the affected fields are coded as missing in
the analytical dataset. Analyses requiring those specific fields
exclude the affected records, and reduced sample sizes are
reported alongside the relevant analytical output. No imputation
is performed.

**Heterogeneity handling.** The included literature is expected to
be heterogeneous in conceptual frameworks, methodological
approaches, outcome operationalizations, and country-context
focus. This heterogeneity is documented through the coding
variables specified in §9 and is reported in Section 3 of the
chapter as part of the descriptive map of each corpus. Because
the review's purpose is to characterize this heterogeneity rather
than to control for it or pool across it, no analytical correction
is applied. This decision corresponds to PRISMA 2020 Item 13.

**Certainty assessment.** GRADE-style certainty assessment (PRISMA
2020 Item 15) is designed to grade the certainty of evidence
underlying effect estimates in meta-analytic syntheses. Mapping
reviews characterize the structure and coverage of literature
rather than synthesize effect estimates, and GRADE is therefore
not applicable to this review's outcomes. Findings are reported
descriptively without certainty grades. This decision is consistent
with practice in published mapping and scoping reviews where
GRADE is not appropriate to the review type.

## 11. Scope of claims

This review is designed to establish:

- How each literature decomposes its central concepts and what cells
  of its outcome × context space it covers
- The structural and bibliometric relationship between the two
  literatures
- Whether prior published work integrates the conjunction central to
  the dissertation, and at what depth

This review is not designed to establish:

- The truth or falsity of empirical claims in either literature
- Effect sizes or causal estimates
- Conclusions about literatures excluded from the search (grey
  literature, non-English, databases beyond WoS and Scopus, works
  prior to 2000)

If the search identifies prior work that integrates the conjunction
at substantive depth, the contribution claim is revised to "extending
[identified work] by [specified additions]" rather than withdrawn or
overstated.

## 12. Limitations declared in advance

**Reporting and publication biases.** The review is subject to
several reporting biases inherent to systematic searches of
indexed peer-reviewed literature. The English-language and
peer-reviewed-only inclusion criteria exclude work published in
other languages, in grey literature, in policy reports, and in
non-indexed venues. Critical minerals economics in particular has
substantial relevant scholarship in Chinese-language sources, in
policy literature from international agencies (IEA, USGS, World
Bank, IRENA), and in industry analyses, none of which enters the
systematic search. The bibliometric component of the analysis is
additionally subject to citation patterns that may underweight
recent work (insufficient elapsed time for citations to accumulate)
and overweight English-language and Western-indexed venues. These
biases are not corrected for analytically. They are flagged here
in advance, addressed where relevant in the chapter's discussion
section, and constitute the principal external validity boundary
on the review's findings. This statement corresponds to PRISMA
2020 Item 14.

The following methodological choices, made for reasons of feasibility,
scope, or evidence-base appropriateness, are also declared as
limitations:

- Solo screening rather than dual screening; intra-rater reliability
  is a weaker check than inter-rater (see §7)
- Two databases only (WoS, Scopus)
- English language only
- Grey literature excluded from main analysis; selected grey
  literature is cited in introduction and discussion as context, and
  a supplementary search may be conducted during peer review if
  requested
- Stratified sample for RQ3 rather than full-corpus citation analysis
- Citation-context coding involves interpretive judgment;
  reproducibility depends on the rubric and worked examples rather
  than on coder training

## 13. Data and code availability

All search outputs (where licensing permits), screening decisions
(with exclusion reasons), coding spreadsheets, and analysis code are
deposited in this repository. Source articles are not redistributed
(copyright). Bibliographic metadata, citation graphs, screening
decisions, and coding outcomes are public.

## 14. Deviations log

Any deviation from this protocol after the commit date of this file
is recorded in `protocol/deviations.md` with date, change, and
rationale.