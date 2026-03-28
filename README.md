<div align="center">

# Thriving and Inclusive Communities — Decision Funnel

Richmond Civic Hackathon • March 27–29, 2026

[![Pillar](https://img.shields.io/badge/Pillar-Thriving_%26_Inclusive_Communities-4c68d7)](#)
[![Stage](https://img.shields.io/badge/Stage-Decision_Funnel-00a38f)](#)
[![Focus](https://img.shields.io/badge/Focus-From_Idea_%E2%86%92_MVP-ff7a59)](#)

</div>

This is a guided decision environment for teams working on the Thriving and Inclusive Communities pillar. It's designed to help you quickly choose a credible, source-linked, weekend-buildable MVP — and avoid tools that could harm the communities they're meant to serve.

Journey stages: Land → Orient → Choose → Research → Compare MVPs → Lock Scope → Build → Validate → Demo → Hand-off

Three questions to answer fast: 1) What problem are we actually solving? 2) Can we credibly demo by Sunday? 3) What privacy risks are we introducing, and how do we mitigate them?

---

## The Challenge

**→ Full detail in [`CHALLENGE.md`](CHALLENGE.md).** Read it before anything else — it defines the two problems, the top blue sky vision, data constraints, how Pillar Award weights use the shared rubric, and optional per-problem prompts to help your team think about the categories (not a second judge rubric).

### Problem 1: Help Residents Safely Discover and Connect to Trusted Support Services — 24/32 — Strong ★ Recommended starting point

> How might we help immigrant and refugee residents in Richmond safely discover and connect to trusted support services despite privacy concerns, language barriers, and uncertainty about which organizations to trust?

Build toward: Privacy-first service finder (no login, no PII) · Multilingual resource tool (Spanish, Arabic, Dari, Pashto, Portuguese — confirmed) · Trusted community messenger via Facebook groups and WhatsApp (confirmed channels) · Help1RVA or 211 Virginia API interface improvement with multilingual support

⚠ Must never require account creation or personal information. Must work through channels residents actually use — not just a web app. Privacy is not a feature here; it is the baseline.

---

### Problem 2: Helping Residents Navigate Support Services Without Repeating Their Story — 22/32 — Needs work

> How might we help residents seeking housing, workforce, or reentry services navigate across multiple agencies without having to repeat their story to every provider?

Build toward: Service pathway visualization (staff-facing, built from public info) · Staff coordination helper · Eligibility navigator (no PII) · Cross-agency pathway explainer for staff and residents

🚨 **D3=1 — no cross-agency dataset exists.** All personal resident data, internal agency data, and HIPAA-covered data are out of scope. Demo will be conceptual for cross-agency elements. Build around this constraint, not through it.

---

### Top Blue Sky: Universal Access to City Services — 21/27 — Strong

> Every City service has a multilingual, plain-language front door that works on a phone, requires no digital literacy, and meets residents where they are.

Build the multilingual access layer: service finder in 2–4 languages, designed for low digital literacy, distributable via QR code and SMS. Problem 1 is the practical floor; this vision is the ceiling.

---

### Pillar Award Rubric

| Category | Weight | Dominant question |
|----------|--------|-------------------|
| **Impact** | **5** | Does this directly address one of the two problems above? |
| User Value | 4 | Does the prototype meaningfully improve a resident's ability to find or access services? |
| Feasibility | 3 | Could this be piloted by Help1RVA, a nonprofit, or a City partner within a year? |
| Innovation | 3 | Fresh thinking on service discovery, navigation, or trust-building? |
| Execution | 3 | Does a working demo exist? Is the flow coherent? |
| Equity | 3 | Does it prioritize the safety and dignity of vulnerable community members? Does it work in multiple languages? |

Official rubric — category definitions, scoring anchors, and judge-facing guidance: [`../RUBRIC.md`](../RUBRIC.md)

---

## Table of Contents

0. [The Challenge](#the-challenge)
1. Quick Start
2. Repo Map
3. Guardrails
4. Decision Phases
   - Phase 0: Landing & Framing
   - Phase 1: Rapid Orientation
   - Phase 2: Problem Selection
   - Phase 3: Research Spin-Up
   - Phase 4: Opportunity Framing
   - Phase 5: Scope Lock
   - Phases 6–9: Build → Validate → Demo
5. Verification Workflow
6. Hackbot Helper
7. Appendix: Pillar Context & Rubric

---

## Quick Start

Do these first 15–30 minutes to get moving:

1) Read: `CHALLENGE.md` — the two problems, top blue sky, Pillar Award weights, and optional per-problem rubric prompts (start here, not QUICKSTART.md)
2) Read: `QUICKSTART.md`
2) Skim: `00_core/00_pillar_overview.md` and `01_problem_space/02_targeted_problem_statements.md`
3) Capture a 5-bullet "Working Direction" using `99_templates/working_direction_note.md`
4) Decide your path:
   - Path A — already have a rough problem: jump to Phase 2 and Phase 4
   - Path B — need help choosing: start at Phase 1 and proceed in order

---

## Repo Map

| Directory / File | Purpose |
|-----------------|---------|
| `research/` | 51 deep research reports — the primary corpus (read `research/INDEX.md` first) |
| `research_notes.md` | Research hub and promoted findings |
| `evidence_log.md` | Verified claims and documented information gaps |
| `02_data/` | Data source index and inventory CSV |
| `03_artifacts/` | Synthesized artifacts (user journeys, prototype recs, trust framework) |
| `04_build_guides/` | MVP shapes, architectures, demo advice |
| `05_prompts/` | Research prompts and runners |
| `99_templates/` | Team and project templates |
| `skills/` | Hackbot skill definitions |

### Navigation files

| File | Purpose |
|------|---------|
| `CORPUS_GUIDE.md` | Canonical orientation for the research corpus — read before diving into reports |
| `manifest.json` | Machine-readable index of all significant files with summaries and tags |
| `research/index.json` | Machine-readable index of all 51 research reports with key_terms |
| `research/INDEX.md` | Human-readable table of contents for the research directory |
| `MAINTENANCE.md` | How to add, update, and synchronize reports and metadata |

---

## Guardrails

- Pick one user, one workflow, and one credible data/doc base.
- Avoid eligibility/legal determinations and policy/integration dependencies.
- Always cite official sources. Log every claim in `evidence_log.md`.
- Keep AI constrained to explanation, retrieval, comparison, and guidance.
- **Never collect PII, immigration status, or health data from vulnerable residents.**
- **Privacy-by-design is not optional — it is the baseline for this pillar.**

---

## Decision Phases

<details open>
<summary><strong>Phase 0 — Landing & Framing</strong></summary>

Goal: understand what this repo is and how to use it without "exploring" for two hours.

What this pillar is about:
- Immigrant and refugee service access; trust-based community connection; cross-agency navigation; language and accessibility inclusion under Thriving and Inclusive Communities.

Success patterns:
- Source-linked, narrow scope, credible demo, explicit privacy limits, no PII collection.

Anti-patterns:
- Platform claims; eligibility/legal decisions; PII collection; immigration status exposure; replacing human trust relationships.

Admin quick links:
- Research hub: `research_notes.md`
- Evidence tracker: `evidence_log.md`
- Source inventory (CSV): `02_data/source_inventory.csv`
- Privacy framework: `03_artifacts/community_trust_framework.md`

Call to action: choose Path A or Path B.

</details>

<details open>
<summary><strong>Phase 1 — Rapid Orientation (20–30 min)</strong></summary>

Read just enough to build a shared mental model:
- `QUICKSTART.md`
- `00_core/00_pillar_overview.md`
- `00_core/01_map_alignment.md`
- `01_problem_space/02_targeted_problem_statements.md`
- `03_artifacts/community_trust_framework.md`

Filter for:
- user groups; pain points; what the City actually cares about
- problems that are software-shaped vs policy-shaped
- privacy risks that would disqualify an approach

Team checkpoint — Working Direction (use `99_templates/working_direction_note.md`):

```
## Working Direction
- Pillar: Thriving and Inclusive Communities
- Candidate problem:
- Likely user:
- Why it matters:
- Why it seems weekend-buildable:
- Biggest uncertainty:
- Key privacy risk:
```

</details>

<details>
<summary><strong>Phase 2 — Problem Selection (30–45 min)</strong></summary>

Files:
- `01_problem_space/01_bluesky_problem_statements.md`
- `01_problem_space/02_targeted_problem_statements.md`
- `00_core/04_solution_patterns.md`
- `05_prompts/01_problem_selection_prompt.md`

Decision rule — choose only if the problem has:
- a real user and understandable workflow
- a plausible public data/document base
- a demoable artifact by Sunday
- an acceptable privacy risk profile

Output: Decision Memo (`99_templates/decision_memo.md`)

```
## Chosen Problem
## User
## Why this one
## Why not the others
## Risks
## Privacy approach
```

</details>

<details>
<summary><strong>Phase 3 — Research Spin-Up (60–90 min)</strong></summary>

Goal: gather just enough evidence to avoid fantasy software.

Use the runner to execute targeted prompts and capture findings:
- Perplexity runner: `05_prompts/perplexity_runner/` (see its README)
- Data index: `02_data/00_index.md`

Evidence Log structure (log in `evidence_log.md`):

```
## Evidence Log
### Confirmed
### Likely but unverified
### Missing
### Useful datasets
### Useful source documents
### Prior art
### Risks
### Privacy implications
```

Tip: parse URLs from API metadata; don't ask for URLs in prompt text.

</details>

<details>
<summary><strong>Phase 4 — Opportunity Framing (45–60 min)</strong></summary>

Compare at least two MVP shapes before choosing.

Files:
- `04_build_guides/01_mvp_shapes.md`
- `04_build_guides/02_recommended_architectures.md`
- `03_artifacts/community_trust_framework.md`

Output:

```
## MVP Options
1. …
2. …
3. …

## Recommended MVP
## Why
## What we are explicitly not building
## Privacy design decisions
```

</details>

<details>
<summary><strong>Phase 5 — Scope Lock (45–60 min)</strong></summary>

Pin down must-haves, mockables, data, AI role, limits, and demo path.

Files:
- `99_templates/project_one_pager_template.md`

Key sentence:

> By Sunday, we will show a prototype that helps [user] do [specific thing] using [specific data/docs], without collecting [specific personal information], and without pretending to do [dangerous overclaim].

</details>

<details>
<summary><strong>Phases 6–9 — Build → Validate → Demo</strong></summary>

Build:
- Break work into FE/BE/data/content; assign source verification and demo owner.
- Keep AI constrained to explanation, retrieval, comparison, and guidance.
- Apply privacy-by-design to every data field and user interaction.

Validate:
- Use risk review prompts and red flags; check source links and clarity.
- Confirm no PII collection before demo.

Demo:
- Follow `04_build_guides/05_demo_advice.md`.

</details>

---

## Verification Workflow

1) Add official URLs and dates in `evidence_log.md`; flip status to Verified.
2) Mirror verified sources into `02_data/source_inventory.csv` with access mode and key fields.
3) After verification, promote findings into the Executive Brief inside `research_notes.md`.

---

## Hackbot Helper

You can use Hackbot to reconstruct context, run research, and shape an MVP.

- Boot prompt: `HACKBOT_BOOT_PROMPT.md`
- Corpus guide: `CORPUS_GUIDE.md`
- Full file manifest: `manifest.json`
- Team profile (recommended): `99_templates/team_profile_template.md`

**Team skills** (`skills/**/SKILL.md`):
repo_memory, problem_scoping, research_runner, dataset_mapper, opportunity_mapper, mvp_designer, risk_review, demo_coach, repo_librarian, continuity_planner, research_search

**Research corpus skills** (`skills/**/SKILL.md`):
research_corpus_navigation, cross_report_synthesis, evidence_grounded_answering, report_update_protocol

Notes:
- Hackbot never invents government programs or legal eligibility. It cites official sources and encourages verification.
- Hackbot always flags privacy risks before recommending data collection features.
- For best results, create a team profile so Hackbot can map tasks to roles and follow your communication preferences.

---

## Appendix: Pillar Context & Rubric

<details>
<summary>Open context from the Pillar Committee session (March 6, 2026)</summary>

Working Session: March 6, 2026, 11:00 AM – 1:00 PM

Pillar: 5 — Thriving and Inclusive Communities

Rubric Score Summary
| Statement                         | D1 | D2 | D3 | D4 | D5 | D6 | D7 | D8 | Total | Band        |
|-----------------------------------|----|----|----|----|----|----|----|----|-------|-------------|
| Immigrant Service Discovery       | —  | —  | —  | —  | —  | —  | —  | —  | 24    | Strong      |
| Cross-Agency Navigation           | —  | —  | 1  | —  | —  | —  | —  | —  | 22    | Needs work  |

Dimension key: D1 Clarity | D2 Scope | D3 Data readiness | D4 Champion | D5 Population & impact | D6 Operating environment | D7 Success criteria | D8 Accessibility

Quick-kill flags:
- Both statements lack a continuation pathway (no named departmental champion confirmed).
- Cross-Agency Navigation has D3=1 — the lowest data readiness score across all 12 targeted statements in the hackathon. No cross-agency referral dataset exists.

Targeted Statement 1: Help Residents Safely Discover and Connect to Trusted Support Services (Score 24/32 — Strong)
- See `01_problem_space/02_targeted_problem_statements.md`.

Targeted Statement 2: Helping Residents Navigate the Right Support Services Without Repeating Their Story (Score 22/32 — Needs work)
- D3=1 data wall. No cross-agency intake dataset. Teams must build around this constraint.
- See `01_problem_space/02_targeted_problem_statements.md`.

Prioritized Actions Before March 27, 2026
1) Compile starter data package for Cross-Agency Navigation (Tier 1 urgent)
2) Name departmental champion: Kate Ayers or Helen Rai (ReEstablish Richmond), Will Thornton or Sidney Edwards (YMCA), or Karla Almendarez-Ramos or Aneesah Smith (NCS)
3) Reference Help1RVA directly in Immigrant Service Discovery statement
4) Map the cross-agency referral pathway
5) ~~Document communication channels and priority languages~~ **CLOSED (2026-03-26):** Channels confirmed by OIRE; priority languages confirmed as Spanish, Arabic, Dari, Pashto, Portuguese

</details>
