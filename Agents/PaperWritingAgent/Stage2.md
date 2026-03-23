# Stage 2 Grounding Pack v0.2
approved: false

## 1) Allowed sources
- User-provided documents/files/data: allowed
- User-provided templates/examples/policies: allowed
- Approved paper list metadata/titles/abstracts: allowed
- External scholarly sources: allowed
- Journal guidance / author instructions: allowed
- Source-scope rule:
  - User-provided research inputs remain primary for study-specific claims
  - External scholarly sources may be used for literature synthesis, framing, and disciplinary context
  - Journal author guidelines may be used for structure, formatting expectations, and section logic
- Restrictions:
  - External sources must not be used to invent study-specific results, methods actually not provided, dataset contents not supplied, or unsupported interpretations
  - Where user-provided inputs conflict with external general sources, study-specific user inputs take precedence for manuscript content unless explicitly flagged as a conflict

## 2) Tools / APIs
- File reading: allowed
- Web browsing for scholarly/source verification: allowed
- Write tools for artifacts: allowed when explicitly requested
- Default tool posture:
  - Read allowed for inspection and synthesis
  - Write denied by default unless the user asks for artifact generation
- Constraints:
  - No source may be treated as authoritative beyond approved scope
  - External browsing should prioritize scholarly and journal-primary sources
  - Failure mode for missing grounding: mark TBD / open question / assumption
  - If a source cannot be verified or accessed, its use must be limited or explicitly flagged

## 3) Citation / provenance policy
- Citation required when:
  - Inline citations are required in the literature review section
  - Citations outside the literature review are optional unless the user later requests broader citation coverage
- Citation granularity:
  - Sentence-level or claim-cluster-level inline citation in the literature review
- Citation style:
  - Inline scholarly citation style, adapted to the target manuscript convention when specified
  - If no style is specified, use a neutral placeholder citation form compatible with later formatting
- Retrieval date/time needed:
  - Required for web-retrieved journal guidance or external source verification notes when relevant
  - Not required inside manuscript prose unless requested
- Provenance labeling:
  - grounded_fact
  - inference
  - assumption
  - tbd_placeholder

## 4) Grounding behavior rules
- Literature review:
  - May use approved paper list metadata/titles/abstracts and external scholarly sources
  - Must include inline citations
  - Must distinguish sourced synthesis from inference
- Introduction / framing:
  - May use external scholarly sources and journal guidance
  - Citations optional unless requested
- Materials and Methods:
  - Must rely primarily on user-provided methods, datasets, study-area inputs, and diagrams/flowcharts
  - Missing procedural details must be marked as assumptions or TBDs
- Results:
  - Must rely only on user-provided findings and approved study inputs
  - No external source may be used to fabricate or extend results
- Discussion:
  - May compare user-provided findings against external scholarly sources where allowed
  - Any interpretive extension beyond supplied evidence must be labeled as inference or assumption
- Conclusions:
  - Must be derived from user-provided findings and discussion content, not invented from external sources

## 5) Failure modes and safeguards
- Missing source detail:
  - Convert to TBD or open question
- Conflicting sources:
  - Flag explicitly and note source precedence
- Ambiguous citation data:
  - Use placeholder citation markers and list missing bibliographic fields
- Insufficient evidence for a claim:
  - Do not state as fact; recast as assumption, inference, or remove
