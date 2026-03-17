# Fast-Track Sources for a Richmond Immigrant & Refugee Org Directory

## Executive Summary

Building a verified, hackathon-usable starter directory of immigrant and refugee organizations in Richmond requires bypassing broad, unverified web searches in favor of high-signal state and health-system rosters. State-run listings yield the fastest, highest-signal seed set: Virginia's Office of New Americans (VDSS) publicly lists six statewide resettlement agencies [1]. A companion VDSS "Refugee Resettlement Providers" DOCX includes office-level details, such as the Church World Service (CWS) Richmond office located at 3314 N. Parham Road, Suite B [2]. 

Richmond has confirmed, in-market resettlement capacity that teams can contact today. For example, the International Rescue Committee (IRC) Richmond lists a staffed office with a direct address and phone number (2004 Bremo Rd, Suite 200; (804) 308-9144) [3]. Furthermore, health-system partnerships surface adjacent services immigrants actually need, such as legal aid, housing, and food. VCU Health's 2024-2025 Community Impact Report notes that $2.8 million has been awarded to community-based organizations since 2019 [4]. Its Medical-Legal Partnership provided $1.3 million in free legal services across 575 cases, utilizing partners like Central Virginia Legal Aid Society, Legal Aid Justice Center, and CancerLINC [4]. 

Expect unstructured formats across these sources (HTML pages, DOCX, and PDFs) and plan a lightweight normalization pipeline. Recency varies, so mitigating "stale contact" risk with a verification pass is essential. Notably, not all national brands operate locally—World Relief is not listed among Virginia's six official resettlement agencies [1], so teams should avoid chasing ghosts and focus on confirmed local entities.

### Success Criteria for the Hackathon Team
* **Volume & Depth**: 20–30 organizations with name, service category, address, phone, and URL.
* **Verification**: At least 10 entries phone-verified with a `last_verified_date`.
* **Categorization**: Tags for "resettlement," "legal," "health access," "food," "housing," and "ESL/education."
* **Provenance**: Clear source-of-truth link and notes per record.

## Ranked Source Landscape

Three primary sources (VDSS ONA, VDSS Providers DOCX, and the VCU Health report) provide the fastest, most verifiable lift for a hackathon team. The IRC Richmond page confirms local presence, while other sources serve as secondary connectors or require manual extraction.

| Rank | Source | Structure | Fields Present | Currency | Access | Coverage Relevance | Usability Score (1-5) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **1** | **VDSS Office of New Americans - Refugee Services** | HTML page with outbound links | Agency names, links to city-specific pages | Active site | Public web | High: Direct refugee resettlement network [1] | 5 |
| **2** | **VDSS Refugee Resettlement Providers** | DOCX document | Org name, program, leadership, addresses, contacts [2] | Date not visible; treat as to-verify | Public download | High: Office-level details (e.g., CWS Richmond) [2] | 5 |
| **3** | **IRC Richmond Office Page** | HTML single-org page | Address, phone, email, volunteer info [3] | Live page | Public web | High: Confirms Richmond presence [3] | 4 |
| **4** | **VCU Health Community Impact Report 2024-2025** | PDF | Named partners (CVLAS, LAJC, CancerLINC, CCC), impact metrics [4] | 2024-2025 [4] | Public PDF | Medium-High: Adjacent supports (legal, housing) [4] | 4 |
| **5** | **Richmond City Health Dept. - ONA-Refugee Services** | HTML page | Program description to address health issues [5] | Live page | Public web | Medium: Connector; not a directory [5] | 3 |
| **6** | **United Way of Greater Richmond & Petersburg** | HTML page (Pending extraction) | Agency names, links, focus areas | Updated by funding cycle | Public web | Medium: Regionwide safety-net orgs | 3 |
| **7** | **Community Foundation for a greater Richmond** | Web/PDF posts (Pending extraction) | Grantee names, focus areas | 2024-2025 items visible | Public web | Medium: Adds nonprofits serving newcomers | 3 |
| **8** | **211 Virginia Directory (Richmond)** | Searchable directory (Pending extraction) | Org name, address, phone, eligibility, languages | Continuously updated | Public search | High: Breadth incl. ESL/immigration/legal | 3 |
| **9** | **Commonwealth Catholic Charities** | HTML site section | Programs, contact info | Live site | Public web | High: Core resettlement provider [1] | 4 |
| **10** | **Local Media (RTD, RVA Mag)** | Articles (Pending extraction) | Orgs named in stories | Current by article date | Public web | Medium: Surfaces grassroots orgs | 2 |

*Takeaway*: Prioritize the top four sources immediately. They provide structured or easily extractable data with high relevance to the target population, allowing the team to build a robust foundation in the first few hours.

## Data Structure and Field Coverage

Because the highest-value sources are unstructured (HTML, PDF, DOCX), the hackathon team must define a simple schema and a quick extraction approach to maintain momentum and ensure data uniformity.

### Minimal Viable Schema
To standardize across disparate sources, implement the following lightweight schema:
* `org_name` (text)
* `category` (enum: resettlement, legal, health access, food, housing, ESL/education, employment)
* `services_summary` (short text)
* `address` (text)
* `phone` (text)
* `url` (text)
* `source` (text; e.g., "VDSS ONA," "VCU Health 2024-2025")
* `last_verified_date` (date)
* `notes` (open text for caveats)

### Extraction Approach
Rely on manual copy-pasting with side-by-side validation for HTML, PDF, and DOCX files. Optionally, use a lightweight parsing script for DOCX and PDF text blocks. Immediately log source URLs per record and paste phone/address data verbatim as shown (e.g., IRC Richmond: 2004 Bremo Rd, Suite 200; (804) 308-9144 [3]). Add a verification tier to prioritize outreach: Tier 1 (state-listed or health-system named), Tier 2 (foundation/United Way funded), and Tier 3 (media/connector-sourced).

## Build the Starting List (20-30 Orgs)

You can assemble a usable 20-30 organization starter list today by combining three primary sources. Once merged, de-duplicated, and tagged, this yields a practical, contact-rich list for immigrant and refugee residents.

### Source Mix and Expected Counts
* **Core resettlement agencies (VDSS ONA + DOCX)**: Virginia lists six statewide agencies [1]. Expect 2-3 with direct Richmond offices (e.g., IRC, CWS, Commonwealth Catholic Charities) and additional statewide orgs serving the region.
* **Health-system named partners (VCU Health 2024-2025)**: Yields 5-10 directly extractable organizations supporting legal, housing, and food needs (e.g., Central Virginia Legal Aid Society, Legal Aid Justice Center, CancerLINC, Commonwealth Catholic Charities) [4].
* **Agency-linked program pages**: Yields 6-10 entries when enumerating program sub-units (employment, case management, immigration legal, ESL) from the core resettlement agencies.

### Sample "Today" Adds from Verified Pages
* **International Rescue Committee - Richmond**: 2004 Bremo Rd, Suite 200, Richmond, VA 23226; (804) 308-9144 [3].
* **Church World Service - Richmond**: 3314 N. Parham Road, Suite B, Richmond, VA 23294 [2].
* **Commonwealth Catholic Charities**: Resettlement services provider [1].
* **Legal Partners**: Central Virginia Legal Aid Society, Legal Aid Justice Center, CancerLINC (all named in the VCU Health report) [4].
* **Connector**: Richmond City Health Dept. - Office of New Americans-Refugee Services [5].

## Gaps and Augmentation Plan

Current evidence-rich sources heavily skew toward official resettlement, health, and legal services. They likely under-represent grassroots and community-level supports. 

### Likely Gaps
* School-based newcomer/ESL supports and family resource lines (e.g., Richmond Public Schools).
* Ethnic community associations and faith-based congregations serving newcomers.
* Small mutual-aid networks, community interpreters, and adult ESL providers.
* Immigration legal clinics beyond the major providers.

### Fast Gap-Fill Actions
* **Richmond Public Schools**: Search rvaschools.net for "multilingual learners," "newcomer," and "family resources" to capture listed community partners or ESL referrals.
* **211 Virginia**: Query "immigrant," "refugee," "ESL," "citizenship," and "immigration legal" within the Richmond/Henrico/Chesterfield area. Manually record the top 10 entries to respect Terms of Service.
* **Local Media Scan**: Conduct a 30-minute keyword scan of the Richmond Times-Dispatch and RVA Mag to spot named grassroots organizations, tagging them as "media-sourced."
* **Cultural Institutions**: Review exhibit or program pages from institutions like The Valentine for immigrant community documentation that references partner organizations.

## Verification and Governance

Public access is open for all cited sources, but automated scraping of some directories (like 211) may be restricted by terms of service. A lightweight verification pass and clear provenance fields prevent stale or misdirected referrals.

### Practices to Adopt
* Phone-verify the top 10 entries immediately; log the call outcome and the `last_verified_date`.
* Record the exact source link for every fielded entry. Prefer direct organization pages over secondary mentions when available.
* Use the "verification tier" and "notes" fields to warn users about potential ambiguity (e.g., a statewide organization that lacks a physical Richmond office).
* Avoid automated bulk scraping of managed directories without permission; rely on manual queries for gap-filling.

## Workplan for the Hackathon

A two-block sprint (extract, then verify) will deliver a credible V1 directory within 6-8 hours.

### Step-by-Step Execution

**Block 1: Extraction & Normalization (2-3 hours)**
* Extract the VDSS ONA page to identify the 6 core agencies [1] and follow links to locate Richmond office pages.
* Parse the VDSS Providers DOCX to capture Richmond office entries, such as CWS Richmond [2].
* Review the VCU Health 2024-2025 report to list all named partner organizations (e.g., CVLAS, LAJC, CancerLINC, CCC) [4]. Capture their home-page URLs.
* Normalize all extracted data into the shared schema and de-duplicate the list.

**Block 2: Verification & Gap-Filling (2-3 hours)**
* Phone-verify the top 10 entries (focusing on resettlement and legal aid).
* Add the Richmond City Health Dept. ONA-Refugee Services as a connector [5] and request any internal partner rosters they may have.
* Begin manual lookups via Richmond Public Schools and 211 Virginia to identify 5-8 additional organizations. Tag these as "pending verification."

**Deliverables by End of Day**
* 20-30 organization entries populated with contacts and service tags.
* A completed verification log for the top 10 entries.
* A backlog of "to-verify" candidates sourced from schools, 211, and local media.

## Annex: Field-by-Field Notes from Key Sources

Understanding exactly what each validated source contains ensures the team extracts data efficiently without missing critical context.

### VDSS ONA - Refugee Services
* **What's inside**: A list of Virginia's six official resettlement agencies (Catholic Charities Diocese of Arlington, Church World Service, Commonwealth Catholic Charities, Ethiopian Community Development Council, International Rescue Committee, Lutheran Social Services) [1].
* **Fields visible**: Agency names and external URLs [1].
* **Use**: Click through to local office pages to find addresses and phone numbers; copy core contacts.

### VDSS Providers DOCX
* **What's inside**: Office-level details for resettlement providers, including specific addresses like the CWS Richmond Office at 3314 N. Parham Road, Suite B, Richmond, VA 23294 [2].
* **Fields visible**: Organization name, leadership/director names, address, and contact info [2].
* **Use**: Copy and paste directly into the schema, prioritizing Richmond-region entries.

### IRC Richmond Page
* **What's inside**: Full contact details for the local office: 2004 Bremo Rd, Suite 200, Richmond, VA 23226; (804) 308-9144 [3].
* **Use**: Treat as a high-confidence, Tier 1 entry with immediate outreach potential.

### VCU Health Community Impact Report 2024-2025
* **What's inside**: Identifies named partners such as Central Virginia Legal Aid Society, Legal Aid Justice Center, CancerLINC, and Commonwealth Catholic Charities [4]. It also includes quantified program impacts, noting $2.8 million in grants since 2019 and $1.3 million in free legal services provided across 575 cases via the Medical-Legal Partnership [4]. The VCU Health Hub at 25th also highlights its partnership with CVLAS to help residents navigate benefits [6].
* **Use**: Add these named partner organizations as "adjacent supports" and tag their categories accordingly (e.g., legal, housing, food).

## References

1. *Refugee Services - Virginia Department of Social Services*. https://www.dss.virginia.gov/community/ona/refugee_services.cgi
2. *Refugee Resettlement Providers*. https://www.dss.virginia.gov/files/division/cvs/rr/benefits_services/access_benefits_services/Refugee_Resettlement_Providers.docx
3. *Richmond, VA | The IRC*. https://www.rescue.org/united-states/richmond-va
4. *Community Impact Report | 2024 - 2025*. https://www.vcuhealth.org/media/vcuhealth/media/external-use/VCUHealthCommunityImpactReport.pdf
5. *Office of New Americans-Refugee Services - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/sample-page/programs/new-americans-refugee-services
6. *How one Virginia community center is connecting residents with the health care resources they need | VCU Health*. https://www.vcuhealth.org/news/how-one-virginia-community-center-is-connecting-residents-with-the-health-care-resources-they-need