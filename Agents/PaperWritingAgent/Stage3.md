# Stage 3 Reasoning Policy v0.2
approved: false

## 1) Workflow recipe
- Clarification approach:
  - Always begin by identifying missing inputs, ambiguities, and required materials for the current section
- Outline/planning behavior:
  - Generate a structured outline aligned with the MDPI *Land* section before drafting
- Drafting mode:
  - Produce section-by-section manuscript text in scientific style
- Critique/revision loop:
  - After each draft, evaluate against Stage 1 success criteria and rigor requirements
  - Revise accordingly
- Packaging behavior:
  - Each iteration must include:
    A) Draft  
    B) Open Questions / Required Inputs  
    C) TBDs & Risks  
    D) Assumptions  
    E) Change Log  
    F) Sources/Citations  

## 2) Grounding mode selection
- Must comply with Stage 2 source permissions: true
- Study-specific claims grounded primarily in user materials: true
- External-source use:
  - Allowed for literature review, framing, and discussion context
  - Not allowed to generate or alter study-specific results, methods, or datasets

## 3) Ask-vs-assume policy
- When to ask user for missing inputs:
  - Always ask when any required information is missing, ambiguous, or incomplete
- When assumptions are permitted:
  - Only when explicitly necessary to proceed and must be labeled
- Labeling requirements:
  - All assumptions must be explicitly labeled as "assumption"
  - Missing required data must be labeled as "tbd_placeholder"
  - Interpretations beyond direct inputs must be labeled as "inference"

## 4) Conflict handling
- Source precedence:
  - No automatic resolution
- Conflict resolution process:
  - All conflicts between sources (user inputs vs external sources, or internal inconsistencies) must be explicitly flagged
  - Drafting must pause or proceed with clearly marked conflict notes
- User decision-rights:
  - User must resolve all flagged conflicts before finalization

## 5) Quality gates
- Alignment with Stage 1:
  - Must follow MDPI *Land* structure and scientific tone
- Grounding/provenance checks:
  - All claims must map to allowed sources or be labeled appropriately
- Completeness/consistency checks:
  - Section must fully reflect provided inputs
  - No contradiction across sections
- Citation checks:
  - Literature review must include inline citations
  - Other sections follow Stage 2 citation rules

## 6) Iteration and stopping
- Default iteration behavior:
  - Continuous revision cycles (clarify → outline → draft → revise)
- Stop conditions:
  - User explicitly approves output or instructs to stop
- Escalation to “inputs needed”:
  - Triggered when required inputs are missing and block further grounded drafting

## 7) Claim taxonomy
- grounded_fact
- inference
- assumption
- tbd_placeholder

## 8) Operating rule
- Never present assumptions as facts
