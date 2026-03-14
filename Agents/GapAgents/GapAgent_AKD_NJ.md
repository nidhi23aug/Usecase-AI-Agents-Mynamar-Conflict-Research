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
Using the matrices, the agent identifies three gap types.

## Explicit gaps
Directly stated in literature.

Example:
- Lack of consistent abandonment definition
- Weak validation datasets
- Difficulty monitoring unstable parcels

---

## Inferred gaps
Derived through cross-paper comparison.

Examples:

- Conflict-linked abandonment rarely mapped as **trajectories**
- Need to distinguish **fallow vs abandonment**
- Limited SAR-optical trajectory integration

---

## Contradictions
Differences between studies.

Examples:

| Issue | Paper A | Paper B |
|------|--------|--------|
Minimum abandonment duration | 2 years | 5 years |
Recultivation definition | ≥1 year | ≥4 years |
Observation strategy | multi-temporal optical | SAR single date |

---

# Stage 5 — Research Question Generation
Research questions are generated from identified gaps.

Example candidates:

### RQ1
What is the **spatiotemporal pattern of abandonment and recultivation** in the Myanmar conflict region?

### RQ2
How **ephemeral is conflict-linked abandonment**?

Metrics:
- duration distributions
- recultivation half-life

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
