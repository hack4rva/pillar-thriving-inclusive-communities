---
title: "Help1RVA vs 211 Virginia — Service Directory Comparison for Immigrant and Refugee Communities"
pillar: thriving-inclusive-communities
section: C
problem_statement: immigrant-service-access
tags:
  - Help1RVA
  - 211 Virginia
  - FindHelp
  - service directory
  - API
  - data access
  - language support
  - Richmond VA
summary: "Deep comparison of Help1RVA (FindHelp platform) and 211 Virginia for serving Richmond's immigrant and refugee communities. Key finding: 211 Virginia has a public developer API at apiportal.211.org with free trial access. FindHelp API is locked to paying customers and prohibits data caching. 211 Virginia also provides 240+ language live interpretation via phone. Research conducted via Parallel.ai deep research, 2026-03-26."
geography: Richmond, VA
source: parallel-ai-deep-research
status: verified
privacy_sensitivity: low
related_reports:
  - D1_data_help1rva
  - D2_data_community_org_directories
  - C1_services_help1rva
---

# Help1RVA vs 211 Virginia — Service Directory Comparison

*Research: Parallel.ai deep research, 2026-03-26*

---

## Executive Summary

Help1RVA and 211 Virginia serve distinct but complementary roles. **211 Virginia is the better tool for individuals** — 24/7 access, 240+ language live interpretation, and a public developer API. **Help1RVA is the better backbone for providers** — local Richmond curation, inter-agency referrals, and program management tools.

Critical finding: a vital layer of support — informal mutual aid networks on Facebook and WhatsApp — exists almost entirely outside both formal directories.

---

## Platform Overview

| Dimension | Help1RVA | 211 Virginia |
|---|---|---|
| URL | help1rva.org | search.211virginia.org / 211virginia.org |
| Underlying platform | FindHelp (formerly Aunt Bertha) | 211 National Data Platform (NDP) |
| Operator | YMCA of Greater Richmond | Virginia DSS + partners |
| Access channels | Web only | Web + phone (dial 2-1-1) + text + chat |
| Geographic scope | Greater Richmond metro | Statewide Virginia |
| Funding model | Private/nonprofit collaborative | State-mandated (Virginia law) |

---

## Language Support

| Dimension | Help1RVA | 211 Virginia |
|---|---|---|
| Website interface | Spanish; FindHelp platform supports listing languages from Swahili to Uzbek to Yoruba | Search site allows filtering by language; interface translation scope unconfirmed |
| Live interpretation | Via YMCA Social Needs Navigators (multilingual staff + translation service) | **240+ languages via LanguageLine** — guaranteed 24/7 via phone, text, and chat |

**211 Virginia's live interpretation in 240+ languages is the decisive advantage for immigrant and refugee residents**, especially for Dari, Pashto, Amharic, Tigrinya, Kinyarwanda, and Burmese speakers for whom no local staff capacity exists.

---

## Data Maintenance Quality

| Dimension | Help1RVA | 211 Virginia |
|---|---|---|
| Update model | Self-service — orgs claim and maintain own listings | Dedicated database curation team with formal review cycle |
| Verification mandate | No mandated schedule | Annual — each listed agency receives a tokenized link to review their info; changes take 4–6 weeks |
| Accreditation | None confirmed | Inform USA national accreditation |
| Risk | Stale listings if orgs don't actively maintain | 18,000+ statewide entries; scale creates coverage gaps |

---

## API and Data Access — Critical for Hackathon Teams

### Help1RVA / FindHelp

- API exists but is **gated to paying customers** via a contractual license
- License is **read-only, real-time only** — explicitly **prohibits caching or persisting directory data**
- Analytics/referral exports (CSV) available to licensed customers only
- No public developer portal or free trial

**Hackathon implication:** You cannot freely access Help1RVA data via API. Manual extraction of 20–30 records is the legally safe path (see D1_data_help1rva.md).

### 211 Virginia

- **Public developer portal: https://apiportal.211.org**
- **Free trial available** — external developers can register and begin using APIs immediately
- APIs available:
  - **Search API** — find resources by keyword and taxonomy
  - **Export API** — bulk export of resource data to external systems
  - **Resources API** (v2 Query API in preview) — complex filtered queries
- Data also available via the **211 Counts public dashboard** (real-time trends and analytics, partnership with Washington University at St. Louis)
- Annual reports and needs reports published publicly

**Hackathon implication:** 211 Virginia data is the most accessible structured dataset for building a service finder. Start here. Use the free trial API for your prototype.

---

## Coverage Gaps

### Services Listed on Both
Major orgs (Commonwealth Catholic Charities, IRC Richmond, ReEstablish Richmond, Sacred Heart Center) appear in both directories.

### Help1RVA Only (Likely)
Hyperlocal Richmond orgs that self-enrolled in FindHelp but didn't submit to 211.

### 211 Virginia Only (Likely)
Statewide agencies with regional offices; state government benefit programs.

### Neither Directory (Confirmed Gap)
**Informal mutual aid networks** — the most immediate support layer for new arrivals:

| Network | Platform | URL | Focus |
|---|---|---|---|
| Afghans in Richmond VA | Facebook group | https://www.facebook.com/groups/1146291969237173/ | Afghan community connection and support |
| Richmond & Tri-Cities, VA Mutual Aid | Facebook group | https://www.facebook.com/groups/3033661696676599/ | Broader Richmond metro mutual aid |

These groups provide: language-specific peer support, ad-hoc transportation, food and furniture exchanges, micro-fundraising for urgent needs. Particularly critical for Dari, Pashto, Tigrinya, and Kinyarwanda speakers.

**Also not captured:** WhatsApp community networks, faith-based informal resettlement support, newcomer-owned micro-enterprises, smaller volunteer-run ethnic associations.

---

## Recommendations by Use Case

| Use Case | Recommended Tool |
|---|---|
| Individual seeking services in their language | **211 Virginia** — call 2-1-1 for live interpretation in 240+ languages |
| Service provider managing their listings | **Help1RVA** — claim and update your program profile |
| Hackathon team building a service finder | **211 Virginia API** (apiportal.211.org, free trial) |
| Finding community trust networks not in directories | **Facebook mutual aid groups + trusted org referrals** |
| Cross-checking Richmond coverage | Use both + verify against org websites |

---

## Key Takeaways for Hackathon Teams

1. **Use 211 Virginia's public API** (apiportal.211.org) for your data layer — it's the most accessible and legally clean path.
2. **Mark Help1RVA/FindHelp data as read-only and ephemeral** — don't cache it, don't build a database from it without a partnership.
3. **211 Virginia's 240+ language phone line is a critical resource to surface** in any navigation tool — it's the best fallback for languages your tool doesn't natively support.
4. **Informal mutual aid networks are invisible to both directories** — acknowledge this gap in your demo and design for it (e.g., allow community orgs to add their own groups).
5. **CCC's resettlement program status is uncertain** — any directory tool should include a "verify current availability" flag on CCC listings (see C6 for details).
