> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# research_corpus_navigation

Purpose: Map a user question to the correct section and specific research reports in the Thriving and Inclusive Communities corpus before attempting to answer.

## When To Use
- A user asks any research question about Richmond's immigrant service access, community trust, or cross-agency navigation
- A user asks about a specific problem domain (service discovery, cross-agency navigation, language access)
- A user asks what reports to read
- An agent needs to determine which files are relevant before answering
- Before making any factual claim that could affect decisions about vulnerable populations

## Inputs
- User question or information need (natural language)

## Outputs
- Identified section(s) from the research corpus
- List of specific files to read (in recommended order)
- Brief explanation of why each file is relevant
- Any files that must be read before answering (prerequisites)
- Privacy flag if the question touches data collection or resident safety

## Process

### Step 1 — Load Navigation Artifacts

Before looking at any research file, load:
1. `research/index.json` — scan all summaries and key_terms
2. If the corpus is unfamiliar: read `CORPUS_GUIDE.md` first

Do NOT skip this step and dive directly into research files.

### Step 2 — Classify the Question

Determine which category the user question falls into:

| Question Category | Relevant Sections |
|------------------|------------------|
| "What problems exist in this space?" | Section A (A1–A5) |
| "Who are the users or stakeholders?" | Section B (B1–B5) |
| "What services or programs exist?" | Section C (C1–C5) |
| "What public data is available?" | Section D (D1–D5), `02_data/` |
| "What has been built elsewhere?" | Section E (E1–E5) |
| "What should we build?" | Section F (F1–F5) |
| "What could go wrong?" | Section G (G1–G5) |
| "Is this feasible for a weekend?" | Section H (H1–H5) |
| "How should we demo this?" | Section I (I1–I5) |
| "What is the overall picture?" | `00_pillar_summary_context.md`, `03_artifacts/research_notes.md` |
| "What datasets or APIs are mentioned?" | D1, D2, D3, `02_data/source_inventory.csv` |
| "What are known data gaps?" | `evidence_log.md` Missing section, D5, 93 |
| "Immigrant service discovery specific" | A1, A4, B1, C1, D1, F2, H2 |
| "Cross-agency navigation specific" | A2, D5, F3, G4, H3 |
| "Language access specific" | A5, B5, E2, G3, H4 |
| "Privacy or data safety" | G2, G5, `03_artifacts/community_trust_framework.md` |
| "What NOT to build" | F5, G1, G2, `92_red_flags.md` |

### Step 3 — Search `research/index.json`

Scan the `key_terms` and `summary` fields for matches to the user's question. Identify:
- High-confidence matches (3+ matching key_terms)
- Medium-confidence matches (1–2 matching key_terms)
- Files worth reading despite no term match (based on section relevance)

### Step 4 — Build a Reading List

Order files by:
1. Direct relevance to the question
2. Section order (earlier sections provide context for later ones)
3. Files mentioned in `CORPUS_GUIDE.md` recommended reading orders

Limit the initial reading list to 5 files maximum. If more are needed after reading, say so.

### Step 5 — Identify Prerequisites

Some questions require reading prerequisite files:
- Any question requiring context about Richmond → read `00_pillar_summary_context.md` first
- Any question about services → read C1 before C2–C5
- Any question about data → read D1 before D2–D5
- Any question requiring problem framing → read A1 or A2 before F or H sections
- Any question about privacy/data collection → read `03_artifacts/community_trust_framework.md` AND check `evidence_log.md` Missing section

Flag prerequisites explicitly. Flag privacy-sensitive questions with: **[PRIVACY FLAG: consult G2, G5, and community_trust_framework.md before answering]**

### Step 6 — Output the Navigation Result

Return:
```
Relevant section(s): [X, Y]
Files to read (in order):
  1. research/[FILE].md — [one-sentence reason why]
  2. research/[FILE].md — [one-sentence reason why]
  3. ...

Prerequisites (read these first if not yet read):
  - research/[FILE].md — [reason]

Files to skip (and why):
  - [Section] — not relevant because [reason]

Privacy flag: [NONE | HIGH — see G2, G5, community_trust_framework.md]
```

### Step 7 — Confirm Scope Boundaries

After delivering the reading list, state:
- What sections were NOT included and why (to confirm nothing was missed)
- Whether cross-report synthesis will be needed
- Whether any answer requires verified facts from `evidence_log.md`
- Whether any answer touches documented missing data (Missing section of evidence_log.md)

## Section Quick Reference

| Section | Topic | Primary Use Case |
|---------|-------|-----------------|
| `00` | Context & Framing | Pillar overview, all orientations |
| `01` | Master Research | Comprehensive evidence base |
| `90–93` | Cross-Cutting | Quick synthesis, red flags, gaps |
| `A` | Problem Landscape | Problem selection, framing |
| `B` | Users & Stakeholders | Persona definition, user needs |
| `C` | Services & Programs | What exists, fragmentation |
| `D` | Data Sources | Dataset availability, API access |
| `E` | Prior Art | Comparable tools, reusable patterns |
| `F` | Opportunities | What to build, ranked options |
| `G` | Risks & Guardrails | Privacy, harm, failure modes |
| `H` | MVP Feasibility | 48-hour viability, scope limits |
| `I` | Demo Guidance | Pitch strategy, credibility |

## Example

**Question:** "What data can we use to build a service finder for immigrant residents?"

**Navigation result:**
```
Relevant sections: D (Data Sources), C (Services)

Files to read (in order):
  1. research/D1_data_help1rva.md — primary source on Help1RVA data access and constraints
  2. research/D2_data_community_org_directories.md — alternative org directory sources
  3. research/C1_services_help1rva.md — what Help1RVA contains and its limitations
  4. 02_data/source_inventory.csv — verified data source list

Prerequisites: read 00_pillar_summary_context.md if not already read for context
PRIVACY FLAG: HIGH — consult G2, G5, community_trust_framework.md before designing data collection

Files to skip: A, B, E, F, G, H, I — not directly relevant to data availability question

Verified gaps to check: evidence_log.md Missing section (E-M001 documents no Help1RVA bulk export)
```
