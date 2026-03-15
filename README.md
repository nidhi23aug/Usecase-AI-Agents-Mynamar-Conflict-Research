# 🌾🤖 AI Agentic Tool Use for Research work

## Studying Agricultural Abandonment in Conflict-Affected Myanmar

An **AI-assisted scientific research pipeline** for studying **Agricultural Land Abandonment (ALA)** in **conflict-affected regions**, beginning with **Myanmar after the 2021 military coup**.

This project explores how **AI agents, remote sensing, and human scientific reasoning** can work together in a **reproducible research workflow**.

---

# 🧠 AI-Agentic Research Workflow

This repository connects the entire scientific workflow:

```
Literature → Research Gaps → Hypotheses → Data → Code → Analysis → Scientific Output
```

The repository is organized around **specialized AI agents**, each responsible for a stage of the research process.

However, **core scientific reasoning and implementation remain human-driven**.

---

# ⚙️ End-to-End Research Pipeline

This repository is designed to move through the following stages:

1️⃣ **AI-assisted literature search**
*(Best available AI literature retrieval tools)*

2️⃣ **Research gap identification**
*(AKD GAP Agent)*

3️⃣ **Hypothesis selection**
*(AKD GAP Agent + Human decision)*

4️⃣ **Method design**
*(Human-designed scientific methodology)*

5️⃣ **Remote sensing data discovery**
*(AKD CMR Data Search Agent)*

6️⃣ **Code discovery and reuse**
*(AKD Code Search Agent)*

7️⃣ **Implementation in Google Earth Engine (GEE)**
*(Human implemented)*

8️⃣ **Inference reasoning (CARE framework)**
*(Future AI agent)*

9️⃣ **Paper writing**

🔟 **Scientific illustrations**

1️⃣1️⃣ **Paper review**

1️⃣2️⃣ **Paper submission**

---

# 🌍 Project Motivation

Agricultural abandonment is often studied in relation to:

* 📉 economic change
* 🌱 land-use transitions
* 🚶 migration
* 🌿 environmental recovery

However, **conflict-driven agricultural abandonment remains poorly quantified**.

In conflict zones, abandonment may result from:

* displacement of farmers
* insecurity and violence
* restricted access to land
* labour shortages
* military occupation
* governance collapse

Myanmar after the **2021 coup** provides a critical case for studying how **conflict reshapes agricultural land use**.

Remote sensing offers a way to **monitor agricultural change even when field access is impossible**.

---

# 🎯 Core Research Theme

**Topic:** Agricultural Land Abandonment (ALA)
**Context:** Conflict-affected regions
**Initial Case Study:** Myanmar after the 2021 coup

---

## 🔎 Core Research Question

> **How has agricultural abandonment changed in conflict-affected parts of Myanmar after the 2021 coup, and how can remote sensing combined with AI-assisted research workflows help detect these patterns?**

---

# 🤖 AI Agent Pipeline

This repository contains **multiple research agents**, each performing a specific task.

The workflow integrates **AI automation with human scientific design**.

---

# 📚 1. Literature Search Agent

🔗 Benchmark repository
[https://github.com/nidhi23aug/Lit-Search-Tool-Comparison](https://github.com/nidhi23aug/Lit-Search-Tool-Comparison)

📂 Documentation

```
Agents/LitSearchAgent_Use/LitSearch_Using_Google_Labs.md
```

### 🎯 Purpose

Identify and evaluate the **best AI-assisted literature retrieval tools**.

### 🧠 Tasks

* Benchmark AI literature search tools
* Generate structured research queries
* Retrieve relevant papers
* Compare retrieval quality
* Select a working corpus of papers

### 📥 Input

* research prompts
* AI literature retrieval tools
* structured query templates

### 📤 Output

* curated paper list
* literature summaries
* bibliography
* search logs

### 📄 Example Paper Set

| ID  | Paper                                          |
| --- | ---------------------------------------------- |
| P11 | Crawford et al. 2022 – abandonment persistence |
| P2  | Prishchepov et al. 2025 – RS methods review    |
| P6  | Liu et al. 2025 – abandonment typology         |
| P3  | Goga et al. 2019 – definitions and validation  |
| P8  | Yusoff & Muharam 2015 – phenology detection    |
| P9  | Yusoff et al. 2017 – SAR detection             |
| P7  | Long et al. 2024 – abandonment intensity       |
| P8b | Yin et al. 2018 – Landsat segmentation         |
| P10 | Orontes Basin conflict LULC                    |

---

# 🧩 2. AKD GAP Search Agent

📂 Directory

```
Agents/GapAgents/
```

📄 Documentation

* [Gap Agent NJ](Agents/GapAgents/GapAgent_AKD_NJ.md)
* [Gap Agent Sid](Agents/GapAgents/Gap_Gemini_Sid.md)

### 🎯 Purpose

Analyze the literature corpus and identify **research gaps**.

### 🔍 Focus Areas

* abandonment during active conflict
* post-coup agricultural change in Myanmar
* remote sensing indicators of forced abandonment
* validation challenges in inaccessible regions

### 📤 Outputs

* research gap map
* candidate research questions
* possible hypotheses
* suggested methods

---

# 🧪 3. Hypothesis Development

### 🎯 Purpose

Define a **testable research hypothesis** based on identified gaps.

### Example Research Questions

**RQ1**

What is the spatiotemporal pattern of cropland abandonment and recultivation in Myanmar after the 2021 coup?

**Hypotheses**

H₀ — No detectable change in abandonment rates.

H₁ — Abandonment patterns change with conflict escalation.

---

**RQ2**

How long does conflict-related abandonment persist?

H₀ — Persistence patterns are similar to non-conflict regions.

H₁ — Persistence differs in conflict-affected areas.

---

### Possible Methods

* optical time-series analysis
* change-point detection
* crop activity proxies
* conflict-exposure stratification
* weakly supervised classification

---

# 🧑‍🔬 4. Human-Led Method Design

⚠️ **This stage is designed and implemented by human researchers.**

Agents assist with discovery, but **scientific methodology remains human-driven**.

---

### 🛰 Representation of Landscape Structure

High-dimensional **Google AlphaEarth embeddings** represent landscape structure in satellite imagery.

These embeddings provide a **generalized representation of land-surface signals**.

---

### 🤖 Cross-Regional Machine Learning Transfer

A supervised machine learning model is trained using **labeled abandonment samples from Mongolia and China**.

The model is transferred to Myanmar using **zero-shot cross-regional inference**.

This enables analysis in **data-scarce regions without retraining**.

---

### 🌱 Persistence-Based Definition of Abandonment

Agricultural land is classified as abandoned only if **uncultivated for three consecutive years**.

This definition aligns with:

* remote-sensing literature
* land governance policies
* national guidelines such as Malaysia's **3-year abandonment rule**

This prevents **temporary fallow from being misclassified as abandonment**.

---

# 🛰 5. AKD CMR Data Search Agent

📄 Documentation

```
Agents/DataSearch/DataSearch.md
```

### 🎯 Purpose

Identify **Earth observation datasets** relevant to the research hypothesis.

### Potential Data Sources

* Sentinel-2
* Landsat
* HLS
* vegetation products
* land cover datasets
* conflict exposure layers

### 📤 Outputs

* dataset inventory
* temporal coverage summary
* spatial suitability notes
* access instructions

---

# 💻 6. AKD Code Search Agent

### 🎯 Purpose

Identify reusable code for:

* cropland persistence detection
* abandonment mapping
* time-series change detection
* SAR-optical fusion
* conflict-sensitive geospatial analysis

### 📤 Outputs

* reusable code inventory
* adaptation plan
* implementation notes
* risk assessment

---

# 🌐 7. Google Earth Engine Implementation

### *(Human-Implemented Stage)*

👨‍💻 **Lead Implementation**

**Zaw Thu Htet (Toby)**
Istituto Universitario di Studi Superiori
Pavia, Italy

All geospatial analysis is implemented using **Google Earth Engine (GEE)**.

### Workflow

* satellite data preparation
* embedding generation
* machine-learning inference
* temporal persistence analysis
* cropland classification refinement
* spatial mapping and statistics

Goal: produce a **reproducible high-resolution agricultural abandonment analysis pipeline**.

---

# 🧠 8. CARE Inference Agent *(Future)*

### 🎯 Purpose

Move beyond detection toward **causal inference and reasoning**.

Possible capabilities:

* evidence synthesis
* uncertainty estimation
* explanation generation
* hypothesis evaluation

Status: **conceptual / exploratory**

---

# 🇲🇲 Case Study: Myanmar After the 2021 Coup

Myanmar is chosen because it combines:

* ⚡ rapid political rupture
* 🔥 spatially heterogeneous conflict
* 🚜 agricultural disruption
* 🚧 limited field access
* 🛰 strong need for satellite monitoring

This makes Myanmar a **scientifically challenging and important case study**.

---

# 🎯 Initial Research Goals

1️⃣ Build an AI-assisted literature discovery workflow
2️⃣ Construct a focused abandonment research corpus
3️⃣ Identify research gaps using AI agents
4️⃣ Convert gaps into remote-sensing hypotheses
5️⃣ Identify suitable Earth observation datasets
6️⃣ Locate reusable geospatial code
7️⃣ Implement the analysis in Google Earth Engine
8️⃣ Document uncertainty and limitations

---

# 📂 Repository Structure

```
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
```

---

# 🚀 Long-Term Vision

This project explores how **AI agents can augment scientific research workflows** by assisting with:

* literature exploration 📚
* gap discovery 🔍
* dataset identification 🛰
* code reuse 💻
* workflow automation ⚙️

The goal is **not to replace scientists**, but to create **AI-assisted research pipelines that accelerate discovery while keeping humans in the loop**.

---
