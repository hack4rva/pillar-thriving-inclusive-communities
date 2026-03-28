# Thriving and Inclusive Communities — Hackathon Challenge

This file defines the two practical problem statements for this pillar and the top-rated blue sky vision. Read this before reading anything else in the repository.

---

## The Two Problems You're Solving

### Problem 1: Help Residents Safely Discover and Connect to Trusted Support Services

**Score: 24/32 — Strong (recommended starting point)**

**Statement:**
While Richmond has a growing network of City programs, nonprofits, and community-based organizations that provide support to immigrant and refugee residents, many residents struggle to safely discover and connect to these services. Concerns about privacy, language barriers, and uncertainty about which organizations can be trusted often prevent residents from seeking help.

**Why this problem matters:**
Support services exist but are invisible or inaccessible to many of the residents who need them most. Help1RVA connects residents to services but requires navigation friction. Service information across Help1RVA, FindHelp/Aunt Bertha, and individual organization websites is not synchronized. Information quality varies and updates lag. The result: residents in crisis don't find help before they give up.

**Build toward:**
- Privacy-first service finder — no login, no PII collected, anonymous browsing by service type
- Multilingual resource tool — Spanish, Arabic, Dari, Pashto, and Portuguese are the confirmed priority languages
- Trusted community messenger system — Facebook groups and WhatsApp are the confirmed primary channels; distribute through community ambassador organizations
- Help1RVA interface improvement — multilingual, voice-friendly, simpler navigation layer; 211 Virginia API (apiportal.211.org) is an alternative data source with free trial access and 240+ language live interpretation
- QR-code printable resource guide for distribution through faith organizations, schools, and clinics

**Key constraints:**
- Privacy is not optional — must not require account creation or personal information from residents
- Must work with existing nonprofit and community-based support networks — do not replace them
- Service information must be updatable by community organizations without technical expertise
- Must function through channels residents actually use — not just a web app
- Must not expose any information that could put residents at enforcement risk

**Data gaps to address:**
- Help1RVA export not currently public — treat as a closed FindHelp instance; use public print views for schema reference. 211 Virginia has a public developer API (apiportal.211.org, free trial) with 240+ language live interpretation — consider it as your primary accessible data source.
- Priority languages confirmed: **Spanish, Arabic, Dari, Pashto, and Portuguese** (Bon Secours CHNA + 2025 VDH survey). Dari and Pashto have very low local staff capacity (8.3% and 0% of organizations have speakers); pair any language UI with navigator backstops.
- Trusted organizations: **CLOSED (2026-03-26)** — 15 organizations confirmed by Karla Almendarez-Ramos, OIRE, NCS — includes IRC, ReEstablish Richmond, Sacred Heart Center, Afghan Association of Virginia, African Community Network, and others. See `research/D2_data_community_org_directories.md`.
- Communication channels: **CLOSED (2026-03-26)** — confirmed by OIRE. Primary: Facebook groups and WhatsApp. Also: Instagram (younger audiences), YouTube, in-person networks, and local radio. See `research/D6_data_communication_channels.md`.

#### Participant guide: connecting to the rubric (if you chose this problem)

Optional prompts — judges use [`RUBRIC.md`](../../RUBRIC.md).

- **Impact:** Make **trusted** services discoverable for immigrant/refugee residents with **privacy-first** design.
- **User Value:** Resident journey without login/PII; channel fit (WhatsApp, QR, print) as relevant.
- **Feasibility:** Honest about Help1RVA vs 211 API vs public print views; updatable by community partners where you claim it.
- **Innovation:** Multilingual, voice-friendly, or ambassador-ready distribution — not just another English-only web form.
- **Execution:** Demo respects no-PII; shows real or sample resource data clearly.
- **Equity and inclusion:** Safety, language priority list, and enforcement-risk awareness front and center.

**What often works well:** Privacy-first finder, multilingual layer, QR/print handouts, channel-appropriate sharing.

**What to avoid:** Collecting immigration/health PII, or features that could increase enforcement risk.

*Try asking yourself:* Would someone worried about privacy still use this?

---

### Problem 2: Helping Residents Navigate the Right Support Services Without Repeating Their Story

**Score: 22/32 — Needs work**
**⚠ Critical data gap: D3=1 — no cross-agency dataset exists. Teams must work with public information only and accept that the demo will be conceptual for cross-agency elements.**

**Statement:**
Residents seeking housing stability, workforce support, or reentry services often need assistance from multiple City departments and partner organizations. However, information about programs is spread across different agencies, eligibility requirements are complex, and residents frequently have to repeat their story to multiple providers.

**Why this problem matters:**
Residents navigating housing, workforce development, or reentry services interact with Social Services, Housing, workforce programs, and nonprofits — all operating on different systems. Each touchpoint may require re-explaining the same circumstances, which is exhausting and can be retraumatizing. The gap is not in whether services exist — it's in whether residents can navigate to them without breaking down in the process.

**Build toward:**
- Service pathway visualization — a staff-facing map of how a resident moves between services (conceptual, built from public service descriptions)
- Staff coordination helper — helps case managers at one organization understand what a resident may need from another, without sharing personal resident data
- Eligibility navigator — given a resident's general situation (no PII), surfaces relevant programs and the order to approach them
- Pathway explainer tool — plain-language breakdown of the housing/workforce/reentry service ecosystem for both residents and intake staff

**Key constraints:**
- HIPAA and PII rules are real blocking constraints — do not collect, store, or display individual resident data
- Cross-agency data sharing is severely limited by policy — do not build on assumptions of data access that doesn't exist
- Must support, not replace, human case managers and community trust relationships
- Demo must be honest about what is conceptual vs. what is data-driven

**What you cannot build this weekend:**
- A tool that requires cross-agency intake data or shared case records
- A system that integrates with Social Services, Housing, or workforce program internal databases
- Anything that makes eligibility rulings or case management decisions

**How to build credibly despite the data constraints:**
- Use publicly available service descriptions from Help1RVA, organization websites, and City program pages
- Build the staff-facing pathway visualization using published program information only
- State clearly in the demo which parts are populated with real data vs. illustrative content

#### Participant guide: connecting to the rubric (if you chose this problem)

Optional prompts — [`RUBRIC.md`](../../RUBRIC.md) is authoritative for judges.

- **Impact:** Clarify **pathways** between housing/workforce/reentry supports using **public** descriptions — reduce repeated storytelling without shared case data.
- **User Value:** Resident (general situation, no PII) or **staff** helper who sees order-of-operations clarity.
- **Feasibility:** No cross-agency case systems, no eligibility **rulings**, label conceptual vs data-backed parts.
- **Innovation:** Pathway maps, role-played handoffs, or explainer UX that respects trauma and trust.
- **Execution:** Honest demo boundary (what’s illustrative).
- **Equity and inclusion:** Center dignity; avoid tech that implies surveillance or data you don’t have.

**What often works well:** Public-information pathway viz, staff coordination helper without resident records, eligibility **navigator** that surfaces programs — not decisions.

**What to avoid:** PII storage, fake integrations, or automated case decisions.

*Try asking yourself:* Does the demo **admit** what’s conceptual — and still feel useful?

---

## The Blue Sky Vision

### Universal Access to City Services — 21/27 — Strong ★

**Statement:**
Every City service has a multilingual, plain-language front door that works on a phone, requires no digital literacy, and meets residents where they are — in their language and through their trusted community organizations.

**Why this scored well:**
The gap between "services exist" and "residents can access them" is primarily a language, literacy, and trust problem — not a supply problem. This blue sky has high hackathon relevance because a multilingual service finder or resource tool is a direct prototype of this vision. The technical barrier is low; the content and community trust work are the actual challenge.

**Hackathon path if you're aiming at this vision:**
Build the multilingual access component of this vision:
- A service finder in 2–4 languages (Spanish at minimum)
- Designed for low digital literacy — large tap targets, plain language, minimal navigation
- Distributable through community channels (QR code, SMS link, WhatsApp share button)

The blue sky is the ceiling. Problem 1 (Safe Service Discovery) is the practical floor. A team that builds Problem 1 with this blue sky framing — multilingual, privacy-first, channel-flexible — will have a compelling pitch for both the Pillar Award and the Moonshot Award.

**Rubric connection (blue sky):** Same emphasis as **Problem 1** (multilingual, low-literacy, channel-flexible access). Use the Problem 1 participant guide.

---

## Pillar Award: official scoring mechanics

**Authoritative rubric:** [`RUBRIC.md`](../../RUBRIC.md) at the hackathon root.

**Participant guides** under each problem are optional — **not** binding on judges.

| Category | Weight |
|----------|--------|
| **Impact** (targeted civic problem) | **5** |
| **User Value** | 4 |
| **Feasibility** / implementability | 3 |
| **Innovation** / originality | 3 |
| **Execution** / prototype quality | 3 |
| **Equity and inclusion** | 3 |

Read **`RUBRIC.md`** for full definitions and anchors.

**Score formula:** Sum of (category score 1–5 × weight). Maximum 105.

**Tiebreaker:** User Value score.

**General tips** (full detail in `RUBRIC.md`): Civic usefulness over complexity; flag fragile assumptions; slides-only → low Execution.
