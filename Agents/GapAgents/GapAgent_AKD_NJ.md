# GAP AGENT Workflow for Research Gap Discovery
This repository documents the **multi-stage research gap discovery pipeline** used to analyze literature and identify research gaps in conflict-related cropland abandonment studies.

The pipeline uses **OpenAI GAP Agent**, which includes an initial **Summarizer Agent** followed by the **AKD CARE GAP Agent**.

Agent workflow reference:
https://platform.openai.com/agent-builder/edit?version=draft&workflow=wf_699f24de418c819084a22fa9e32479c10427a51408a83b34

---

# Pipeline Overview

The workflow progresses through **6 stages**:

1. **Stage 1 – Scope Selection**
2. **Stage 2 – Paper Filtering**
3. **Stage 3 – Gap Matrix Construction**
4. **Stage 4 – Gap Identification**
5. **Stage 5 – Research Question Generation**
6. **Stage 6 – Gap Prioritization**

Users move to the next stage **only after making a selection decision** at the end of each stage.

# Stage 0 — Input Processing (Automated)
Before user interaction begins, the **Summarizer Agent processes the literature corpus**.

### Input
- Collection of research papers (PDFs)

### Automated Tasks
- Extract summaries
- Identify methods, definitions, and key findings
- Produce structured summaries used by later stages

### Output
- Structured literature summaries used by the GAP Agent.

---

# Stage 1 — Scope Selection
Users choose the **primary research scope** that defines the gap discovery process.

## Scope Options

### Scope A — Mapping conflict-linked cropland abandonment & recultivation trajectories
Core idea:
Map **abandonment → recultivation → re-abandonment dynamics** as time-series trajectories.

Motivation:
- Abandonment is often **temporary and cyclical**.
- Recultivation must be explicitly modeled.

Typical outputs:
- Abandonment start year
- Duration
- Recultivation probability
- Spatial hotspots

---

### Scope B — Crop-specific abandonment detection in cloud-prone conflict regions
Focus:
- Paddy rice
- Plantations (rubber / oil palm)

Methods:
- Phenology
- SAR remote sensing

Outputs:
- Crop-specific abandonment maps
- Error patterns by crop

---

### Scope C — Conflict attribution
Goal:
Estimate **causal relationship between conflict intensity and abandonment**.

Methods:
- Difference-in-Differences
- Propensity Score Matching

Outputs:
- Estimated treatment effects

---

### Scope D — Persistence and environmental implications
Focus:
Measure whether abandonment persists long enough to affect:

- Carbon sequestration
- Biodiversity recovery

Outputs:
- Persistence half-life
- Long-term abandonment zones

---

## User Selection
User must choose:

```

Scope: A / B / C / D
Region:
Crop system:
Time window:

```

NJ's selection:

```

Scope A selected

```

NJ then proceeds to **Stage 2**.

---

# Stage 2 — Paper Filtering
Based on the chosen scope, the system selects relevant literature.

### Example: Papers selected for Scope A

| ID | Paper |
|----|------|
| P11 | Crawford et al. 2022 – abandonment persistence |
| P2 | Prishchepov et al. 2025 – RS methods review |
| P6 | Liu et al. 2025 – abandonment typology |
| P3 | Goga et al. 2019 – definitions and validation |
| P8 | Yusoff & Muharam 2015 – phenology detection |
| P9 | Yusoff et al. 2017 – SAR detection |
| P7 | Long et al. 2024 – abandonment intensity |
| P8b | Yin et al. 2018 – Landsat segmentation |
| P10 | Orontes Basin conflict LULC |

These papers form the **analysis corpus** for later stages.

---
# Stage 3 — Gap Matrix Construction
Gap matrices structure the literature analysis.

## Matrix 1 — Trajectory Dynamics
Focus:
Understanding **abandonment timing and cycling**.

Rows
```
A1 Abandonment timing
A2 Duration distribution
A3 Recultivation probability
A4 Multiple cycles
A5 Temporary vs long-term abandonment

```

Columns
```

Binary mapping
Annual time series
Event segmentation
Intensity metrics

```

---

## Matrix 2 — Observation Strategy
Focus:
Remote sensing challenges in conflict regions.

Rows
```

Cloud cover
Fragmented parcels
Terrain effects
Vegetation regrowth
Land cover confusion

```

Columns
```

Optical phenology
SAR time series
Optical-SAR fusion
Object-based mapping

```

---

## Matrix 3 — Conceptual Definitions
Focus:
Distinguishing land use categories.

Classes
```

Short fallow
Seasonal abandonment
Long-term abandonment
Shifting cultivation
Passive abandonment (conflict)

```

Operational criteria
```

Minimum inactivity years
Land cover transitions
Management signals
Recultivation rules

```

---

## Matrix 4 — Validation Strategy
Focus:
Validation challenges in conflict zones.

Sources
```

Field surveys
VHR imagery
Time series validation
Ancillary datasets
Crowdsourced interpretation

```

Quality metrics
```

Accuracy assessment
Temporal alignment
Uncertainty estimates
Reproducibility

```

---

# Stage 4 — Gap Identification
A) Explicit gaps (author-stated)
EG1 — No consistent, widely accepted abandonment definition (comparability problem)
Origin: Explicit

Evidence:

Goga et al. review: “no generally accepted AAL definition” (review conclusion) [Summary: Paper 3 Abstract/Conclusions].

Liu et al. review: definitions vary across organizations and studies; seasonal vs year-round; active vs passive [PDF: remotesensing.0584.pdf ].

EG2 — Lack of field research / validation data designed for abandonment classes and trajectories
Origin: Explicit

Evidence:

Goga et al.: “absence of similar field research… for validation and understanding” [PDF: remotesensing-11-02759.pdf ; also Summary: Paper 3 Abstract].

EG3 — Difficulty monitoring fragmented and temporally unstable abandoned parcels
Origin: Explicit

Evidence:

Liu et al. 2025 review calls for advances in observing “fragmented and temporally unstable parcels” [PDF: remotesensing.0584.pdf ].

EG4 — Under-exploration of some regions (incl. parts of Southeast Asia) and some land-use systems; need method adaptation
Origin: Explicit

Evidence:

Prishchepov et al. 2025 review: abandonment underexplored in “other parts of Southeast Asia” and methods may need adjustment for different field/land-use structures [PDF: 1-s2.0-S0034425725004237-main.pdf ].

B) Inferred gaps (cross-paper synthesis; Myanmar-conflict use-case motivated, but gap is stated within-corpus)
IG1 — Conflict-driven abandonment is recognized conceptually, but not operationalized as annual abandonment–recultivation trajectories in tropical conflict settings (within this set)
Origin: Inferred

Confidence: Medium (strong conceptual support; Myanmar not directly studied in set)

Evidence A: Passive abandonment can be caused by armed conflict (typology) [PDF: remotesensing.0584.pdf ].

Evidence B: Abandonment is often ephemeral and cycles with recultivation, requiring annual tracking and persistence modeling (half-lives; repeated transitions) [Summary: Paper 11 RESULTS “Modeling recultivation (decay)” + recultivation durations].

⇒ Gap: The corpus does not show a worked example that combines conflict context with annual trajectory + recultivation/persistence metrics (e.g., half-lives, cycling intensity) in a tropical/monsoon conflict region like Myanmar.

IG2 — Need methods that separate short disruption/fallow vs abandonment vs recultivation when land use is intermittent (likely in conflict zones)
Origin: Inferred

Confidence: High (directly supported by multiple methods/definitions in set)

Evidence A: Crawford defines abandonment conservatively as ≥5 consecutive years out of cultivation; recultivation is ≥1 year and “resets” regeneration [Summary: Paper 11 MATERIALS AND METHODS].

Evidence B: Yin et al. (RSE 2018) explicitly distinguishes abandonment (>5 years inactive) from fallow (<5 years) and defines recultivation requiring persistence (remain active >4 years) [PDF: yin_prishchepov_et_al_RSE_2018.pdf ].

⇒ Gap: For a Myanmar conflict setting (where interruptions may be multi-year but not “terminal”), the corpus does not provide guidance on how to calibrate/choose thresholds and event definitions so that “conflict disruption” isn’t mis-labeled as long-term abandonment (or vice versa).

IG3 — Cloud-prone monsoon regions: trajectory mapping often depends on optical annual products, but tropical studies show SAR is essential; integrated trajectory + SAR workflows are not demonstrated in this set
Origin: Inferred

Confidence: Medium

Evidence A: Malaysia studies show the need for multi-temporal phenology in the tropics and motivate SAR due to cloud limitations; PALSAR enables mapping under clouds [Summary: Paper 9 Introduction/Conclusion; Summary: Paper 8].

Evidence B: Crawford’s persistence/decay modeling is built on annual Landsat land-cover trajectories (optical) [Summary: Paper 11 MATERIALS AND METHODS]. Reviews recommend optical–radar fusion (Sentinel-1 + Sentinel-2) [Summary: Paper 3 Abstract/Conclusions].

⇒ Gap: The corpus does not include a concrete, end-to-end example that (i) produces annual abandonment–recultivation trajectories and (ii) uses SAR systematically to fill monsoon/cloud gaps in a way that preserves event timing (start year, duration, recultivation).

IG4 — Crop-type dependence: strong performance for paddy abandonment, weaker for plantations (e.g., oil palm); conflict zones may contain mixed systems, but crop-stratified trajectory metrics are underdeveloped in this set
Origin: Inferred

Confidence: Medium

Evidence A: SAR phenology/classification: paddy abandonment high accuracy; oil palm abandonment low accuracy and affected by biomass saturation/terrain geometry and minority-class issues [Summary: Paper 9 Results/Conclusion].

Evidence B: Reviews call out under-studied land-use types such as plantations and need more nuanced mapping beyond binary [PDF: 1-s2.0-S0034425725004237-main.pdf ].

⇒ Gap: The corpus lacks a trajectory framework that reports abandonment/recultivation persistence metrics by crop system (paddy vs plantation) while also addressing the known sensor failure modes (e.g., oil palm separability) that could bias conflict-region estimates.

IG5 — Persistence (“half-life/decay”) models exist, but uncertainty propagation from classification errors + smoothing choices into persistence estimates is not fully developed in this set (important when ground truth is scarce)
Origin: Inferred

Confidence: Low–Medium (we have hints; not fully specified)

Evidence A: Crawford applies temporal smoothing and models cohort decay/half-lives from mapped trajectories [Summary: Paper 11 METHODS + “decay modeling”].

Evidence B: Reviews emphasize uncertainty/validation weakness and that many studies lack robust validation/field data [Summary: Paper 3 Abstract/Conclusions; PDF: 1-s2.0-S0034425725004237-main.pdf discussing validation limits].

⇒ Gap: For a conflict setting like Myanmar (limited field validation), the corpus does not provide a clear blueprint for quantifying how map error affects estimated durations/half-lives, which could be central if you plan to report “persistence” as a key result.

C) Contradictions / disagreements (within-corpus)
CD1 — Minimum duration threshold for “abandonment” varies (2 years vs 5 years), changing what gets counted as abandonment vs fallow/disruption
Side A (short threshold): Long et al. (Yangtze basin) uses ≥2 consecutive years non-cultivation [PDF: remotesensing-16-01052.pdf ].

Side B (long threshold): Crawford uses ≥5 consecutive years [Summary: Paper 11 METHODS]; Yin 2018 also uses >5 years and explicitly maps fallow separately [PDF: yin_prishchepov_et_al_RSE_2018.pdf ].

Why it matters for Myanmar conflict study: A 2-year rule may treat conflict disruptions as “abandonment,” while a 5-year rule may miss meaningful conflict impacts if displacement/disruption lasts 2–4 years.

Hypothesized drivers (not resolved): differing crop rotations/climates; policy definitions; objective (monitoring vs ecological regeneration focus).

CD2 — How much multi-temporal information is “necessary” differs by sensor/crop (optical phenology vs SAR single-date acceptability)
Side A: Optical phenology approach argues multi-temporal imagery is essential; paddy needs ≥3 key dates; rubber needs dates confirming wintering/defoliation [PDF: remotesensing-07-11974.pdf ].

Side B: SAR study reports single SAR image can be “satisfactory” for rubber/oil palm in their setting, though oil palm abandonment still low accuracy and thresholds must be adjusted [PDF: Phenology and classification…PALSAR…pdf ; Summary: Paper 9].

Hypothesized drivers: sensor physics (backscatter vs reflectance), crop structure, availability of acquisition dates, terrain.

CD3 — Recultivation definition differences (any 1-year return vs requiring sustained activity)
Side A: Crawford treats any ≥1 year return to cropland as recultivation that resets regeneration [Summary: Paper 11 METHODS].

Side B: Yin 2018 labels recultivation when converted back and remains active >4 years [PDF: yin_prishchepov_et_al_RSE_2018.pdf ].

Hypothesized drivers: focus on ecological interruption (Crawford) vs robust change detection against noise (Yin).

Pause — confirm gaps to carry forward
You selected matrices 1+2, so I can proceed in two ways:

Proceed to Stage 5 (Research Questions/Hypotheses) using the inferred gaps above (conflict + trajectories; thresholds; SAR+optical integration; crop dependence; uncertainty).

Or, you can tell me which 3–5 gaps are most relevant to your Myanmar study and I’ll build Stage 5 only from those.

Reply with either:

“Confirm Stage 4, proceed to Stage 5”, or

A list of gap IDs (e.g., IG1, IG2, IG3, CD1) you want to focus on.


---

# Stage 5 — Research Question / Hypothesis Suggestions (derived from Stage 4 gaps; suggestions, not endorsements)

Below are 10 candidate questions tailored to a Myanmar conflict-region study of cropland abandonment–recultivation trajectories (Scope A). I keep them neutral and association-first unless the corpus supports stronger claims.

For each: Linked gap(s) + candidate H₀/H₁ + variables/proxies consistent with this corpus.

### RQ1 — What is the spatiotemporal pattern of cropland abandonment and recultivation in the Myanmar conflict region?
Derives from: IG1, EG3, EG4

H₀: No detectable change in abandonment/recultivation rates across conflict vs non-conflict periods/areas.

H₁: Abandonment/recultivation rates show detectable temporal shifts aligned with conflict escalation/de-escalation.

Variables/proxies (RS): annual (or seasonal) cropland state; abandonment onset year; recultivation onset year; duration distributions (per pixel/object). (Trajectory logic grounded in Crawford [Summary: P11 Methods/Results] and Yin segmentation approach [PDF: yin_prishchepov…2018].)

### RQ2 — How ephemeral is “conflict-linked” abandonment: what are the duration distributions and recultivation half-lives?
Derives from: IG1, Matrix 1 (A2–A4)

H₀: Abandonment persistence does not differ from non-conflict benchmark areas/time.

H₁: Abandonment persistence differs (shorter or longer) in conflict-affected areas.

Variables/proxies: cohort-based survival/decay curves; half-life (time to 50% recultivation) as in Crawford’s decay framing [Summary: P11 “Modeling recultivation of abandoned croplands”].

### RQ3 — How sensitive are Myanmar abandonment estimates to the minimum non-cultivation threshold (e.g., 2-year vs 5-year)?
Derives from: IG2, CD1

H₀: Estimated abandonment area/timing/persistence are robust to threshold choice.

H₁: Estimates vary substantially with threshold choice, changing interpretation of conflict impacts.

Variables/proxies: abandonment maps under multiple thresholds; confusion between “fallow/disruption” vs “abandonment” (threshold debate: Long et al. ≥2 years [PDF: remotesensing-16-01052.pdf] vs Crawford ≥5 years [Summary: P11 Methods]; Yin distinguishes fallow vs abandonment [PDF: yin_prishchepov…2018].)

### RQ4 — Does adding SAR time series (e.g., Sentinel-1 / PALSAR-type logic) improve event timing (abandonment/recultivation year) under monsoon cloud conditions?
Derives from: IG3, Matrix 2 (C1 + D2/D3)

H₀: SAR integration does not improve abandonment/recultivation timing accuracy compared with optical-only time series.

H₁: SAR integration improves timing accuracy and reduces missingness/uncertainty in cloudy seasons.

Variables/proxies: number of valid observations; temporal gaps; agreement with reference labels; timing error distribution. (Cloud constraint and SAR value supported by Malaysia SAR paper [Summary: P9 Intro/Conclusion]; fusion recommended in Goga review [Summary: P3] and Prishchepov review [PDF: 1-s2.0…04237…].)

### RQ5 — Which crop systems in the Myanmar conflict region are most reliably mapped for abandonment/recultivation (e.g., paddy vs plantations), and what are dominant error modes?
Derives from: IG4, CD2

H₀: Mapping performance is similar across crop systems.

H₁: Performance differs by crop system; some systems (e.g., plantations) exhibit systematic confusion.

Variables/proxies: class-wise accuracy (F1/user/producer); crop mask/strata; terrain/geometry flags for SAR artifacts. (Crop dependence is explicit in PALSAR study: oil palm abandonment harder [Summary: P9 Results].)

### RQ6 — How common are repeated cycles (abandon → recultivate → abandon again) in conflict-affected landscapes?
Derives from: Matrix 1 (A4), Crawford cycling observation

H₀: Most parcels exhibit at most one abandonment episode.

H₁: A substantial share of parcels exhibits multiple cycles (turnover).

Variables/proxies: count of transitions per pixel/object; mean recultivation episode length; probability of re-abandonment. (Crawford notes recultivation episodes often short and repeated transitions occur [Summary: P11 Results].)

### RQ7 — How do terrain and landscape fragmentation influence detectability and estimated persistence of abandonment?
Derives from: EG3, Matrix 2 (C2–C3)

H₀: Fragmentation/terrain do not materially affect abandonment detection or persistence estimates.

H₁: Small/fragmented parcels and complex terrain increase omission/commission errors and bias persistence metrics.

Variables/proxies: parcel size proxies (object sizes from segmentation); slope/elevation (DEM); radar layover/shadow proxies; edge density. (Fragmentation + terrain are explicit challenges in Liu review [PDF: remotesensing.0584.pdf].)

### RQ8 — What is the “recultivation definition” effect: does defining recultivation as ≥1 year (Crawford) vs sustained activity (e.g., ≥4 years in Yin) change inferred turnover?
Derives from: CD3, IG2

H₀: Recultivation rate/half-life estimates are robust to recultivation definition.

H₁: Different recultivation definitions produce meaningfully different turnover and persistence conclusions.

Variables/proxies: alternative recultivation rules; resulting half-lives; re-abandonment frequency. (Crawford: ≥1 year resets [Summary: P11 Methods]; Yin: sustained active >4 years for recultivation [PDF: yin_prishchepov…2018].)

### RQ9 — How much does classification uncertainty propagate into persistence metrics (duration distributions, half-lives) when ground validation is limited?
Derives from: IG5, EG2

H₀: Persistence metrics are stable under plausible classification error models.

H₁: Persistence metrics are sensitive to classification errors/smoothing choices.

Variables/proxies: Monte Carlo/perturbation over error rates; alternative smoothing windows; confidence intervals for half-life estimates. (Need motivated by Crawford’s modeling reliance on mapped trajectories [Summary: P11 Methods] + reviews stressing weak validation [Summary: P3].)

### RQ10 — Are there detectable clusters where abandonment is likely to persist (low recultivation hazard), suggesting “stable” versus “unstable” abandonment zones?
Derives from: Matrix 1 (A3), IG1

H₀: No spatial clustering in persistence; hazards are spatially homogeneous after covariates.

H₁: Persistence clusters exist (e.g., persistent abandonment pockets), potentially linked to accessibility/land quality proxies.

Variables/proxies: spatial hazard surfaces; distance to roads/settlements (if used); cohort hazard by location. (Liu review notes distance/accessibility proxies often used for causes [PDF: remotesensing.0584.pdf], but causal interpretation should remain cautious unless design supports it.)

Pause — confirm which RQs you want to keep (to proceed to Stage 6)
Pick 6–8 question IDs you want to carry forward (e.g., RQ1, RQ2, RQ3, RQ4, RQ6, RQ9).

Once you confirm, I’ll do Stage 6 — qualitative prioritization (High / Medium / Exploratory) using only corpus-grounded criteria (conceptual value, intra-corpus novelty, impact; feasibility excluded).
---

## NJ Selection
NJ selects research questions.

Example:

```

Selected:
RQ1
RQ2

```

---

### Exploratory
Optional extensions.

Examples:
- Uncertainty propagation
- Crop-system dependence

---

# Final Output
The workflow produces:

- Ranked research gaps
- Supporting literature evidence
- Suggested research questions

---

# Summary of Workflow

```

Paper corpus
↓
Summarizer Agent
↓
Stage 1 — Scope selection
↓
Stage 2 — Paper filtering
↓
Stage 3 — Gap matrices
↓
Stage 4 — Gap identification
↓
Stage 5 — Research questions



---

# Intended Use
This pipeline is designed for:

- research gap discovery
- literature synthesis
- systematic review assistance
- research proposal development

---
