> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# evidence_grounded_answering

Purpose: Answer user questions using only content actually present in this repository corpus, with explicit grounding and uncertainty marking. Apply heightened scrutiny for claims that could affect vulnerable populations.

## When To Use
- Any time a factual claim about Richmond programs, data, or services is being made
- When a user asks: "Does X exist?" "Is Y available?" "What does City do about Z?"
- When an agent is about to state something it cannot directly verify from files it has read
- Before asserting that a dataset, program, service, or policy exists
- Before making any claim about privacy safety, data collection practices, or eligibility
- Before asserting that an immigrant or refugee service is available or accessible

## Inputs
- User question
- Files read in current context
- Optional: `evidence_log.md` for verified claims and documented gaps

## Outputs
- Answer grounded in specific file content
- Inline citations for each substantive claim
- Explicit uncertainty markers for unverified statements
- "Not found" statements when information is absent
- Privacy flag if the answer involves data collection or resident-facing information

## Process

### Step 1 — Establish What Has Been Read

Before answering, state (internally or explicitly) which files have been read. Only make claims from those files. Do not interpolate from general knowledge.

### Step 2 — Classify Each Claim

For every substantive claim in your answer, classify it:

| Status | Meaning | Marker |
|--------|---------|--------|
| `Confirmed` | Present in a source file AND verified in `evidence_log.md` | No marker; cite source |
| `Stated in corpus` | Present in a research file but not independently verified | `(per [filename])` |
| `Uncertain` | Implied or summarized but not directly stated in a file read | `[Uncertain: implied by X but not stated directly]` |
| `Not found` | Not present in any file read | `[Not found in files read]` |
| `Requires reading` | Likely in a specific file that has not been read | `[Requires reading: filename]` |
| `Missing (documented)` | Explicitly documented as unavailable in evidence_log.md | `[Missing per evidence_log.md E-M00X]` |

### Step 3 — Check the Evidence Log

For claims about:
- Specific service directories (Help1RVA, VirginiaNavigator) and their capabilities
- Data availability (what datasets exist and in what format)
- Program availability and eligibility requirements
- Cross-agency referral pathways or intake datasets
- Communication channels used by immigrant residents

Cross-check `evidence_log.md`. The `Missing` section lists five explicitly documented gaps (E-M001 through E-M005). If a claim relates to one of these, you MUST apply the `Missing (documented)` marker.

### Step 4 — Apply the Privacy Scrutiny Check

Before finalizing any answer touching data or services for vulnerable populations:

1. Does the answer imply any data should be collected from immigrant/refugee residents? → Check G2, G5, community_trust_framework.md
2. Does the answer suggest a tool could determine eligibility? → Flag with `[PRIVACY RISK: eligibility determination is out of scope per F5 and community_trust_framework.md]`
3. Does the answer involve immigration status, health data, or household composition? → Flag with `[HIGH SENSITIVITY: do not collect or display]`

### Step 5 — Formulate the Answer

Structure:
1. Direct answer to the question
2. Supporting evidence with citations
3. Explicit uncertainty statements
4. Privacy flag if applicable
5. What is NOT covered (to set expectations)

### Step 6 — Apply the Anti-Fabrication Check

Before finalizing the answer, run this check:

- Does every named government program actually appear in a file I have read?
- Does every dataset I mentioned actually appear in D section files or `02_data/`?
- Does every service I described actually appear in a C section file or verified source?
- Am I inventing specificity (exact percentages, exact dates) not present in the source?
- Have I checked the evidence_log.md Missing section for claimed-but-unavailable data?

If any check fails → remove or mark the claim as `[Unverified]`.

### Step 7 — State Scope Limits

At the end of the answer, state:
- What files were used to answer this question
- What topics the answer does NOT cover because relevant files were not read

## Required Language

When information is absent, use:
- "This repository does not contain that information."
- "I cannot verify that from the files I have read in this session."
- "That would require reading [specific file] which I have not yet loaded."
- "[Unverified]: this appears in a summary but I have not read the source file."
- "[Missing per evidence_log.md]: this data is documented as not publicly available."

Do NOT use:
- "Likely..." (without a citation)
- "Generally..." (as a hedge for an ungrounded claim)
- "It is common for cities to..." (implies external knowledge not in corpus)
- "I believe..." (implies opinion substituting for evidence)
- "The data should be available..." (unless a source confirms it)
- "This tool would be safe to use..." (without citing G2, G5, or community_trust_framework.md)

## Pillar-Specific Anti-Fabrication Rules

The Thriving and Inclusive Communities pillar has additional fabrication risks because:
1. Trust claims are high-stakes: stating a service is "trusted" or "safe" requires evidence
2. Eligibility claims can harm users: overstating program access for undocumented residents is dangerous
3. Data availability is constrained: five documented missing datasets (E-M001 through E-M005)
4. Language coverage is uneven: do not assume Spanish translation covers all LEP residents

Never state:
- That a specific service will accept a resident without documentation — unless a source file confirms this
- That a dataset exists in bulk or API form — unless confirmed (Help1RVA has no public API per D1)
- That a cross-agency referral pathway dataset exists — it is documented as missing (E-M002)
- That a tool can determine eligibility — eligibility determination is explicitly out of scope (F5)

## Example

**Question:** "Is there a way to get the Help1RVA service data as an API?"

**Grounded answer:**

No. Help1RVA has no publicly documented API or bulk data export function (per `research/D1_data_help1rva.md`; documented as missing in `evidence_log.md` E-M001). Help1RVA operates as a white-labeled instance of the findhelp platform, which controls API access and prohibits scraping under its Terms of Service (per `research/D1_data_help1rva.md`).

The recommended path for a hackathon prototype is a targeted manual extraction of 20–30 curated services in the Citizenship & Immigration, Translation & Interpretation, and ESL categories, which can be completed in 2–3 hours (per `research/D1_data_help1rva.md`).

[Requires reading: `research/C5_services_findhelp_uniteus.md` for a fuller assessment of what the findhelp/Unite Us platform stack makes available.]

*Files read for this answer: D1, evidence_log.md*
*Not covered: D2 (alternative directories), C5 (FindHelp/Unite Us stack), D5 (data quality)*

## Anti-Patterns

- Never state a City program exists without a source file citation
- Never quote a statistic (percentage, resident count, service count) without a source
- Never say "Help1RVA supports X" based only on index.json summaries — read D1 or C1
- Never blend confirmed and uncertain claims in the same sentence without differentiation
- Never omit the evidence_log.md Missing section check when answering about data availability
