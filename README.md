# AI AGENTIC TOOL USE To study the Agricultural Abandonment in Conflict-Affected Myanmar

An end-to-end AI-driven research and analysis pipeline for studying **agricultural abandonment in conflict-affected regions**, starting with **Myanmar after the 2021 coup**.

## AI Agentic Tool Use
Studying Agricultural Abandonment in Conflict-Affected Myanmar. This repository implements an AI-assisted scientific workflow for studying agricultural land abandonment (ALA) in conflict-affected regions, beginning with Myanmar after the 2021 coup.

The project explores how AI agents, remote sensing, and human scientific reasoning can be combined into a reproducible workflow that connects:
```
literature → research gaps → hypotheses → data → code → analysis → scientific output.

```

The repository is organized around a set of specialized AI research agents, each responsible for a stage of the research process, while core scientific design and implementation remain human-driven.

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

## AI Agent Pipeline

This repository is organized around a sequence of AI-agents and humans as its being done in conventional research.

### 1. Literature Search Agent [https://github.com/nidhi23aug/Lit-Search-Tool-Comparison] 
Documents

[LitSearch Using Google Lab](Agents/LitSearchAgent_Use/LitSearch_Using_Google_Labs.md)


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
Directory

Agents/GapAgents/

Documentation

1) [Gap Agent NJ](Agents/GapAgents/GapAgent_AKD_NJ.md)
2) [Gap Agent Sid](Gap_Gemini_Sid.md)

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

### 3. Hypothesis
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
### 4. Human-Led Method Design [Human Designed]
Method design is performed by human researchers.

The agents support discovery and preparation, but scientific methodology and model design remain human-driven.

The current methodological approach focuses on detecting persistent agricultural land abandonment (ALA) using remote sensing and machine learning.

#### Key design components include:

Representation of Landscape Structure
High-dimensional Google AlphaEarth embeddings are used to represent landscape structure and land-use signals in satellite imagery.

These embeddings provide a generalized representation of land surface characteristics suitable for machine learning analysis.

#### Cross-Regional Machine Learning Transfer

A supervised machine-learning model is trained using labeled abandonment samples from Mongolia and China, where reliable training data are available.

The trained model is then transferred to Myanmar using a zero-shot cross-regional inference framework, enabling analysis in a data-scarce environment without retraining.

#### Persistence-Based Definition of Abandonment

To rigorously distinguish genuine abandonment from normal fallow cycles, the study applies a three-year persistence rule:

Agricultural land is classified as abandoned only if it remains uncultivated for three consecutive years.

This persistence-based definition aligns with:

- remote-sensing literature on cropland abandonment
- land governance policies in several countries
- national guidelines in places such as Malaysia, where land is considered abandoned after three years of non-cultivation

Using persistence criteria reduces the risk of misclassifying temporary fallow as permanent abandonment.


### 5. AKD CMR Data Search Agent
Documentation- 
[DataSearch](Agents/DataSearch/DataSearch.md)
Purpose:
- Search and shortlist Earth observation datasets relevant to the selected hypothesis and method
- Link method requirements to available products

Potential data sources:

- Sentinel-2
- Landsat
- HLS
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

### 6. AKD Code Search Agent
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

### 7. GEE Execution Layer (Human-Implemented Stage)

Currently this is being Implemented by ***Zaw Thu Htet*** (Toby) from the ***Istituto Universitario di Studi Superiori, Pavia, Italy*** .

All geospatial analysis is to be implemented by human researchers (Toby) using Google Earth Engine (GEE).
The GEE workflow includes:
- satellite data preparation
- embedding generation
- machine-learning inference
- temporal persistence analysis
- cropland classification refinement
- spatial aggregation and mapping

The goal is to produce a reproducible remote-sensing analysis pipeline capable of detecting agricultural land abandonment at high spatial resolution.

---

### 8. CARE / Inference Agent (Exploratory, Future)

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

1. Build a reliable AI-assisted literature discovery workflow
2. Construct a focused research corpus on agricultural abandonment
3. Identify research gaps(AKD-Gap Search Agent) relevant to conflict-affected agriculture
4. Convert gaps into testable remote-sensing hypotheses (AKD-Gap Search Agent)
5. Identify suitable Earth observation datasets (AKD-CMR- Agent)
6. locate reusable geospatial analysis code (AKD-Code Search Agent) 
7. implement the remote-sensing workflow in Google Earth Engine (Human driven by Toby)
8. document assumptions, uncertainty, and limitations

---

## Repository Structure

```text
Agents/
│
├── DataSearch/
│   └── DataSearch.md
│
├── GapAgents/
│   ├── GapAgent_AKD_NJ.md
│   └── Gap_Gemini_Sid.md
│
├── LitSearchAgent_Use/
│   ├── LitSearch Using Google Labs.md
│   ├── list-of-articles-sid.md
│   └── test.md
│
README.md
