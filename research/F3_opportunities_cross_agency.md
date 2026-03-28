> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Building Navigation Without Sharing Data — Four MVP Paths That Work Under D3=1

## Executive Summary

The hardest design challenge in cross-agency navigation is building a useful tool when the D3=1 constraint prohibits cross-agency data sharing. Without access to protected health information (PHI), intake records, or real-time capacity data, traditional "smart routing" fails. However, residents often face rejections not because of bad routing, but because they are unprepared for specific intake requirements. 

By leveraging open data standards like the Human Services Data Specification (HSDS) [1] [2] and public program rules (e.g., SNAP, WIC, LIHEAP) [3] [4] [5], a hackathon team can build a highly credible **Intake Guide MVP**. This approach bypasses the need for PHI entirely by focusing on pre-call preparation, utilizing existing APIs like One Degree [6] [7], and providing a clear, privacy-preserving upgrade path for when data-sharing policies eventually evolve.

## Problem Framing — Navigation Fails Without Sharing Data; Preparation Fixes It Faster

Residents frequently get lost between agencies and have to repeat their stories. The scale of this issue is massive; for instance, 16 million people in the United States dial 2-1-1 each year for help finding services [8]. 

Under the D3=1 constraint, cross-agency datasets containing intake records and referral outcomes are locked behind HIPAA walls and organizational silos. Attempting to build a predictive routing tool without this data risks sending vulnerable residents to agencies where they will be rejected for lacking the right paperwork. Instead of trying to predict outcomes without data, the most effective intervention is to ensure residents are perfectly prepared for the intake process of whichever agency they approach.

## Data Landscape You Can Use Today — HSDS, 211, One Degree, and Official Program Rules

There is a wealth of high-quality, public data available to build a robust navigation tool without touching PHI:

* **Open Standards (HSDS):** The Open Referral Human Services Data Specification (HSDS) provides a normative data model with specific fields for `service`, `eligibility`, `required_documents`, and `service_taxonomy` [1] [9] [10] [11] [2].
* **Official Program Requirements:** Government agencies publicly document their intake requirements. For example, the USDA provides detailed verification checklists for SNAP [3] and WIC [4], while HealthCare.gov lists required documents for Marketplace coverage [12], and state agencies list LIHEAP requirements [5].
* **Open APIs and Directories:** One Degree offers a free API for non-commercial use, providing access to a database of approximately 31,800 community resources with search features including text and tags [6] [13] [14]. Findhelp maintains a comprehensive national directory where 95% of resources are re-verified at least once every 180 days [15].
* **Needs Data:** 2-1-1 Counts provides real-time, searchable data on community-specific needs, tracking unmet needs and requests across 13 top categories and 76 subcategories [8].

## Approach Comparison — What’s Buildable, Useful, and Credible in 48 Hours

| Approach | Data Required | Primary User Flow | 48-Hour Feasibility | Credibility & Utility for Judges |
| :--- | :--- | :--- | :--- | :--- |
| **1. Pathway Map** | Public org info, HSDS service/taxonomy fields [9] [2]. | User selects a need → sees visual sequence of steps/orgs → clicks into profiles. | Medium. Can map 1-2 specific need areas (e.g., housing) with clickable steps. | High clarity, but risks oversimplification and cannot guarantee capacity. |
| **2. Intake Guide** | Official checklists (SNAP, WIC, LIHEAP) [3] [4] [5], HSDS eligibility/documents [10] [11]. | Case manager picks org → tool outputs pre-call checklist & scripts → shares with client. | High. Can easily compile 15-25 local org checklists and build a clean UI. | Very High. Directly cuts failed referrals, aligns with casework realities, highly actionable. |
| **3. Service Taxonomy** | HSDS taxonomy [2], One Degree API [6], Findhelp data [15]. | User describes need + filters → receives prioritized list of orgs with intake notes. | Medium-High. Requires integrating One Degree API and mapping to HSDS. | High. Practical routing without PHI, but risks overwhelming users with too many results [15]. |
| **4. Gap Visibility** | 211 Counts unmet needs data [8], local program counts. | Stakeholder selects geo/category → views needs vs. available programs. | High. Simple dashboard using 211 Counts data and basic charting. | High for policymakers, but does not directly help residents navigate the system today. |

## Recommended MVP — Intake Guide with HSDS Backbone and Guided Search Front Door

**Recommendation:** The hackathon team should build the **"Intake Guide"** approach, augmented with a lightweight "Service Taxonomy" front door. 

**Rationale:** 
This approach creates immediate, measurable value under the D3=1 constraint by eliminating avoidable denials caused by missing paperwork. It relies entirely on public, citable requirements (like SNAP and WIC documentation rules) [3] [4] and fits perfectly into existing HSDS fields (`eligibility`, `required_documents`) [10] [11]. 

**What to build in 48 hours:**
1. **Guided Search:** A minimal front-end using One Degree's API [6] or static HSDS JSON to let users select a need (e.g., "Food Assistance").
2. **Curated Profiles:** 15-25 deep-dive profiles for local organizations.
3. **Pre-Call Checklists:** For each organization, output a bilingual (English/Spanish) checklist of required documents (ID, proof of income, residency) [3] [4], intake hours, and a "what to say when you call" script.
4. **Export:** Ability to text, email, or print the checklist for the resident.

## What Judges Will See — Credibility, Utility, and a Real Upgrade Path

Judges will see a highly practical tool that solves a real workflow problem for case managers today. By citing official sources directly on the screen (e.g., "Requirements sourced from NC DHHS LIHEAP guidelines" [5]), the team establishes immediate trust. 

Furthermore, by structuring the underlying data using the Open Referral HSDS standard [1], the team demonstrates technical maturity. The MVP proves that the architecture is privacy-preserving today, but interoperability-ready for tomorrow.

## Risk Register and Mitigations — Don’t Repeat Past Directory Mistakes

* **Risk: Overwhelming Search Results.** Users of existing platforms like Aunt Bertha (Findhelp) have noted that directories can make it difficult to distinguish the most relevant local resources among exhaustive search results [15].
 * *Mitigation:* Focus on curation over crawling. Limit the MVP to top-tier, highly verified organizations rather than scraping thousands of unverified links.
* **Risk: Missing Niche/Non-English Programs.** Directories often miss smaller resources or those for non-English speaking help seekers [15].
 * *Mitigation:* Ensure the MVP is bilingual from day one (leveraging One Degree's Spanish language support capabilities) [14] and include explicit language-access filters.

## Metrics Without PHI — How We’ll Prove It Works

You do not need client-level data to prove this tool works. Success can be measured through operational KPIs:
1. **Checklist Completion Rate:** How often case managers generate and share a prep-sheet.
2. **Time-to-First-Call:** Reduction in time spent researching requirements before dialing.
3. **Provider Verification:** A one-click micro-form allowing destination agencies to confirm, "Yes, this client arrived with the correct documentation."

## 48-Hour Build Plan — Roles, Tasks, and Deliverables

* **Day 1 (Data & Design):** 
 * *Data Team:* Manually compile intake requirements for 20 key local organizations using official sources (SNAP, WIC, Medicaid) [3] [4] [12]. Format this data into HSDS JSON structures [1].
 * *Eng Team:* Scaffold the Next.js/React application. Build the taxonomy search UI and the organization profile pages.
* **Day 2 (Integration & Polish):**
 * *Eng Team:* Implement the export functionality (print/SMS/email). Optionally connect the One Degree API for broader search fallback [6].
 * *UX/Product:* Finalize bilingual templates. Draft the pitch narrative focusing on the D3=1 constraint and the HSDS upgrade path.

## Transparency Script for Judges — The D3=1 Position

When presenting to the judges, address the data constraint head-on with this narrative:

*"Under the D3=1 constraint, we know that cross-agency intake records and referral outcomes are locked behind HIPAA firewalls. We intentionally did not attempt to hack together or simulate protected health information. Instead, we built a solution that works today using 100% public data.*

*We built our platform on the Open Referral HSDS standard [1]. Today, it uses public eligibility and required document fields [10] [11] sourced directly from government authorities [3] [4] to ensure residents are perfectly prepared before they ever make a call. Tomorrow, when data-sharing governance permits, our HSDS-compliant architecture is already structured to accept closed-loop referral statuses and real-time capacity feeds from vendor APIs [15]. We are privacy-preserving by design today, and interoperability-ready for the future."*

## Appendix — Sources and Standards at a Glance

* **HSDS Reference:** Open Referral Data Specifications for `service`, `eligibility`, `required_documents`, and `service_taxonomy` [1] [9] [10] [11] [2].
* **Official Intake Requirements:** USDA FNS SNAP Verification [3], WIC Eligibility Tool [4], HealthCare.gov Required Documents [12], NC DHHS LIHEAP [5].
* **Directories & APIs:** One Degree Resource Server API [6] [16] [13], Findhelp (Aunt Bertha) Platform Profiles [15], 211 Counts Dashboard [8] [17].

## References

1. *About — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/reference/
2. *About — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/reference/#service-taxonomy
3. *Send in Required Documents*. https://fns-prod.azureedge.us/sites/default/files/resource-files/Required-Verification-Model-Notice-Annotated.pdf
4. *| Food and Nutrition Service*. https://www.fns.usda.gov/wic/eligibility-tool
5. *NC DHHS: Low Income Energy Assistance*. https://www.ncdhhs.gov/divisions/social-services/energy-assistance/low-income-energy-assistance-lieap
6. *One Degree Resource Server*. https://data.1degree.org/
7. *One Degree | Community resources near you*. https://www.1degree.org/
8. *211 Counts Overview UWSC r4.indd*. https://www.211summit.org/docs/211countstips.pdf
9. *About — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/reference/#service
10. *About — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/reference/#eligibility
11. *About — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/reference/#required-documents
12. *Health Plan Required Documents & Deadlines | HealthCare.gov*. https://www.healthcare.gov/verify-information/documents-and-deadlines/
13. *resource-server-api-docs/docs/common/query.md at main · 1deg/resource-server-api-docs · GitHub*. https://github.com/1deg/resource-server-api-docs/blob/main/docs/common/query.md
14. *Work With Us - About One Degree*. https://about.1degree.org/work-with-us/
15. *Community Resource Referral Platforms: A Guide for ...*. https://sirenetwork.ucsf.edu/sites/default/files/wysiwyg/Community-Resource-Referral-Platforms-Guide.pdf
16. *GitHub - 1deg/resource-server-api-docs: API Documentation for the One Degree Resource Server · GitHub*. https://github.com/1deg/resource-server-api-docs
17. *Data – 211 Illinois*. https://211illinois.org/data/