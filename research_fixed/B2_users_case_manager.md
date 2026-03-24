
# Richmond Refugee Case Managers: Time, Tools, and Trust—A Persona Built for Action

## Executive Summary
The Richmond-area refugee and immigrant case manager operates in a high-stakes, logistics-heavy environment where administrative burdens frequently crowd out direct client care. Tasked with navigating complex resettlement timelines and fragmented local resources, these professionals manage caseloads of up to 40 families while juggling strict privacy regulations and multilingual communication barriers. This persona brief synthesizes evidence from local job requirements, national time-use studies, and technology evaluations to define the operational reality of case managers at organizations like the YMCA, ReEstablish Richmond, and Commonwealth Catholic Charities (CCC). 

## The Day-to-Day Role and Caseload Reality
A refugee case manager's role is highly time-bound and outcomes-driven. At organizations like the YMCA of Greater Richmond, International Rescue Committee (IRC), and CCC, case managers are responsible for comprehensive needs assessments, securing safe housing, school enrollment, and connecting clients to state benefits (SNAP, Medicaid, WIC, SSI) [1] [2] [3]. 

Caseloads are demanding. A YMCA International Casework Manager is directly responsible for up to 40 cases at a time, with strict deliverables: core services must be completed within 30 days, and Match Grant (MG) employment services within 240 days [2]. ReEstablish Richmond case managers focus heavily on overcoming integration barriers, specifically targeting transportation, English language learning, and employment navigation [4] [5]. The day-to-day reality involves high task-switching between arranging interpretation, providing physical transportation to medical or court appointments, and conducting monthly follow-ups to track self-sufficiency plans [1] [2].

## Time Allocation and Administrative Burden
Despite the human-centric nature of social work, direct client interaction makes up a minority of a case manager's week. 

* **The Evidence:** Time-use studies of caseworkers reveal that workers spend 60% to 70% of their time on case-related activities, but only 20% to 35% of their time is spent in direct client contact [6]. A comprehensive workload study in West Virginia modeled that, after accounting for required breaks and leave, caseworkers have approximately 59% of their paid hours available for case-related tasks [7]. 
* **The Inference:** For a 40-hour workweek, a Richmond refugee case manager likely spends only 8 to 14 hours face-to-face with clients. The remaining 26 to 32 hours are consumed by documentation, travel, coordinating referrals, and navigating directories. 

| Time Category | Estimated Weekly Allocation | Key Activities | Source Evidence |
| :--- | :--- | :--- | :--- |
| **Direct Client Contact** | 20% - 35% (8-14 hours) | Intake, assessments, home visits, accompaniment to appointments. | [6] |
| **Coordination & Referrals** | 15% - 25% (6-10 hours) | *Inference:* Searching directories, calling providers, scheduling interpreters, tracking outcomes. | Derived from [6] [7] |
| **Documentation & Admin** | 25% - 35% (10-14 hours) | Case notes, compliance reporting, updating case management systems. | [6] [7] |
| **Non-Case/Leave/Breaks** | ~41% (16 hours) | Staff meetings, training, PTO, required breaks. | [7] |

*Key Takeaway:* Administrative and coordination tasks consume the bulk of a case manager's capacity. Tools that streamline referrals and automate documentation offer the highest potential for reclaiming time for direct client care.

## Information Needs and Gaps
Case managers suffer from an abundance of directories but a scarcity of actionable, real-time information. 

Richmond has robust resource databases: 211 Virginia maintains over 19,000 programs and offers interpretation in over 150 languages [8] [9]. Help1RVA hosts over 1,800 local programs, relying on agencies to self-claim and update their services, hours, and language availability [10]. However, user research on community resource referral systems (CRRS) reveals that simply listing a resource is insufficient. Case managers need to know specific intake barriers, real-time eligibility windows, and whether a provider actually has the language capacity they advertise [11]. When a referral results in a missed phone call or a language mismatch, the directory fails the user [11].

## Technology Landscape and Pain Points
Case managers currently navigate a fragmented technology stack, leading to duplicated efforts and data silos.

| Technology Category | Tools Used Locally | Strengths | Pain Points & Limitations | Sources |
| :--- | :--- | :--- | :--- | :--- |
| **Case Management Systems** | Bonterra (Apricot), Salesforce | Centralizes client data, tracks program outcomes, generates funder reports. | High setup costs, manual data entry, often lacks seamless external referral tracking. | [12] [13] |
| **Resource Directories** | 211 Virginia, Help1RVA | Massive scale, free to use, covers basic social determinants of health. | Static data; lacks closed-loop outcome tracking; provider capacity often outdated. | [9] [10] [11] |
| **Closed-Loop Networks** | Unite Us (Unite Virginia) | Tracks if services were delivered; integrates clinical and social data. | Requires network buy-in; can miss the nuanced "seeker experience" (e.g., barriers faced). | [14] [11] |
| **Client Communication** | WhatsApp, Phone calls | High adoption among immigrant/refugee populations; accessible. | Often disconnected from the official case record; privacy/consent tracking is manual. | [15] [16] |

*Key Takeaway:* The primary pain point is the lack of interoperability. Case managers find resources in Help1RVA, communicate with clients via WhatsApp, and manually log the outcomes in Apricot. 

## Coordination Efficiency: Quantifying the Opportunity
Based on the time allocation data, case managers spend an estimated 6 to 10 hours per week on coordination and referrals. Implementing closed-loop referral systems has been proven to drive massive efficiencies. For example, Ballad Health's use of the Unite Virginia network resulted in a 16.2% reduction in emergency department utilization and saved an estimated $68.80 per member per month by effectively tracking and closing the loop on social care referrals [14]. 

*Inference:* If a unified tool could pre-verify provider requirements, bundle referrals (e.g., housing + food + interpreter), and automate status updates, it could conservatively reduce coordination time by 20% to 30%. This would save 1.5 to 3 hours per week per case manager, directly increasing capacity for client-facing work.

## Trust, Privacy, and Data Sharing
Trust and privacy are binding constraints, governed by strict federal and ethical guidelines. Case managers cannot simply share client profiles across networks without granular consent.

| Data Constraint | Governing Body / Policy | Rules for Case Managers | Source |
| :--- | :--- | :--- | :--- |
| **Personally Identifiable Information (PII)** | Office of Refugee Resettlement (ORR) Policy Letter 17-02 | Cannot release PII without consent except for direct program administration. Language and ethnicity become PII when combined with identifiers. | [17] |
| **Informed Consent & Comprehension** | NASW Code of Ethics (1.03) | Must use clear language, provide interpreters if clients are not literate in English, and explain risks/limits of sharing data. | [18] |
| **Minimum Necessary Disclosure** | NASW Code of Ethics (1.07) | Disclose only the least amount of confidential information necessary to achieve the desired referral purpose. | [18] |

*Key Takeaway:* Any coordination tool must feature granular, service-by-service consent mechanisms, available in the client's native language, ensuring that only the "minimum necessary" data is transmitted to external partners.

## Success Definition
From the perspective of a Richmond refugee case manager, a successful coordination tool is not defined by the *volume* of referrals made, but by the *speed and reliability* of successful connections. Success looks like:
1. **Fewer Dead-Ends:** Knowing a provider's exact intake requirements and language capacity *before* sending the client.
2. **Closed-Loop Visibility:** Receiving automated updates when a client is accepted, scheduled, or served, eliminating the need for manual follow-up calls [14] [11].
3. **Seamless Communication:** The ability to securely message clients via their preferred channels (like WhatsApp) with automated translation, while keeping records compliant [15] [16].

***

## Source Citations
* [1] IRC - International Rescue Committee. "Refugee Support Services Case Manager."
* [2] YMCA. "International Casework Manager-MG Job Description."
* [8] 211 Virginia. "2020-2021 Annual Report."
* [9] United Way of Henry County & Martinsville. "About 2-1-1 VIRGINIA."
* [10] YMCA of Greater Richmond. "Social Needs Navigation - Help1RVA."
* [4] ReEstablish Richmond. "Employment Navigation."
* [5] ReEstablish Richmond. "Our Programs."
* [12] Bonterra. "Apricot Software | Case management software for nonprofits."
* [13] Untapped Solutions. "Untapped vs Salesforce & Bonterra (Apricot) - CRM Comparison."
* [3] Commonwealth Catholic Charities. "Refugee Resettlement."
* [17] The Administration for Children and Families. "Data Sharing | Policy Letter 17-02."
* [18] National Association of Social Workers (NASW). "Social Workers' Ethical Responsibilities to Clients."
* [6] SDSU. "Research Summary: Caseload Standards & Weighting."
* [7] West Virginia Legislature. "Workload Study Report."
* [14] Unite Us. "How Ballad Health Saves $68.80 PMPM by Reducing ED Utilization with Unite Us."
* [11] PMC. "Getting Inside Closed-Loop Referrals: Exploring the Patient Experience..."
* [15] Immigration Policy Lab. "One Year Later: How IPL Used WhatsApp for Outreach Surveys."
* [16] Joint Data Center. "Automated Chat Application Surveys Using WhatsApp."

***

## Top 3 features a case manager coordination tool should have based on this research.

1. **Closed-loop referrals with outcomes and barrier capture:** The tool must track accepted, scheduled, served, and unresolved statuses, while documenting specific barriers (e.g., missing requirements, interpreter mismatches) to measure true time-to-service. Integrating with existing networks like Unite Virginia (Unite Us) is highly recommended [14] [11].
2. **Multilingual, consent-centered communication (including WhatsApp integration):** The platform must support granular, purpose-specific consent and role-based access. It should feature templated, multilingual messages and reminders via SMS/WhatsApp, storing consent artifacts directly in the case record to comply with NASW and ORR guidelines [17] [18] [15] [16].
3. **Provider-verified directory overlays:** To reduce dead-ends and speed up referrals, the tool should layer up-to-date intake requirements, interpreter/language capacity, operating hours, and last-verified timestamps over existing databases like 211 Virginia and Help1RVA [8] [9] [10] [11].

## References

1. *Refugee Support Services Case Manager | IRC - International Rescue Committee*. https://www.impactpool.org/jobs/728661
2. *Job Title Employer/ Agency Job Description 2024-02-28*. https://www.uh.edu/socialwork/alumni/career-services/job-board/ymca-2-28-2024-international-casework-manager-mg.pdf
3. *Refugee Resettlement | Commonwealth Catholic Charities | Virginia| Richmond | Roanoke | Hampton Roads*. https://www.cccofva.org/refugees
4. *NN: Employment Navigation — ReEstablish Richmond*. https://www.reestablishrichmond.org/employment-navigation
5. *Our Programs — ReEstablish Richmond*. https://www.reestablishrichmond.org/our-programs
6. *Research Summary: Caseload Standards & Weighting...*. https://theacademy.sdsu.edu/wp-content/uploads/2021/10/CWDS-Research-Summary_Caseload-Standards-and-Weighting.pdf
7. *Workload Study Report*. https://www.wvlegislature.gov/legisdocs/reports/agency/H01_CY_2022_15696.pdf
8. *2020-2021 Annual Report*. https://www.yourunitedway.org/wp-content/uploads/2021/11/211-VA-Annual-Report-FINAL-102821.pdf
9. *2-1-1 Virginia | United Way of Henry County & Martinsville*. https://www.unitedwayofhcm.org/211
10. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/
11. *Getting Inside Closed-Loop Referrals: Exploring the Patient Experience of Finding and Connecting to Social Care With a Community Resource Referral System Using a Community-Based Participatory Approach - PMC*. https://pmc.ncbi.nlm.nih.gov/articles/PMC12052525/
12. *Apricot Software | Bonterra*. https://www.bonterratech.com/product/apricot
13. *Untapped vs Salesforce & Bonterra (Apricot) - CRM Comparison*. https://untappedsolutions.com/comparison
14. *How Ballad Health Saves $68.80 PMPM by Reducing ED Utilization with Unite Us*. https://uniteus.com/case-study/reducing-ed-utilization-at-ballad-health/
15. *One Year Later: How IPL Used WhatsApp for Outreach Surveys - Immigration Policy Lab*. https://immigrationlab.org/2021/09/20/one-year-later-how-ipl-used-whatsapp-for-outreach-surveys/
16. *Automated Chat Application Surveys Using WhatsApp*. https://www.jointdatacenter.org/wp-content/uploads/2022/01/Automated-Chat-Application-Surveys-Using-WhatsApp.pdf
17. *Data Sharing | The Administration for Children and Families*. https://acf.gov/orr/grant-funding/data-sharing
18. *Social Workers' Ethical Responsibilities to Clients*. https://www.socialworkers.org/About/Ethics/Code-of-Ethics/Code-of-Ethics-English/Social-Workers-Ethical-Responsibilities-to-Clients