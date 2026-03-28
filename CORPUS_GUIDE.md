> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](docs/methodology.md) for details.

# Research Corpus Guide

**Thriving and Inclusive Communities Pillar — Richmond Civic Hackathon**

This file is the canonical orientation document for both human readers and AI agents using this research corpus. Read it before diving into individual reports.

---

## What This Corpus Is

This repository contains a structured research corpus on Richmond's immigrant service access, community trust, language inclusion, and cross-agency navigation problem space, organized to support a weekend civic hackathon. It includes:

- **51 deep research reports** generated via Parallel.ai (in `research/`)
- **Evidence-synthesized artifacts** (in `03_artifacts/`)
- **Data source inventory** (in `02_data/`)
- **Build and demo guides** (in `04_build_guides/`)
- **Skills** — executable procedural guides for AI agents (in `skills/`)
- **Templates** — team and project scaffolding (in `99_templates/`)

The corpus is grounded in publicly verifiable claims about Richmond's immigrant and refugee service ecosystem. It does not contain invented data, unverified program descriptions, or fabricated citations.

**Privacy note:** This pillar has unusually high stakes for privacy. The populations served include people with legitimate fear of identification and data exposure. Every claim about what data exists or what a tool collects must be traceable to a source file. Never assume data is safe to collect.

---

## Canonical Source of Truth

| Priority | File | What It Contains |
|----------|------|-----------------|
| 1 (highest) | `research/[SECTION][N]_*.md` | Primary research reports — authoritative content |
| 2 | `evidence_log.md` | Verified claims and known information gaps |
| 3 | `03_artifacts/research_notes.md` | Promoted findings from verified evidence |
| 4 | `03_artifacts/community_trust_framework.md` | Privacy and trust design requirements |
| 5 (lowest) | Index and manifest files | Navigation aids — not authoritative for claims |

**Rule:** Navigation aids (README, index.json, manifest.json, CORPUS_GUIDE.md) reduce search scope. They are not substitutes for reading original reports. Before making substantive claims, read the source report.

---

## How the Corpus Is Organized

### Top-Level Directories

```
research/         ← 51 deep research files (the core corpus)
03_artifacts/     ← synthesized artifacts (trust framework, user journeys, prototype recs)
02_data/          ← data source inventory and index
04_build_guides/  ← MVP shapes, architectures, demo advice
00_core/          ← pillar overview and MAP alignment
01_problem_space/ ← problem statements (scored)
skills/           ← agent skill definitions
99_templates/     ← team and project templates
evidence_log.md   ← root-level verified claims and gaps tracker
```

### Research Section Structure

The `research/` directory is organized into labeled sections:

| Section | Topic | Files |
|---------|-------|-------|
| `00` | Context & Framing | 1 file |
| `01` | Master Research Framework | 1 file |
| `90–93` | Cross-Cutting Analysis | 4 files |
| `A` | Problem Landscape | A1–A5 |
| `B` | Users & Stakeholders | B1–B5 |
| `C` | Services & Programs | C1–C5 |
| `D` | Data Sources | D1–D5 |
| `E` | Prior Art & Benchmarks | E1–E5 |
| `F` | Opportunities | F1–F5 |
| `G` | Risks & Guardrails | G1–G5 |
| `H` | MVP Feasibility | H1–H5 |
| `I` | Demo Guidance | I1–I5 |

---

## How to Navigate the Corpus

### Start With Navigation Artifacts (Always)

**Before reading any research report, use navigation files to narrow scope:**

1. **`manifest.json`** (root) — machine-readable index of all significant files with summaries and tags
2. **`research/index.json`** — structured metadata for all 51 research files (id, section, title, summary, key_terms)
3. **`research/INDEX.md`** — human-readable table of contents for the research directory
4. **`README.md`** (root) — decision phases and overall repo map

### Navigation Decision Tree

```
User question received
        ↓
Is it about the hackathon process?
  YES → README.md, QUICKSTART.md, 04_build_guides/
  NO ↓
Is it about a specific problem domain?
  Immigrant service access/trust → research/A1, A4, B1, C1, F2, H2
  Cross-agency navigation → research/A2, D5, F3, H3
  Language access → research/A5, B5, G3, H4
  Both problem statements → read 00_pillar_summary_context first
        ↓
Narrow to section using research/index.json
        ↓
Read original .md files for claims
        ↓
Check evidence_log.md for verified/missing status of specific facts
        ↓
Check 03_artifacts/community_trust_framework.md before any privacy claim
```

### Question-to-Section Mapping

| User Question Type | Start Here |
|-------------------|-----------|
| What problems exist? | `A` section (A1–A5) |
| Who are the users? | `B` section (B1–B5) |
| What services exist already? | `C` section (C1–C5) |
| What data is available? | `D` section (D1–D5), `02_data/` |
| What has been built elsewhere? | `E` section (E1–E5) |
| What should we build? | `F` section (F1–F5) |
| What could go wrong? | `G` section (G1–G5) |
| Is this feasible in a weekend? | `H` section (H1–H5) |
| How do we demo this? | `I` section (I1–I5) |
| What datasets are mentioned? | `D1`, `D2`, `D3`, `02_data/source_inventory.csv` |
| What is the overall picture? | `00_pillar_summary_context.md`, `03_artifacts/research_notes.md` |
| What are the trust/privacy rules? | `03_artifacts/community_trust_framework.md`, `G2`, `G5` |
| What are the known data gaps? | `evidence_log.md` (Missing section), `D5`, `93_missing_information_gaps.md` |
| Immigrant service access specific | A1, A4, B1, C1, C2, D1, F2, H2 |
| Cross-agency navigation specific | A2, D5, F3, G4, H3 |
| Language access specific | A5, B5, E2, G3, H4 |

---

## How to Use the Metadata Files

### `research/index.json`

A JSON array with one entry per research file. Each entry has:
- `id` — file basename (e.g., `A1_problem_landscape_immigrant_service_access`)
- `section` — section label (e.g., `A`, `B`, `cross-cutting`)
- `title` — display title
- `summary` — 1–2 sentence grounded summary
- `key_terms` — 6 relevant terms for keyword search

**Use it to:** find which files are relevant before reading them. Do not answer questions from summaries alone — read the source `.md` file.

### `manifest.json`

A comprehensive machine-readable index of all significant files in the repository. Each entry includes:
- `id`, `path`, `type`, `title`, `summary`
- `pillar`, `tags`, `recommended_audience`
- `read_after` — what to read first
- `source_of_truth` — whether this file is authoritative

**Use it to:** build a retrieval index, understand the full scope of the corpus, or identify which file type to use for a given purpose.

### `evidence_log.md`

Tracks verified factual claims and documented information gaps. Status values: `Verified`, `Likely`, `Unverified`, `Missing`.

**Use it to:** check whether a specific factual claim has been verified. The `Missing` section explicitly lists what is NOT known — consult it before assuming data exists. Do not invent claims that are not in this log.

### `03_artifacts/community_trust_framework.md`

Contains the privacy-by-design requirements and trust framework for this pillar. This file is authoritative for privacy design decisions — it is NOT a navigation aid.

---

## How AI Agents Should Use This Corpus

### Required Behavior

1. **Always read navigation artifacts before raw reports.** Start with `research/index.json` or `manifest.json` to identify relevant files. Do not dive into arbitrary `.md` files without knowing their scope.

2. **Read original reports before making substantive claims.** The summaries in index files are useful for navigation, not for citation. If a question requires a specific fact, find it in the source `.md` file.

3. **Scope before answering.** Identify the relevant section(s) first. A question about immigrant service data belongs to sections `D` and `C`. A question about privacy design belongs to section `G` and `03_artifacts/community_trust_framework.md`.

4. **Acknowledge when files have not been read.** If a report appears relevant but has not been read in the current context, say so rather than guessing from summaries.

5. **Cite the source file.** When presenting findings, reference the file they came from (e.g., "Per `research/A1_problem_landscape_immigrant_service_access.md`...").

6. **Distinguish navigation files from source-of-truth files.** `manifest.json`, `README.md`, `research/INDEX.md`, and `index.json` are navigation aids. They are not authoritative for factual claims.

7. **Mark uncertainty explicitly.** If a claim cannot be verified from the files that have been read, use: `[Unverified]` or `[Requires reading: filename]`.

8. **Always check evidence_log.md for missing data flags.** Before asserting that a dataset or service exists, check the `Missing` section of `evidence_log.md`. Several key datasets are documented as not publicly available.

9. **Apply heightened privacy scrutiny.** This pillar covers tools for vulnerable populations. Before recommending any data collection approach, check `G2`, `G5`, and `03_artifacts/community_trust_framework.md`.

### How to Answer Cross-Report Questions

When a question requires synthesis across multiple reports:
1. Use `research/index.json` to identify all potentially relevant files
2. Read the summaries, then decide which reports need full reading
3. Read the source files
4. Synthesize from source content, citing each report separately
5. Note any tensions or contradictions between reports
6. Do not blend claims from different sections without acknowledging the synthesis

### When to Read Additional Files

You MUST read additional files before answering if:
- The question involves a specific dataset or data format → read D section
- The question involves a specific user persona → read B section
- The question requires a factual claim about Richmond programs → check `evidence_log.md`
- The answer requires citing prior art → read E section
- The question is about risk or guardrails → read G section
- Any claim involves privacy, PII, or data collection → read `G2`, `G5`, and `03_artifacts/community_trust_framework.md`

---

## What This Corpus Does NOT Contain

- Legal advice or immigration status determinations
- Official City positions or policy commitments on immigration
- Private resident or client data of any kind
- Authoritative eligibility guidance (programs change; always encourage users to verify)
- Verified cross-agency referral pathway datasets (documented as missing in evidence_log.md)
- Real-time or current program availability (data may be months old; always verify with source)

When information is absent, say: "This repository does not contain that information." When a gap is documented, say: "This information is listed as missing in `evidence_log.md`."

---

## Recommended Reading Order for Common Scenarios

### New team at hackathon start
1. `README.md` → `QUICKSTART.md` → `00_core/00_pillar_overview.md`
2. `01_problem_space/02_targeted_problem_statements.md`
3. `research/00_pillar_summary_context.md`
4. `04_build_guides/01_mvp_shapes.md`

### Team choosing between Service Discovery and Cross-Agency Navigation
1. `research/A3_problem_landscape_compare_statements.md`
2. `research/F1_opportunities_ranked.md`
3. `research/H1_mvp_48hr_framework.md`
4. `research/D5_data_quality_gaps.md` (if considering cross-agency)

### Team deep-diving on data availability
1. `02_data/00_index.md` and `02_data/source_inventory.csv`
2. `evidence_log.md` (check the Missing section first)
3. `research/D1_data_help1rva.md`
4. `research/D2_data_community_org_directories.md`
5. `research/D3_data_census_immigrants.md`

### Team building a privacy-first prototype
1. `03_artifacts/community_trust_framework.md`
2. `research/G2_risks_pii_exposure.md`
3. `research/G5_risks_guardrails.md`
4. `research/F5_opportunities_do_not_build.md`

### Agent answering research questions
1. `research/index.json` → identify relevant section
2. Narrow to specific files using key_terms search
3. Source `.md` files → read for claims
4. `evidence_log.md` → verify specific facts and check for documented gaps

---

## Source-of-Truth vs. Convenience File Table

| File | Type | Authoritative For | NOT Authoritative For |
|------|------|-------------------|-----------------------|
| `research/[SECTION][N]_*.md` | Source | Primary research claims, cited data | Process, navigation |
| `evidence_log.md` | Evidence tracker | Verified facts, documented gaps | Research synthesis |
| `03_artifacts/community_trust_framework.md` | Synthesized artifact | Privacy design requirements | Raw research claims |
| `03_artifacts/research_notes.md` | Synthesized artifact | Promoted findings | Unverified claims |
| `research/index.json` | Navigation | File discovery, keyword search | Factual claims |
| `manifest.json` | Navigation | Full repo inventory | Factual claims |
| `research/INDEX.md` | Navigation | Human-readable TOC | Factual claims |
| `README.md` | Navigation | Process and repo map | Research content |
| `04_build_guides/*.md` | Build guidance | MVP patterns, demo advice | Research claims |

---

## File Naming Conventions

Research files follow the pattern: `[SECTION][NUMBER]_[TOPIC_SLUG].md`

Examples:
- `A1_problem_landscape_immigrant_service_access.md` — Section A, file 1
- `G5_risks_guardrails.md` — Section G, file 5
- `90_top_10_research_questions.md` — Cross-cutting file 90

Sections run A through I. Numbers within sections run 1–5. Cross-cutting files use 90–93. Context files use 00–01.

---

## See Also

- `AGENTS.md` — Hackbot agent specification and research corpus navigation instructions
- `MAINTENANCE.md` — How to add, update, and synchronize reports and metadata
- `manifest.json` — Machine-readable index of all significant files
- `research/index.json` — Machine-readable index of all research reports
- `03_artifacts/community_trust_framework.md` — Privacy and trust design requirements
