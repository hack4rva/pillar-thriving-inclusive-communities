# Virginia refugee resettlement 2021–2026: Richmond’s footprint, services, and data playbook

## Executive Summary
Virginia remains a critical hub for refugee resettlement, ranking as the 4th highest destination state in FY2022 with 1,872 combined refugees and Special Immigrant Visa (SIV) holders [1]. Within this landscape, Richmond operates as a high-demand locality supported by two primary Reception and Placement (R&P) agencies—Commonwealth Catholic Charities (CCC) and the International Rescue Committee (IRC)—alongside vital integration NGOs like ReEstablish Richmond [2] [3] [4] [5]. 

The state directs substantial resources toward these populations, with the Virginia Department of Social Services (VDSS) Office of New Americans (ONA) administering $55,522,000 annually in non-general funds across eight federally funded programs [6]. However, the early-service window is narrow and unforgiving: foundational R&P services last only 30 to 90 days [1], and the Matching Grant program requires enrollment within 31 days of arrival [7]. Missing these windows creates severe downstream risks for housing and economic self-sufficiency. 

For data tracking and hackathon modeling, a critical methodological shift occurred in July 2024: federal Refugee Processing Center (RPC) reports now track "Actual Destination City" rather than just the affiliate's city, allowing for precise tracking of Richmond's true arrival share [8] [9] [10].

## Why this brief matters — A practical map to volumes, services, and decisions
This brief serves as a strategic decision guide for understanding refugee flows, targeting services, and utilizing reliable public data for Virginia and the Richmond area. For policymakers, service providers, and hackathon teams, navigating the resettlement ecosystem requires distinguishing between formal USRAP refugees and broader immigrant populations, understanding strict federal service timelines, and knowing exactly where public data ends and institutional data gaps begin. By mapping the provider landscape and clarifying recent federal reporting changes, this playbook enables stakeholders to build accurate models, align proposals with federal funding priorities, and identify critical intervention points in the refugee integration journey.

## Data landscape and reliability — What’s published, where, and how to use it
The public data landscape for refugee resettlement relies on a combination of federal tracking systems and state-level administrative reports. While state-level volumes are well-documented, granular city-level data and specific agency capacities require careful navigation of recent reporting changes and direct outreach.

| Dataset / Source | Granularity & Cadence | Key Fields & Usage | Caveats & Limitations |
| :--- | :--- | :--- | :--- |
| **RPC "Refugee Arrivals by State and Nationality"** [11] [12] [8] [9] [10] | State and City level; updated monthly | Tracks formal USRAP refugee admissions by origin and destination. | Post-July 2024 uses "Actual Destination City"; prior data used Affiliate City. |
| **RPC "Amerasian and SIV Arrivals"** [11] [13] | State level; updated monthly | Tracks Iraqi and Afghan SIVs receiving resettlement benefits. | Kept separate from standard refugee counts; must be aggregated manually for total flows. |
| **PRM R&P Fact Sheets** [1] | National/State level; annual | Outlines the 30-90 day core services and top destination states. | Does not provide local agency capacity limits. |
| **ORR Program Pages** [7] [14] | Federal program rules | Details Matching Grant (MG), Refugee Support Services (RSS), and eligibility. | Policy guidelines only; no local utilization data. |
| **ORR Virginia Affiliates List** [5] | City level; static | Lists official R&P local affiliates by city and contact info. | Does not list non-R&P support NGOs. |
| **VDSS/ONA Annual Reports** [15] [6] [16] | State level; annual | Details $55.5M funding, 8 programs, and statewide client counts. | Lacks city-level arrival counts and specific agency capacities. |

**Key Takeaway:** Federal RPC/ORR and Virginia ONA sources provide robust arrivals data, provider lists, and program overviews, but users must account for the July 2024 methodology change when analyzing historical city-level trends.

## Virginia arrival volumes — Annual refugees by year (FY2021–FY2025)
Virginia's annual refugee flows have risen significantly post-2021, driven by global crises and the rebuilding of the U.S. Refugee Admissions Program (USRAP). In FY2022, Virginia ranked as the 4th highest destination state in the country, receiving 1,872 combined refugees and SIVs [1]. 

To build a complete FY2021–FY2025 dataset, analysts must extract final end-of-year totals from the RPC's historical archives [12]. It is critical to note that the RPC maintains separate reports for standard refugees and Amerasian/SIV arrivals [11] [13]. When calculating total resettlement burdens on state infrastructure, these two datasets must be combined, but they should be kept distinct in formal reporting to maintain demographic accuracy.

## Within-state geography — Estimating Richmond’s share using new "Actual Destination City"
Historically, tracking exact city-level arrivals was flawed because federal data relied on the "Affiliate City" (where the agency office was located) rather than where the refugee actually lived. As of July 2024, the RPC updated its "Arrivals by State and Nationality" reports to use "Actual Destination City" and "Actual Destination State" [8] [9] [10]. These values now reflect the placement city for virtual R&P cases and the affiliate city for all other cases [17].

To compute Richmond's exact share of Virginia arrivals:
1. Parse the FY2024 (Q4), FY2025, and FY2026 year-to-date RPC PDF reports [8] [9] [10].
2. Filter for "Actual Destination City = Richmond" and "Actual Destination State = Virginia".
3. Divide the Richmond total by the Virginia state total to establish the regional share.

**Pre-change caveat:** When analyzing data prior to July 2024, any city-level data must be heavily caveated as an "Affiliate City Proxy," which may overcount Richmond if agencies placed families in surrounding counties.

## Richmond provider landscape — Who does what, and where capacity likely sits
Richmond is served by a mix of official federal resettlement agencies and specialized community integration organizations. While the Office of Refugee Resettlement (ORR) lists the official R&P affiliates [5], local NGOs provide critical wraparound support.

| Organization | Role & Programs | Contact / Location | Capacity Notes |
| :--- | :--- | :--- | :--- |
| **Commonwealth Catholic Charities (CCC)** [4] [5] | Official R&P Agency. Provides R&P, Matching Grant, RSS, and Unaccompanied Refugee Minor (URM) foster care. | 1601 Rolling Hills Dr, Richmond, VA. 804-285-5900 | Largest immigrant service org in VA; exact capacity requires direct request. |
| **International Rescue Committee (IRC)** [2] [5] | Official R&P Agency. Provides R&P, employment services, education, and integration support. | Richmond, VA. 804-308-9144 | Welcomed 2,000 refugees in its first 10 years; exact current capacity requires direct request. |
| **ReEstablish Richmond** [3] | Community Integration NGO (Non-R&P). Connects refugees to resources, builds community, and fosters self-sufficiency. | Richmond, VA | Acts as a vital post-R&P support network; relies on volunteer mobilization. |

**Key Takeaway:** CCC and IRC are the gatekeepers for initial arrival and federal funding pathways, while ReEstablish Richmond fills critical long-term integration gaps. Public capacity figures (exact "slots" per year) are not published and require direct outreach.

## Origin countries and service design — Language, health, and jobs
Virginia's refugee demographics are heavily influenced by recent humanitarian crises, requiring tailored service design. Federal reporting highlights Virginia as a top destination for Afghan allies following the 2021 evacuation [18]. Additionally, the state serves ongoing flows of Ukrainian humanitarian parolees, who are eligible for ORR-funded services [6].

This origin mix dictates specific operational needs:
* **Language Access:** High demand for Dari, Pashto, and Ukrainian interpretation services.
* **Health Services:** Need for trauma-informed mental health support, particularly for allied Afghan veterans [16].
* **Employment:** Focus on credential transfer and skills recertification for professionals arriving from these regions.

## The first 90 days and beyond — Program timelines and handoffs
The federal resettlement framework operates on strict timelines. Failure to transition clients smoothly from initial reception to long-term support programs risks severe economic instability.

| Program | Administering Body | Timeline | Core Services & Objectives |
| :--- | :--- | :--- | :--- |
| **Reception & Placement (R&P)** [19] [1] | Dept. of State (PRM) | **Day 0 to 90** | Airport reception, initial housing, basic furnishings, school registration, SSN application, and initial medical appointments. |
| **Matching Grant (MG)** [7] | HHS (ORR) | **Enroll within 31 days** | Alternative to public cash assistance. Focuses on rapid employment, case management, and achieving self-sufficiency within **240 days**. |
| **Refugee Support Services (RSS)** [14] | HHS (ORR) via State | Up to 5 years | Employability assessment, job placement, English language training, and barrier removal (childcare, translation). |
| **RCA / RMA** [6] | HHS (ORR) via State | Varies | Refugee Cash Assistance and Refugee Medical Assistance for those not eligible for standard TANF/Medicaid. |

**Key Takeaway:** The transition from R&P to MG/RSS is the most critical juncture. Service providers must execute warm handoffs within the first 30 days to ensure refugees do not miss the 31-day Matching Grant enrollment window.

## ORR/VDSS information on Virginia — What’s publicly available
At the federal level, ORR provides a public directory of local affiliates by city [5] and broad program guidelines [7] [14]. At the state level, the VDSS Office of New Americans (ONA) acts as the State Refugee Coordinator. ONA administers $55,522,000 annually in non-general funds to support eight federally funded refugee programs [6]. 

ONA partners with over 20 stakeholders and oversees funding for 7 direct services programs across 13 office locations statewide [15]. While ONA reports detail budget allocations, expenditures, and total clients served statewide (e.g., 5,499 individuals served with employment services in FY2022) [16], they do not publish granular, city-level arrival counts or agency-specific capacity limits.

## Data gaps and how to close them
Several critical data points are not available in public dashboards and require specific outreach strategies.

| Data Gap | Likely Data Holder | Recommended Action / Method | Effort Level |
| :--- | :--- | :--- | :--- |
| **Agency R&P/MG Capacity & Projections** | CCC/IRC Richmond; VDSS ONA | Direct request to agency directors or FOIA request to VDSS ONA. | Medium |
| **Richmond Monthly Arrivals (Pre-July 2024)** | RPC Archives [12] | Scrape historical PDFs using "Affiliate City" as a proxy, heavily caveating the methodology. | Medium |
| **RMA (Medical Assistance) Utilization** | Dept. of Medical Assistance Services (DMAS) | Data sharing agreement or FOIA (ONA explicitly notes DMAS tracks this) [6]. | Medium |

## Hackathon-ready population estimates
For hackathon teams needing immediate, defensible numbers for demos, transparency regarding sources and definitions is vital. Teams should use the following scaffolding:

**Option A (Strict Federal Counts):**
* Cite the exact Virginia refugee totals from the RPC "Arrivals by State and Nationality" PDFs for FY2021–FY2025 [12].
* Calculate the Richmond share using the "Actual Destination City" metric available from July 2024 onward [8] [9] [10].

**Option B (Broader Contextual Demo):**
* State that Virginia was the 4th largest resettlement state in FY2022, receiving 1,872 refugees and SIVs [1].
* Pair this with current-year (FY2026 MTD) refugee totals [9] and SIV totals [13].
* **Mandatory Banner:** Always include a disclaimer noting the July 2024 methodology change from "Affiliate City" to "Actual Destination City."

## Terminology and caveats — Preventing apples-to-oranges errors
When building dashboards or reports, mixing immigration statuses will skew data and misrepresent funding eligibility. 
* **"Refugees" vs. "ORR-Eligible":** RPC arrival reports strictly count USRAP refugees [11]. However, VDSS/ONA programs serve a broader "ORR-eligible" population, which includes Asylees, Cuban/Haitian Entrants, SIVs, Afghan/Ukrainian Humanitarian Parolees, and Trafficking Victims [6]. 
* **SIV Separation:** Afghan and Iraqi SIVs are tracked in entirely separate RPC reports [13].
* **Secondary Migration:** Federal arrival data tracks *initial* resettlement. It does not account for refugees who move to Richmond from other states after their initial 90-day R&P period.

## Coordination with schools and youth services
Refugee arrivals place specific, sustained demands on local school systems. In FY2022, the Virginia Refugee Student Achievement Project (VRSAP) utilized 21 school liaisons statewide to support 1,432 newly arrived, refugee-eligible children [16]. 

Furthermore, Virginia is one of only 15 states providing comprehensive Unaccompanied Refugee Minor (URM) foster care services. In FY2022, the URM program served 76 youth statewide, with CCC in Richmond acting as one of the two licensed child-placing agencies for the state [6] [16]. Stakeholders must coordinate early with Richmond Public Schools (RPS) regarding enrollment surges, language access, and trauma-informed support, while engaging CCC directly on URM placements.

## Appendices

### Source Index
| Source | Description | Usage Notes |
| :--- | :--- | :--- |
| **RPC Admissions & Arrivals** [11] [12] | Federal hub for monthly arrival PDFs. | Use for state/city arrival volumes. |
| **RPC FY2024/2026 PDFs** [8] [9] [10] | State and Nationality reports. | Source for "Actual Destination City" data. |
| **PRM R&P Fact Sheet** [1] | Overview of 30-90 day services. | Source for FY22 state rankings. |
| **ORR Program Pages** [7] [14] | MG and RSS guidelines. | Use for program timelines (e.g., 31-day MG rule). |
| **VDSS/ONA RD954 (2025)** [6] | State legislative report. | Source for $55.5M budget and eligibility rules. |
| **VDSS/ONA Annual Report (2023)** [16] | Historical state report. | Source for VRSAP and URM youth metrics. |

### Key Contacts
* **State Refugee Coordinator:** Seyoum Berhe, Director, Office of New Americans (Seyoum.Berhe@dss.virginia.gov) [6].
* **Commonwealth Catholic Charities (Richmond):** 1601 Rolling Hills Drive, Richmond, VA 23229; 804-285-5900 [4].
* **International Rescue Committee (Richmond):** 804-308-9144 [5].

## References

1. *The Reception and Placement (R&P) Program*. https://www.rpc.state.gov/documents/FY%202023%20Reception%20&%20Placement%20Fact%20Sheet.pdf
2. *Richmond, VA | The IRC*. https://www.rescue.org/united-states/richmond-va
3. *ReEstablish Richmond*. https://www.reestablishrichmond.org/
4. *Refugee Resettlement  | Commonwealth Catholic Charities | Virginia| Richmond | Roanoke | Hampton Roads*. https://www.cccofva.org/refugees
5. *State of Virginia - Programs and Services by City | The Administration for Children and Families*. https://acf.gov/orr/contact-information/state-virginia-programs-and-services-locality
6. *Refugee Assistance Programs in Virginia – December 1, 2025*. https://rga.lis.virginia.gov/Published/2025/RD954/PDF
7. *Matching Grant Program | The Administration for Children and Families*. https://acf.gov/orr/programs/refugees/matching-grants
8. *Refugee Arrivals by State and Nationality - Fiscal Year 2024*. https://www.rpc.state.gov/documents/Refugee%20Arrivals%20by%20State%20and%20Nationality%20as%20of%2030%20Sep%202024.pdf
9. *Refugee Arrivals by State and Nationality - Fiscal Year 2026*. https://www.rpc.state.gov/documents/Refugee%20Arrivals%20by%20State%20and%20Nationality%20as%20of%20January%2031,%202026.pdf
10. *Refugee Arrivals by State and Nationality - Fiscal Year 2024*. https://www.rpc.state.gov/documents/Refugee%20Arrivals%20by%20State%20and%20Nationality%20as%20of%2031%20Jul%202024.pdf
11. *Admissions & Arrivals  — Refugee Processing Center*. https://www.rpc.state.gov/admissions-and-arrivals/
12. *Archives  — Refugee Processing Center*. https://www.rpc.state.gov/archives/
13. *Amerasian and SIV Arrivals by Nationality and State*. https://www.rpc.state.gov/documents/Amerasian%20and%20SIV%20Arrivals%20by%20Nationality%20and%20State%20as%20of%20December%2031,%202025.pdf
14. *Refugee Support Services | The Administration for Children and Families*. https://acf.gov/orr/programs/refugees/refugee-support-services
15. *2025 Office of New Americans Report*. https://rga.lis.virginia.gov/Published/2026/RD16/PDF
16. *Virginia Department of Social Services Annual Report on the ...*. https://rga.lis.virginia.gov/Published/2023/RD240/PDF
17. *Refugee Arrivals by State and Nationality*. https://www.rpc.state.gov/documents/Refugee%20Arrivals%20by%20State%20and%20Nationality%20as%20of%2031%20Oct%202025.pdf
18. *FY 2024 USRAP Report to Congress_FINAL*. https://www.rpc.state.gov/documents/FY-2024-USRAP-Report-to-Congress_FINAL-Accessible-11.02.2023.pdf
19. *Reception and Placement - United States Department of State*. https://2017-2021.state.gov/refugee-admissions/reception-and-placement/