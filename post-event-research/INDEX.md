# Post-Event Research Index — Thriving and Inclusive Communities

**Pillar:** Thriving and Inclusive Communities
**GitHub:** [hack4rva/pillar-thriving-inclusive-communities](https://github.com/hack4rva/pillar-thriving-inclusive-communities)
**Problem Statements:**
- PS1: Immigrant Service Discovery — Help residents safely find trusted community services without creating accounts or sharing identifying information
- PS2: Cross-Agency Service Navigation — Help residents navigate housing, workforce, and reentry services without repeating their story across agencies

**For AI agents:** Read this file to locate any post-event research artifact. Do not list the directory.

---

## Shared Research (Cross-Demo, Per Problem Statement)

| Dir | JTBD | Pain Points | Prior Art |
|-----|:----:|:-----------:|:---------:|
| [`_shared-immigrant-discovery/`](_shared-immigrant-discovery/) | ✅ | ✅ | ✅ |
| [`_shared-cross-agency/`](_shared-cross-agency/) | ✅ | ✅ | ✅ |

These files synthesize the problem statement across all demos in that PS. Read them before reading any per-project file.

---

## Per-Project Research Inventory

| Project | Problem Statement | JTBD | Pain | Prior Art | Solution Ideas |
|---------|------------------|:----:|:----:|:---------:|:--------------:|
| [`804me/`](804me/) | PS2: Cross-Agency | ✅ | ✅ | — | — |
| [`circle-trust/`](circle-trust/) | PS1: Immigrant Discovery | ✅ | ✅ | — | — |
| [`core-eligibility-pack-builder/`](core-eligibility-pack-builder/) | PS2: Cross-Agency | ✅ | ✅ | — | — |
| [`reentry-72-hour-navigator/`](reentry-72-hour-navigator/) | PS2: Cross-Agency | ✅ | ✅ | — | — |
| [`rva-helps/`](rva-helps/) | PS1: Immigrant Discovery | ✅ | ✅ | — | — |
| [`whatsapp-service-finder/`](whatsapp-service-finder/) | PS1: Immigrant Discovery | ✅ | ✅ | — | — |

---

## Research Answers (`_research-answers/`)

Parallel AI queries that answered the JTBD open questions. Read `QUERY_MAP.md` to see which file answers which question.

| File | Problem Statement | Questions Answered |
|------|------------------|-------------------|
| [`QUERY_MAP.md`](_research-answers/QUERY_MAP.md) | Both | Full map of JTBD questions → query files |
| [`id_q1_data.md`](_research-answers/id_q1_data.md) | PS1 | Service directory data, Help1RVA, 211, trust signals |
| [`id_q2_trust.md`](_research-answers/id_q2_trust.md) | PS1 | User trust barriers, equity, no-account-required patterns |
| [`ca_q1_systems.md`](_research-answers/ca_q1_systems.md) | PS2 | Cross-agency data systems, housing/workforce/reentry APIs |
| [`ca_q2_equity.md`](_research-answers/ca_q2_equity.md) | PS2 | User burden, equity gaps, integration constraints |

---

## Agent Reading Sequence

```
1. Read this file (INDEX.md) — orient
2. For PS1 context: _shared-immigrant-discovery/jtbd_analysis.md
3. For PS2 context: _shared-cross-agency/jtbd_analysis.md
4. For a specific project: <project>/jtbd_analysis.md → <project>/pain_points.md
5. For answered research questions: _research-answers/QUERY_MAP.md → relevant query file
```
