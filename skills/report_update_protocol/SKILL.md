> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# report_update_protocol

Purpose: Safely add or update research reports and keep all metadata, indexes, and navigation files synchronized for the Thriving and Inclusive Communities corpus.

## When To Use
- Adding a new research report to the corpus
- Updating an existing report with new findings
- Correcting a factual error in a report
- Moving or renaming a file
- Adding a new section to the research corpus
- Updating evidence_log.md with newly verified claims or documented gaps

## Inputs
- New or updated content to add
- Target location (section and filename)
- Any source citations or evidence to track
- Privacy sensitivity assessment if applicable

## Outputs
- Updated or new `.md` file with proper structure and frontmatter
- Updated `research/index.json` entry
- Updated `research/INDEX.md` row
- Updated `manifest.json` entry
- Optionally: updated `evidence_log.md` if new verified claims or missing data confirmed

## Process

### Step 1 — Locate or Name the File

For a **new report:**
1. Determine the correct section (A–I, or cross-cutting 94–98 for new entries; 90–93 already used)
2. Choose the next available number in the section
3. Create the filename: `[SECTION][NUMBER]_[topic_slug].md`
4. Confirm no file with that name already exists in `research/`

For an **existing report:**
1. Find the file in `research/`
2. Confirm it is the correct file (verify the H1 heading matches)
3. Note its current entry in `research/index.json` for comparison

### Step 2 — Prepare the File Content

Every report must:
- Begin with a clear H1 heading (the full report title)
- Contain only grounded claims (no invented data)
- Cite sources where possible (reference numbers from research tools are acceptable; include URLs if available)
- Avoid any assertion about data availability not verified against evidence_log.md

Recommended frontmatter (add if not present):

```yaml
---
title: "Full Report Title"
pillar: thriving-inclusive-communities
section: A
problem_statement: immigrant-service-access | cross-agency-navigation | general
tags:
  - [tag1]
  - [tag2]
summary: "1–2 sentence grounded summary of content."
geography: Richmond, VA
source: parallel-ai | perplexity-sonar-deep-research | manual | other
status: raw | reviewed | verified
related_reports:
  - A1_problem_landscape_immigrant_service_access
---
```

Only add fields you can fill accurately. Do not fabricate.

**Privacy note:** If the report contains claims about data collection, PII handling, or immigrant-resident safety, add:
```yaml
privacy_sensitivity: high
```

### Step 3 — Update `research/index.json`

Locate the file's entry (or create a new one):

```json
{
  "id": "SECTION_NUMBER_topic_slug",
  "section": "SECTION_LETTER_OR_LABEL",
  "title": "Human-Readable Title",
  "summary": "Accurate 1–2 sentence grounded summary from the actual content.",
  "key_terms": ["term1", "term2", "term3", "term4", "term5", "term6"]
}
```

Rules:
- `id` must match the filename (without `.md`) exactly
- `summary` must reflect the actual content, not an invented description
- `key_terms` should be terms a researcher would search for to find this file
- For new files, insert in the correct section order (not appended to end)
- Validate after editing: `python3 -m json.tool research/index.json`

### Step 4 — Update `research/INDEX.md`

Add a row to the correct section in `research/INDEX.md`:

```markdown
- [`SECTION_N_topic_slug.md`](SECTION_N_topic_slug.md) — Brief description
```

For updated files, check whether the existing description still accurately represents the content.

### Step 5 — Update `manifest.json`

Add or update the entry in the root manifest:

```json
{
  "id": "research/SECTION_N_topic_slug",
  "path": "research/SECTION_N_topic_slug.md",
  "type": "research_report",
  "title": "Human-Readable Title",
  "pillar": "thriving-inclusive-communities",
  "section": "SECTION_LETTER",
  "summary": "Accurate 1–2 sentence summary.",
  "tags": ["tag1", "tag2", "tag3"],
  "recommended_audience": ["describe who should read this and why"],
  "read_after": ["research/prerequisite_file.md"],
  "source_of_truth": true
}
```

Validate after editing: `python3 -m json.tool manifest.json`

### Step 6 — Update `evidence_log.md` (If Applicable)

If the report contains a newly verified factual claim (a claim with an official source URL), add a new entry under `## Confirmed`:
```
- E-001: [claim description] | Source: [URL] | Accessed: [date] | Status: Verified
```

If the report documents a data gap or confirms something is not publicly available, add to `## Missing`:
```
- E-M006: [description of missing data] — not publicly available per [source]
```

If the report corrects a previously confirmed claim, update the existing entry with a `[CORRECTED]` note rather than deleting it.

### Step 7 — Run the Validation Check

Before committing:

```
[ ] File exists at expected path in research/
[ ] H1 heading is accurate and matches frontmatter title (if frontmatter present)
[ ] Frontmatter fields are grounded (no fabricated values)
[ ] research/index.json entry is accurate and valid JSON
[ ] research/INDEX.md row is present and accurate
[ ] manifest.json entry is present and valid JSON
[ ] Both JSON files pass: python3 -m json.tool [file]
[ ] evidence_log.md updated if new verified claims or documented gaps added
[ ] Privacy-sensitive content flagged and reviewed against community_trust_framework.md
[ ] No broken internal links created
```

### Special Case: Renaming a File

Renaming an existing file requires updating all references. Check all of:
- `research/index.json` (`id` field)
- `manifest.json` (`id` and `path` fields)
- `research/INDEX.md` (link text and href)
- Any `related_reports` fields in other files' frontmatter
- `AGENTS.md` (if file is named there)
- `CORPUS_GUIDE.md` (if file is specifically referenced)
- `MAINTENANCE.md` (if file is specifically referenced)

Avoid renaming unless necessary.

### Special Case: Removing a File

Before removing, check:
1. Is the file referenced in any navigation artifacts?
2. Is the file's content covered by another file?
3. Would removing it create a gap that agents would encounter?

Prefer deprecating over deleting: add a note to the file and its index entry rather than removing it outright. Deprecation format: add `status: deprecated` to frontmatter and note the replacement file.

## Pillar-Specific Guidance

When adding reports to the Thriving and Inclusive Communities corpus:

1. **Check A section context first**: New problem landscape reports should cross-reference A1 (immigrant service access) or A2 (cross-agency navigation) as related_reports.

2. **D section reports must note API/export availability explicitly**: Given the known constraint that Help1RVA has no public API (E-M001), any data report should explicitly state what access methods are available.

3. **G section reports require community_trust_framework.md alignment**: New risk reports should be cross-referenced against 03_artifacts/community_trust_framework.md to ensure consistency.

4. **evidence_log.md Missing section is authoritative**: If a new report discovers or confirms a data gap, update the Missing section immediately — this is the first place agents check before assuming data exists.
