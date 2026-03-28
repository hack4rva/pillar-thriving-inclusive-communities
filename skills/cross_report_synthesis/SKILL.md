> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# cross_report_synthesis

Purpose: Synthesize findings from multiple research reports into a coherent answer while preserving source traceability, acknowledging uncertainty, and flagging tensions specific to the Thriving and Inclusive Communities pillar.

## When To Use
- A user asks a question that spans multiple reports or sections
- A team needs a summary of findings across a problem domain (e.g., "What does the research say about language access barriers?")
- An agent needs to answer: "What does the corpus say about X across all relevant reports?"
- A user asks for a synthesis of risks, opportunities, or data sources
- Any question touching privacy design that requires cross-referencing G section with community_trust_framework.md

## Inputs
- User question or synthesis goal
- List of relevant report files (from `research_corpus_navigation` skill)
- Access to the source `.md` files

## Outputs
- Synthesized answer with per-claim source citations
- Tensions or contradictions noted explicitly
- Confidence level per claim (confirmed, likely, uncertain)
- List of reports read vs. reports not read
- Identified gaps where synthesis is incomplete
- Privacy flag if synthesis touches data collection or resident safety

## Process

### Step 1 — Load Navigation Context

Before synthesizing, confirm you have run `research_corpus_navigation` or equivalent to identify which files are relevant. Do not synthesize from random file selections.

For any synthesis touching privacy or data collection: also confirm you have `03_artifacts/community_trust_framework.md` in the reading list.

### Step 2 — Read Source Files Fully

For each file in the reading list:
1. Read the full `.md` file (not just summaries or frontmatter)
2. Note specific claims, data points, named entities, and source citations
3. Note the confidence level of each claim: does the report cite a primary source, or is it a secondary synthesis?

Do NOT synthesize from index.json summaries alone. Summaries are navigation aids, not authoritative content.

### Step 3 — Build a Claim Map

For each substantive claim you plan to include:

```
Claim: [statement]
Source: [filename, section heading if helpful]
Confidence: confirmed | likely | uncertain
Primary source: [URL or citation if available in the report]
Conflicts with: [other report + how it conflicts, if applicable]
Privacy implication: [NONE | describe if claim affects data or resident safety]
```

### Step 4 — Identify Tensions and Gaps

Before writing the synthesis, explicitly check:
- Do any reports contradict each other? (If so, note both positions and their sources)
- Are there claims that appear in one report but are absent from others where you would expect them?
- Are there questions that the reports together still do not answer?
- Does the `evidence_log.md` Missing section list any gap directly relevant to this synthesis?

Flag gaps with: `[Gap: no report in this corpus addresses X]`
Flag missing data with: `[Missing per evidence_log.md: E-M00X]`

### Step 5 — Write the Synthesis

Structure:
1. **Scope**: which files were read, which were not
2. **Main findings**: 3–7 bullet points with inline citations
3. **Tensions**: any conflicting information and its sources
4. **Gaps**: what the corpus does not cover
5. **Privacy notes**: any privacy implications from the synthesis (if applicable)
6. **Confidence summary**: overall confidence in the synthesis

### Citation Format

Use inline citations:
- `(per research/A1_problem_landscape_immigrant_service_access.md)`
- `(per evidence_log.md, E-M001)`
- `[Unverified: not found in files read]`
- `[Uncertain: mentioned in summary but not verified in source]`
- `[Missing per evidence_log.md: cross-agency referral dataset not available]`

Never blend claims from different sources into a single uncited sentence.

### Step 6 — State What Was NOT Read

Always end the synthesis with:

```
Files read for this synthesis:
  - research/[FILE].md
  - research/[FILE].md

Files not read (possibly relevant):
  - research/[FILE].md — reason it may contain relevant information
```

This allows the user or a future agent to know the synthesis is incomplete if additional files exist.

## Anti-Patterns to Avoid

- **Never** synthesize from index.json summaries alone
- **Never** blend claims from different reports without attribution
- **Never** omit tensions or contradictions to make the answer cleaner
- **Never** claim the synthesis is complete if relevant unread files exist
- **Never** invent figures or statistics not present in the source files
- **Never** suggest a data source exists if evidence_log.md documents it as missing
- **Never** synthesize privacy guidance without including community_trust_framework.md

## Pillar-Specific Synthesis Rules

This pillar has additional synthesis requirements due to the vulnerability of the populations served:

1. **Trust before access**: Any synthesis about what will improve service uptake must acknowledge the trust-first framing from A1, A4, and 00_pillar_summary_context.md. Separating information access from trust is a known failure mode.

2. **D3=1 is a hard constraint**: Any synthesis about cross-agency navigation must acknowledge the data readiness constraint documented in A2 and D5. Do not synthesize as if live cross-agency data is available.

3. **Privacy is not a post-build concern**: When synthesizing opportunity or MVP guidance, always fold in G section risks. Privacy design is a prerequisite, not a feature.

4. **Check evidence_log.md Missing section first**: Before synthesizing what data is available, confirm against the Missing section. Five key data gaps are documented (E-M001 through E-M005).

## Example Output Structure

```
**Synthesis: What Data Is Available for a Service Discovery Prototype?**

Files read: D1, D2, D3, C1, evidence_log.md
Files not read (possibly relevant): D4 (refugee resettlement data), D5 (data quality gaps)

**Main Findings**
1. Help1RVA has no public API or bulk data export; a manual extraction of 20–30 curated services is the recommended path (per research/D1_data_help1rva.md; Missing per evidence_log.md E-M001).
2. VirginiaNavigator and IRC Richmond maintain public org directories usable as supplementary sources (per research/D2_data_community_org_directories.md).
3. Census data via ACS identifies 6,537 LEP Spanish speakers in Richmond as a key target population (per research/D3_data_census_immigrants.md).
4. All data collection from users must default to zero-PII (per 03_artifacts/community_trust_framework.md).

**Tensions**
- D1 documents Help1RVA as the primary local directory, but C1 notes its language support is limited to English in most program listings [Uncertain — multilingual coverage not fully assessed].

**Gaps**
- [Gap: D4 and D5 not yet read; refugee resettlement data availability and data quality assessment incomplete]
- [Missing per evidence_log.md E-M001: no bulk Help1RVA export available]

**Privacy notes**: Any service dataset must not include intake or eligibility information without explicit consent design reviewed against community_trust_framework.md.

**Confidence: Moderate** — main data availability findings confirmed; D4 and D5 unread.
```
