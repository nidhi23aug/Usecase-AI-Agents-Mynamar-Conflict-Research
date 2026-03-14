# AI AGENTIC TOOL USE To study the Agricultural Abandonment in Conflict-Affected Myanmar

An end-to-end AI-driven research and analysis pipeline for studying **agricultural abandonment in conflict-affected regions**, starting with **Myanmar after the 2021 coup**.

This repository is designed to move from:

1. **AI-assisted literature search[[Use the Best AI Tool available]]**
2. **Research gap identification [[AKD GAP Agent]]**
3. **Hypothesis selection [[AKD GAP AGENT, Human Selection]]**
4. **Method design[[Human Designed]]**
5. **NASA/remote sensing data discovery[[ AKD CMR DATA SEARCH AGENT]]**
6. **Code discovery and reuse [[AKD CODE SEARCH AGENT]]**
7. **Implementation in Google Earth Engine (GEE) [[HUMAN SELECTED]]**
8. **Toward an inference-oriented agent using CARE [[Currently Human but FUTURISTIC an Agent]]**
10. **Writing Paper [[ ]]**
11. **Illustrations [[ AKD Illustration Agents]]**
12. **Review Paper [[ ]]**
13. **Paper Submission [[ ]]**

---

## Project Motivation

Agricultural abandonment is often studied in relation to economics, land-use transition, migration, and environmental recovery. In conflict-affected regions, however, abandonment can be driven by displacement, insecurity, access disruption, labor collapse, military occupation, or changing governance structures.

Myanmar after the 2021 coup offers a critical case for investigating how conflict reshapes agricultural land use and whether remote sensing can detect and characterize abandonment patterns in a fragile, rapidly changing context.

This repository aims to build a reproducible AI-Agentic workflow that connects literature, gaps, hypotheses, data, code, and implementation.

---

## Core Research Theme

**Topic:** Agricultural abandonment  
**Context:** Conflict-affected region  
**Initial case study:** Myanmar post-coup

### Initial framing question

How has agricultural abandonment changed in conflict-affected parts of Myanmar after the 2021 coup, and how can remote sensing plus AI-assisted scientific workflows help identify its spatial patterns, drivers, and likely consequences?

---

## AKD Pipeline

This repository is organized around a sequence of AKD-style agents.

### 1. Literature Search Agent [https://github.com/nidhi23aug/Lit-Search-Tool-Comparison] 
Purpose:
- Identify the best AI-assisted literature retrieval tools available
- Choose the Best AI- Assisted Lit Search tool for this study.
- Run structured searches on agricultural abandonment, conflict, land-use change, Myanmar, displacement, and Earth observation
- Compare retrieval quality and relevance
- Select a working paper set (5-10 papers) for downstream reasoning

Input:
- research prompts
- Use the best benchmarked AI retrieval tools [[ Work done [here](https://github.com/nidhi23aug/Lit-Search-Tool-Comparison) ]]
- query templates

Output:
- selected paper list
- paper notes
- bibliography
- search logs

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

---

### 2. AKD GAP Search Agent
Purpose:
- Read the selected literature corpus
- Identify what is missing in current research
- Surface underexplored combinations such as:
  - abandonment under active conflict
  - post-coup Myanmar agricultural change
  - remote sensing indicators of forced or conflict-driven abandonment
  - uncertainty and validation in inaccessible regions

Input:
- selected papers from literature search

Output:
- structured gap map
- candidate research hypotheses
- candidate methods

---

### 3. Hypothesis and Method Selection
Purpose:
- Choose one primary hypothesis
- Define a feasible remote sensing method
- Connect the hypothesis to measurable variables and sensors

Possible RQ and hypothesis:

RQ1 — What is the spatiotemporal pattern of cropland abandonment and recultivation in the Myanmar conflict region after the 2021 coup?
- H₀: No detectable change in abandonment/recultivation rates across conflict vs non-conflict periods/areas.
- H₁: Abandonment/recultivation rates show detectable temporal shifts aligned with conflict escalation/de-escalation.

RQ2 — How ephemeral is “conflict-linked” abandonment: what are the duration distributions and recultivation half-lives?
- H₀: Abandonment persistence does not differ from non-conflict benchmark areas/time.
- H₁: Abandonment persistence differs (shorter or longer) in conflict-affected areas.

Possible method directions:
- optical time-series analysis
- change-point detection
- crop activity proxies
- conflict-exposure stratified analysis
- weakly supervised classification in data-sparse regions

Output:
- primary hypothesis
- methodological design note
- variable/sensor mapping

---

### 4. AKD CMR Data Search Agent
Purpose:
- Search and shortlist Earth observation datasets relevant to the selected hypothesis and method
- Link method requirements to available products

Potential data sources:
- Landsat
- Sentinel-1
- Sentinel-2
- MODIS
- NASA products accessible through CMR
- land cover, vegetation, moisture, and disturbance products
- auxiliary conflict or accessibility layers where appropriate

Output:
- dataset inventory
- temporal coverage summary
- spatial suitability notes
- access instructions

## Tabular Summary (≥2 datasets)

| Rank | Short Name                    | Concept ID        | Optical?                 | 10 m resolution? | Temporal Coverage              | Primary Metadata Mismatch   |
| ---- | ----------------------------- | ----------------- | ------------------------ | ---------------- | ------------------------------ | --------------------------- |
| 1    | TerraScope Sentinel-2 L1C     | C2207478568-FEDEO | Yes                      | Yes (10/20/60 m) | 2015-07-06 → 2021-12-31        | Does not reach 2025         |
| 2    | TerraScope Sentinel-2 L2A TOC | C2207478523-FEDEO | Yes                      | Not explicit     | 2015-07-06 → 2021-12-31        | 10 m not explicit           |
| 3    | ESA WorldCover 2020           | C2655129129-FEDEO | Derived optical          | Yes              | Placeholder 1970 (actual 2020) | Single-year map             |
| 4    | ESA WorldCover 2021           | C2655129178-FEDEO | Derived optical          | Yes              | Placeholder 1970 (actual 2021) | Single-year map             |
| 5    | WorldCover NDVI 2020          | C2770608964-FEDEO | Optical-derived          | Yes              | Placeholder 1970               | Single-year composite       |
| 6    | WorldCover NDVI 2021          | C2655128870-FEDEO | Optical-derived          | Yes              | Placeholder 1970               | Single-year composite       |
| 7    | WorldCereal Active Cropland   | C2734302030-FEDEO | Derived cropland product | Not stated       | Placeholder 1970               | Temporal span not specified |
| 8    | Sentinel-2 L2A COG (INPE)     | C3108204483-INPE  | Yes                      | Not stated       | 2019-01-10 → 2025-06-25        | Brazil-only                 |
| 9    | Sentinel-2 L2A 16-Day Cube    | C3108204485-INPE  | Yes                      | Yes              | 2017-01-01 → 2025-06-09        | Brazil-only                 |
 
---

### 5. AKD Code Search Agent
Purpose:
- Search for reusable code, workflows, and algorithm patterns
- Identify existing GEE scripts or open-source implementations relevant to:
  - cropland persistence
  - abandonment detection
  - land-use change mapping
  - SAR/optical fusion
  - time-series break detection
  - conflict-sensitive geospatial workflows

Output:
- reusable code inventory
- implementation notes
- adaptation plan
- risks and limitations

---

### 6. GEE Execution Layer
Purpose:
- Implement the selected workflow in Google Earth Engine
- Build a reproducible, modular analysis pipeline
- Export maps, summaries, and validation products

Potential outputs:
- annual cultivated area layers
- abandonment likelihood maps
- pre/post-coup comparison maps
- conflict-exposure stratified statistics
- uncertainty summaries

---

### 7. CARE / Inference Agent (Exploratory)
Purpose:
- Move beyond detection toward inference
- Explore causal reasoning or confidence-aware interpretation
- Support statements such as:
  - where abandonment is most likely
  - what evidence supports that inference
  - which areas are uncertain
  - which explanations remain plausible

Status:
- exploratory
- conceptual design still under development

---

## Starting Case Study: Myanmar Post-Coup

Myanmar is used here as the initial study region because it combines:
- rapid political rupture after the 2021 coup
- severe spatial heterogeneity in conflict intensity
- likely agricultural disruption
- limited ground access for validation
- strong need for reproducible remote sensing workflows

This makes it a scientifically challenging and societally important setting for testing an AKD pipeline.

---

## Initial Research Goals

1. Build a reliable literature-search workflow using strong AI retrieval tools.
2. Select a focused corpus on agricultural abandonment in conflict and fragile settings.
3. Identify a tractable gap relevant to Myanmar post-coup.
4. Convert the gap into a testable remote sensing hypothesis.
5. Match hypothesis needs to available EO datasets and existing code.
6. Implement a first-pass prototype in GEE.
7. Document uncertainty, assumptions, and limitations clearly.

---

## Repository Structure

```text
docs/               project framing, decisions, hypotheses
lit_review/         search logs, selected papers, notes, bibliography
agents/             AKD agent prompts, logic, configs
data/               metadata, manifests, source inventories
gee/                Earth Engine scripts and asset references
notebooks/          exploratory notebooks and prototyping
src/                reusable code modules
results/            maps, figures, tables, summaries
