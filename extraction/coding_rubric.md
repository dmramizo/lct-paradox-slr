# Coding Rubric

**Project:** The low-carbon transition paradox — a systematic review
of sustainability-oriented trade and critical minerals in clean
energy technologies

**Version:** 1.0 (locked before coding begins)
**Last updated:** [today's date]

This rubric is the operational counterpart to `protocol/methodology.md`
§8. It specifies the decision rules and worked examples that govern
how each included paper is coded. The rubric is locked at the commit
date of this file. Any modification after that date is recorded in
`protocol/deviations.md` with date, change, and rationale.

---

## How to use this rubric

1. **Open the included-paper PDF** and read the abstract, introduction,
   and methods sections in full. Skim results and discussion.
2. **For each coded variable**, apply the decision rule below.
3. **Record the decision** in the appropriate row of
   `extraction/corpus_A_coded.csv` or `extraction/corpus_B_coded.csv`.
4. **If a paper is borderline**, choose the closer category and
   record a note in the `coding_note` column. Do NOT create new
   categories mid-coding.
5. **If you encounter a paper that genuinely cannot be coded** under
   the rubric, flag it in `extraction/borderline_papers.md` with
   the reason. Borderline cases are reviewed in batch every two weeks
   during the coding period; rubric modifications, if any, are
   recorded as deviations.

The full coding spreadsheet schemas are in
`extraction/corpus_A_template.csv` and
`extraction/corpus_B_template.csv`.

---

## Part 1 — Corpus A: Sustainability-oriented trade

Coded variables: `trade_treatment`, `outcome_examined`,
`country_context`, `methodology_category`.

---

### Variable A1: `trade_treatment`

**Question to answer:** How does this paper conceptualize
sustainability-oriented trade?

**Categories:**

- `unified` — paper treats green trade and circular trade as a
  single phenomenon, OR examines only one of them in a way that
  treats it as the entirety of sustainability-oriented trade
- `green_circular_distinct` — paper explicitly distinguishes green
  trade from circular trade and treats them as separate (even if
  it studies only one)
- `further_differentiated` — paper differentiates within green or
  circular trade by channel (export vs. import), sector (e.g.,
  solar vs. wind), or technology class

**Decision rule:** Apply categories sequentially. If a paper meets
`further_differentiated`, code it as such even if it also meets
`green_circular_distinct`. Code at the highest level of
differentiation explicitly used.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Study of "environmental goods trade" without further breakdown | `unified` | No differentiation between green and circular |
| Study comparing recycled-materials trade with environmental goods trade | `green_circular_distinct` | Both treated as separate phenomena |
| Study of green exports specifically (not green imports) with stated rationale for the distinction | `further_differentiated` | Channel-level differentiation |
| Study of solar PV trade only | `further_differentiated` | Technology-class differentiation |
| Study of "green trade" referencing circular trade only in the literature review | `unified` | Circular trade is not part of the analysis |

**Edge cases:**

- A paper that uses "circular economy trade" as its term but never
  contrasts it with green trade → `unified` (the conceptualization
  is single-phenomenon)
- A paper using "low-carbon trade" as an umbrella covering both →
  `unified`
- A paper that mentions green/circular distinction in introduction
  but analyzes only aggregate sustainability-oriented trade →
  `unified`

---

### Variable A2: `outcome_examined`

**Question to answer:** What outcome dimensions does this paper's
empirical or theoretical analysis examine?

**Categories:**

- `environmental` — emissions, pollution, ecological footprint,
  resource use, biodiversity, or other environmental outcomes
- `capability` — economic complexity, productive capabilities,
  industrial capabilities, technological upgrading, learning
  effects, GVC position
- `both` — paper analyzes both environmental and capability
  outcomes within the same study
- `other` — paper analyzes a sustainability-oriented trade outcome
  that is neither environmental nor capability (e.g., welfare,
  inequality, employment, trade balance)

**Decision rule:** "Examines" means analyzes empirically OR develops
theoretical predictions about. Mention in the literature review
without analytical engagement does NOT qualify. If a paper analyzes
multiple outcomes, code based on the *primary* outcome the paper's
methods are designed to identify; if no clear primary outcome,
code as `both` only when environmental AND capability are both
analyzed empirically.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Panel regression of green trade on CO2 emissions | `environmental` | Single outcome dimension |
| Study of environmental goods exports and economic complexity | `capability` | ECI is a capability measure |
| Study estimating both environmental Kuznets curve AND complexity effects of green trade | `both` | Both dimensions analyzed |
| Study of green trade and household welfare | `other` | Neither environmental nor capability |
| Study of CO2 emissions that mentions complexity in the conclusion only | `environmental` | Complexity not analyzed |

**Edge cases:**

- A paper that uses GDP growth as the outcome → `other` (growth is
  not capability per se, even though it is correlated)
- A paper using GVC participation as the outcome → `capability`
  (GVC position reflects capability)
- A paper using employment in green sectors as the outcome →
  `other`

---

### Variable A3: `country_context`

**Question to answer:** What country sample does this paper analyze?

**Categories:**

- `developed` — sample restricted to high-income / OECD countries
- `developing` — sample restricted to low- and middle-income
  countries
- `mixed` — sample includes both developed and developing countries
  AND analysis includes interaction or heterogeneity by development
  stage
- `global` — sample includes both developed and developing countries
  but treated as a homogeneous global sample without development-stage
  heterogeneity

**Decision rule:** "Mixed" requires that the paper *does something*
analytically with the development distinction (interaction terms,
sub-samples, threshold analysis). A pooled regression of all countries
without distinction is `global`, even if the sample includes both
groups.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Study of EU-15 countries only | `developed` | High-income sample |
| Study of African developing economies | `developing` | LMIC sample |
| Panel of 100 countries with developing-country dummy interaction | `mixed` | Heterogeneity analyzed |
| Panel of 100 countries with no development-stage analysis | `global` | Pooled treatment |
| Threshold regression on urbanization across all countries | `mixed` | Analyzes heterogeneity |
| Single-country case study (Vietnam) | `developing` | LMIC sample |
| Single-country case study (Germany) | `developed` | High-income sample |

**Edge cases:**

- A paper using a continuous development indicator (e.g., GDP per
  capita) without binary/threshold distinction → `global` if no
  heterogeneity analysis; `mixed` if heterogeneity is the analytical
  focus
- A paper analyzing the BRICS group → `developing` (even though some
  classifications differ; for consistency, BRICS = developing in
  this rubric)
- A paper analyzing G20 countries → `mixed` if the analysis
  distinguishes high-income from middle-income members; `global`
  otherwise

---

### Variable A4: `methodology_category`

**Question to answer:** What is this paper's primary methodological
approach?

**Categories:**

- `empirical_econometric` — quantitative analysis of observational
  data (regression, panel methods, gravity models, instrumental
  variables, etc.)
- `theoretical` — formal model without primary empirical estimation
  (analytical, computational, simulation)
- `case_study` — qualitative or mixed-methods analysis of one or
  several specific cases
- `mixed` — combines empirical estimation with case-study or
  qualitative analysis as roughly co-equal components
- `review` — systematic, scoping, or narrative literature review

**Decision rule:** Code based on the methodological centerpiece of
the paper. Theoretical extensions appearing in an appendix do not
make a paper `mixed`. A regression robustness check on a primarily
case-study paper does not make it `mixed`.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Panel FE regression of green trade on emissions | `empirical_econometric` | Quantitative observational analysis |
| CGE model simulating green trade liberalization | `theoretical` | Formal model with simulation |
| Comparative case study of Korean and Taiwanese green industries | `case_study` | Comparative qualitative analysis |
| Paper combining a theoretical model and empirical estimation as core contributions | `mixed` | Co-equal components |
| Systematic review of trade-environment literature | `review` | Literature review |

---

## Part 2 — Corpus B: Critical minerals processing

Coded variables: `concentration_treatment`, `downstream_linkage`,
`mineral_focus`, `jurisdictional_focus`.

---

### Variable B1: `concentration_treatment`

**Question to answer:** How does this paper treat the concentration
of critical minerals processing?

**Categories:**

- `descriptive` — paper documents concentration as fact (market
  shares, HHI values, jurisdictional shares) without theoretical
  explanation
- `theorized` — paper offers a theoretical or qualitative
  explanation for why concentration formed or persists
- `formally_modeled` — paper formalizes concentration in a model
  (game-theoretic, IO, dynamic, optimization) with explicit
  equilibrium or comparative-static results

**Decision rule:** "Theorized" requires a verbal or qualitative
explanation that goes beyond stating shares. "Formally modeled"
requires mathematical or computational formalization with derived
results. A paper that cites a theoretical explanation from the
literature without developing one itself is `descriptive`.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Paper reporting that China holds 87% of REE refining | `descriptive` | Documents fact without explanation |
| Paper arguing concentration formed because of state-led industrial policy, citing historical evidence | `theorized` | Qualitative explanation |
| Paper deriving Cournot equilibrium for REE processing market | `formally_modeled` | Mathematical formalization |
| Paper reporting market shares and citing Mancheri 2015 for explanation | `descriptive` | Cites but does not develop theory |

---

### Variable B2: `downstream_linkage`

**Question to answer:** Does this paper engage with the linkage
between processed critical minerals and downstream green technology
manufacturing?

**Categories:**

- `none` — paper does not address downstream demand or linkage
- `mentioned` — paper mentions downstream demand or technology
  linkage in passing without analytical engagement
- `analyzed` — paper analyzes the linkage substantively (effect on
  costs, capacity, prices, technology adoption, supply security)

**Decision rule:** "Analyzed" requires that downstream linkage
appears as a variable, mechanism, or central analytical element of
the paper, not merely as motivation in the introduction.

**Worked examples:**

| Example paper type | Code | Why |
|---|---|---|
| Geological assessment of REE deposits | `none` | No downstream engagement |
| Paper on REE processing that motivates by mentioning EV demand growth | `mentioned` | Downstream as motivation only |
| Paper analyzing the impact of REE processing concentration on EV battery costs | `analyzed` | Linkage is analytical |
| Paper modeling lithium supply with green technology demand projections | `analyzed` | Downstream is part of model |

---

### Variable B3: `mineral_focus`

**Question to answer:** Which critical mineral(s) does this paper
focus on?

**Categories:**

- `REE` — rare earth elements (any combination of light or heavy REE)
- `lithium` — lithium specifically
- `cobalt` — cobalt specifically
- `nickel` — nickel specifically (battery-grade or general)
- `multiple` — paper analyzes 2–4 specific minerals comparatively
- `general` — paper treats "critical minerals" or "battery minerals"
  as a category without single-mineral focus, OR analyzes 5+ minerals

**Decision rule:** Code by primary analytical focus. A paper on REE
that includes lithium as a comparison case is `REE` if REE is the
primary subject; `multiple` if both are co-equal.

---

### Variable B4: `jurisdictional_focus`

**Question to answer:** Which jurisdiction(s) does this paper
analyze?

**Categories:**

- `China` — China is the primary jurisdictional focus
- `US` — United States primary
- `EU` — European Union primary (or specific EU member states)
- `Japan` — Japan primary
- `Australia` — Australia primary
- `other` — single-country focus on a jurisdiction not listed above
  (e.g., Indonesia, DRC, Chile)
- `multiple` — comparative analysis of 2–4 jurisdictions
- `global` — global supply chain or market analysis without primary
  jurisdictional focus

**Decision rule:** Single-jurisdiction case studies are coded by
that jurisdiction. Comparative studies of 2–4 jurisdictions are
`multiple`. Studies of "Western policy responses" without specific
country breakdown are `multiple` if at least two of US/EU/Japan are
explicitly addressed, `global` otherwise.

---

## Part 3 — Cross-corpus citation-context coding (RQ3)

This part of the rubric applies only to papers in the stratified
random sample drawn from each corpus. For each sample paper that
cites at least one work from the other corpus, every such citation
is coded for depth of engagement.

**The unit of coding is the citation, not the paper.** A single
paper may have multiple cross-corpus citations, each coded
separately.

---

### Variable C1: `engagement_depth`

**Question to answer:** At what depth does this citation engage with
the cited work?

**Categories:**

- `passing_reference` — citation appears in the introduction,
  related work, or footnotes without analytical use; would not
  affect the citing paper's argument or findings if removed
- `supporting_fact` — citation supports a specific factual or
  empirical claim made by the citing paper (e.g., "China holds 85%
  of REE processing capacity (Mancheri, 2015)") — removing it would
  require the citing paper to find another source for the same fact,
  but would not change the argument
- `substantive_analytical_use` — citation is integrated into the
  citing paper's argument, framework, model, methodology, or
  evidence base; the cited work shapes how the citing paper
  conceptualizes its problem, designs its analysis, or interprets
  its findings; removing it would substantively change the citing
  paper

**Decision rule:** Apply the "removal test." Ask: if this citation
were deleted from the paper, would (a) nothing meaningful change
[`passing_reference`], (b) the paper need to find a substitute
source for the same point [`supporting_fact`], or (c) the citing
paper's argument or analysis change substantively
[`substantive_analytical_use`]?

When unsure between two adjacent categories, code the lower one.
This rule biases toward conservative findings about cross-corpus
engagement, which is methodologically appropriate given that the
RQ3 finding is the central contribution of the chapter.

**Worked examples:**

| Citation context | Code | Reasoning |
|---|---|---|
| "Critical minerals supply has emerged as a central concern (IEA, 2023; Mancheri, 2015)" in the first paragraph of a green trade paper's introduction | `passing_reference` | Citation provides general framing, not analytical use |
| "China processes approximately 87% of global rare earth supply (Mancheri, 2015)" in a green trade paper that uses this fact to motivate a robustness check | `supporting_fact` | Specific fact supports a methodological choice |
| A green trade paper that builds its theoretical framework on Mancheri's account of capability accumulation in REE processing, applies that framework to its own data, and references Mancheri throughout the methods and discussion | `substantive_analytical_use` | The cited work shapes the citing paper's analytical structure |
| A critical-minerals paper that cites Sauvage 2014 in the introduction as one of several pieces of evidence that environmental goods trade has grown | `passing_reference` | General framing |
| A critical-minerals paper that uses Sauvage 2014's classification of environmental goods to delimit which minerals to study | `substantive_analytical_use` | Cited work shapes scope and methodology |
| A critical-minerals paper that cites Hidalgo & Hausmann 2009 to define economic complexity and then uses that definition in its own analysis | `substantive_analytical_use` | Definition is structural to the analysis |
| A critical-minerals paper that mentions "complexity-based development theory" in passing with a citation to Hidalgo & Hausmann | `passing_reference` | Mentioned but not used |

**Edge cases:**

- A citation that appears multiple times in the same paper (e.g.,
  in introduction, methods, and discussion) → code based on the
  most analytically substantive instance
- A citation in a footnote that is substantive in content → code
  by content, not by location
- A citation that is critical or oppositional (i.e., the citing
  paper argues *against* the cited work) → can still be
  `substantive_analytical_use` if the engagement is deep, even
  though disagreement is involved

---

## Part 4 — Coding workflow and quality checks

### Workflow

1. **Pilot coding (before locking the rubric for production).**
   Code 20 papers per corpus as a pilot. Identify any rubric
   ambiguities. Record changes in this file with version notes.
   Lock the rubric as v1.0 only after the pilot is complete.

2. **Production coding.** Code all included papers (Corpus A and
   Corpus B) using the locked rubric. Record decisions in the
   coding spreadsheets.

3. **Stratified sample for RQ3.** After full-text coding is
   complete, draw the stratified random sample. Code citations
   per the C1 rubric.

### Intra-rater reliability

A 15% random sample of coded papers (Corpus A and Corpus B
separately) is re-coded by the same reviewer (D. Ramizo) after a
10-day washout period. Cohen's κ is computed for each variable.
Disagreements are reviewed and the original coding is retained
unless the re-coding identifies a clear error, in which case both
the original and corrected codes are documented.

The same procedure applies to a 15% sample of cross-corpus
citations.

### Reporting

Final reported κ values, by variable, are included in the chapter's
methodology section. Coding decisions, including any disagreements
identified during the reliability check, are committed to
`extraction/reliability_check.csv`.

---

## Version history

| Version | Date | Change |
|---|---|---|
| 0.1 | [today's date] | Initial draft, pre-pilot |
| 1.0 | [TBD after pilot] | Locked for production coding |