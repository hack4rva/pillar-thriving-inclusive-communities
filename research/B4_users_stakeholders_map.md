# Closing the Last-Mile Gap: A Richmond Stakeholder Map to Streamline Immigrant and Refugee Service Access

## Executive Summary
Richmond's immigrant and refugee service ecosystem is rich in resources but fragmented by parallel referral platforms and complex eligibility rules. Two dominant referral pathways exist: Help1RVA offers an open directory of over 1,800 programs supported by YMCA navigators [1], while Unite Virginia (Unite Us) provides a closed-loop system that has served 85,174 clients statewide [2]. A successful hackathon prototype must bridge these systems rather than force a winner-take-all approach. 

The City's Office of Immigrant and Refugee Engagement (OIRE) acts as a critical force-multiplier, providing free navigation, legal clinics, and a citywide Language Access Plan [3] [4]. However, downstream services face severe bottlenecks: healthcare access at clinics like CrossOver requires strict eligibility (Medicaid or uninsured at/below 200% FPL) and can entail wait times of "several weeks" [5], while legal aid is highly constrained by scope and capacity [6] [7]. To build a viable solution, hackathon teams must design for triage, embed explicit eligibility expectations, and prioritize language equity by co-designing with trusted community anchors like ReEstablish Richmond and the Sacred Heart Center.

## Purpose and Scope
This report delivers a practical, Richmond-specific stakeholder map designed to accelerate immigrant and refugee service access. By aligning digital platforms, human navigators, and community anchor organizations, hackathon teams can identify exactly who to build for, who to partner with, and how to navigate the operational realities of Richmond's safety net.

## Ecosystem Snapshot: Dual Platforms and Municipal Navigation
Richmond's access system is decentralized but alignable through dual-platform support and municipal convening. The landscape is defined by two major technological infrastructures and a strong city-led navigation effort. Help1RVA operates as a collaborative initiative bringing together over 1,800 local programs into a free, easy-to-use platform [1]. Conversely, the Unite Virginia network focuses on secure, electronic closed-loop referrals, boasting 174,229 needs identified and 94,470 referrals sent across the state [2]. Bridging these platforms is the City of Richmond's OIRE, which provides direct navigation services to connect newcomers to essential resources based on needs assessments [3].

## Stakeholder Profiles Table
The following table maps the 10 critical stakeholder categories involved in Richmond's immigrant and refugee service ecosystem, detailing their roles, motivations, and capacity to engage in a hackathon prototype.

| Stakeholder | Role | Interests | Concerns | Hackathon Participation Potential |
| :--- | :--- | :--- | :--- | :--- |
| **1. Immigrant & Refugee Residents** | Primary beneficiaries seeking housing, jobs, health, and legal aid. | Quick access to services in their native language; clear eligibility rules. | Data privacy, deportation risks, language barriers, and long wait times. | **Medium**: Best engaged through trusted anchor orgs for user testing and feedback. |
| **2. Nonprofit Case Managers** | Frontline navigators connecting clients to the safety net. | Streamlined referral workflows; eliminating double data entry across platforms. | Platform fatigue; sending clients to dead-end referrals with full waitlists. | **High**: Excellent candidates for workflow validation and UI/UX testing. |
| **3. Trusted Community Orgs** (Sacred Heart, AASoCV) | Cultural brokers and community hubs providing holistic support [8] [9]. | Community empowerment; culturally competent care; holistic family support. | Capacity limits; erosion of community trust if tech solutions fail to deliver. | **Medium**: Crucial for validating language and cultural appropriateness. |
| **4. City of Richmond Staff** (OIRE, DSS) | System conveners, policy makers, and emergency aid providers [3]. | Language access compliance; equitable service distribution; cross-sector coordination. | Resource constraints; maintaining updated directories of services. | **High**: Can provide policy guidance, language tools, and pilot agency recruitment. |
| **5. Workforce Programs** (VCW, CRWP, Reynolds) | Providers of ESL, job training, and WIOA-funded career services [10] [11] [12]. | High job placement rates; successful ESL-to-employment transitions. | Strict federal eligibility barriers (e.g., WIOA requirements); funding cuts. | **Medium**: Valuable for aligning prototype metrics with fundable WIOA outcomes. |
| **6. Help1RVA Operators** (YMCA Navigators) | Platform maintainers and human navigators providing 48-hour callbacks [1]. | Broad platform adoption; accurate and updated program listings from CBOs. | Outdated directory information; unresponsiveness from listed agencies. | **Very High**: Key operational partners for testing intake-to-navigator workflows. |
| **7. FindHelp / UniteUs Reps** | Technology infrastructure providers for open and closed-loop referrals [1] [2]. | Network growth; demonstrating impact through data and insights. | CBO churn; data silos; resistance to adopting new tech workflows. | **Low/Medium**: Useful for API documentation and integration advice. |
| **8. Legal Aid Orgs** (LAJC, CVLAS) | Defenders of civil and immigration rights [6] [7]. | Targeted, highly qualified referrals; systemic policy reform. | Overwhelming demand; receiving out-of-scope referrals (e.g., CVLAS cannot take immigration cases) [7]. | **Medium**: Essential for designing accurate legal triage decision trees. |
| **9. Healthcare Providers** (CrossOver, Daily Planet) | Safety net clinics providing care to uninsured and Medicaid populations [5] [13]. | Matching eligible patients to available appointments; reducing no-shows. | Severe capacity limits; long wait times for new uninsured patients [5]. | **Low**: Limited weekend capacity, but their eligibility rules must be hardcoded. |
| **10. Potential Champions** (ReEstablish, YMCA) | Ecosystem leaders driving language equity and scalable navigation [1] [14]. | Sustainable, scalable solutions that directly remove barriers for newcomers. | Hackathon "vaporware" that doesn't survive past the weekend. | **Very High**: Core partners for momentum, data access, and post-weekend pilots. |

*Takeaway: Hackathon teams must design for the case managers and YMCA navigators who bear the administrative burden, while relying on OIRE and ReEstablish Richmond to ensure language and cultural equity for the end-users.*

### Top 3 Stakeholders a Hackathon Team Should Try to Reach During the Weekend
1. **YMCA Social Needs Navigators (Help1RVA Operators)**: They are the human engine behind the Help1RVA platform. Understanding their 48-hour callback workflow and how they utilize translation services [1] is critical for building a realistic prototype.
2. **ReEstablish Richmond**: As a premier hub for newcomer navigation and language access advocacy (having successfully translated the DMV manual into Kinyarwanda) [14], they can provide immediate reality checks on language equity and user trust.
3. **City of Richmond OIRE Staff**: OIRE hosts monthly networking groups with regional partners and manages the city's Language Access Plan [3] [4]. They are the ultimate convener and can validate if a prototype aligns with municipal equity goals.

## Platform and Navigation Landscape: Bridging the Divide
Richmond's referral ecosystem requires supporting both open-directory and closed-loop systems, integrated with human navigators for complex needs.

| Channel | Operator | Coverage & Cost | Referral Type & Data | Notable Numbers |
| :--- | :--- | :--- | :--- | :--- |
| **Help1RVA (FindHelp)** | YMCA of Greater Richmond | 1,800+ local programs; Free | Open directory; self-search or navigator-assisted | Organizations can easily claim and update their own program listings [1]. |
| **Unite Virginia** | Unite Us | Statewide; Free for CBOs [2] | Closed-loop coordinated care; secure electronic referrals | 85,174 clients served; 94,470 referrals sent [2]. |
| **YMCA Navigators** | YMCA of Greater Richmond | Short-term assistance; Free | Human-in-the-loop navigation; multilingual | Navigators contact users within 48 hours of form submission [1]. |

*Takeaway: A successful prototype should not force agencies to choose a platform; instead, it should default to data-light self-search via Help1RVA, escalating to Unite Us or YMCA navigators only when closed-loop tracking or human intervention is required.*

## OIRE as the Municipal Convener for Language Equity
The City of Richmond's Office of Immigrant and Refugee Engagement (OIRE) is the practical gateway for cross-sector coordination. OIRE provides free navigation services, connecting customers to community resources based on needs assessments [3]. They also host critical interventions, including immigration legal clinics in partnership with private law firms, and Medicaid application assistance [3]. 

Crucially, OIRE manages the city's Language Access Plan, ensuring equal access to city services regardless of English proficiency [4]. They provide free interpretation and translation services, and operate the "iSpeak Richmond" initiative, which includes language identification guides and tools for Limited English Proficiency (LEP) residents [4]. 

## Workforce Pathways: Turning ESL Progress into Employment
Pairing ESL placement with workforce co-enrollment is essential to shorten the time to a newcomer's first job. 

| Provider | Entry Criteria & Focus | Services & Supports | Outcomes & Scale |
| :--- | :--- | :--- | :--- |
| **Capital Region Workforce Partnership (CRWP)** | Eight-jurisdiction consortium managing WIOA funds [11]. | Adult, Dislocated Worker, and Youth services; career planning [11]. | Welcomed over 28,000 jobseekers; 88% job placement for adults [11]. |
| **Virginia Career Works (VCW) Capital** | WIOA eligibility; English language learners qualify under barriers [12]. | Occupational skills training, paid work experiences, supportive services [12]. | Fully funded by a $4.04 million DOL award [12]. |
| **Reynolds Community College ESL** | Placement testing required (writing, reading, oral) [10]. | Day/evening classes; 15-week semesters; financial aid available [10]. | Takes one semester to two years to complete coursework [10]. |

*Takeaway: Hackathon teams should build an ESL-to-WIOA "bridge" flow that connects Reynolds ESL students directly to VCW Capital's supportive services, leveraging English Learner status as a qualifying barrier for WIOA funds.*

## Legal Aid Triage: Matching Needs to the Right Door
Immigration-specific case capacity is highly limited in Richmond. Triage and expectation-setting are required to reduce dead-end referrals.

| Organization | Focus Areas | Eligibility & Scope | Capacity Signals |
| :--- | :--- | :--- | :--- |
| **Legal Aid Justice Center (LAJC)** | Immigration rights, fighting detention, immigrant youth [6]. | Individual representation for a limited number of immigrants facing removal [6]. | Hosts two law student clinics; accepts a limited number of cases based on capacity [6]. |
| **Central Virginia Legal Aid Society (CVLAS)** | Civil legal services (housing, consumer debt, family) [15]. | Income up to 187.5% FPL; **Does not serve immigrants or prisoners** [7]. | Helped 15,968 people through services/education; interpreters available [15] [7]. |
| **OIRE Legal Clinics** | Immigration Law and Tax Law [3]. | City residents [3]. | Hosted in partnership with private law firms; requires appointments [3]. |

*Takeaway: A prototype must include a strict legal decision tree. Sending an immigration case to CVLAS will result in an automatic rejection [7], wasting time and eroding trust. Users must be routed to LAJC or OIRE clinics for immigration-specific needs.*

## Health Access: Eligibility and Wait-Time Friction
Health referrals break down when eligibility and wait times are not transparent. CrossOver Healthcare Ministry serves patients who are eligible for Medicaid or are uninsured with a household income at or below 200% of the federal poverty level [5]. Crucially, CrossOver explicitly warns that appointments for uninsured patients are in high demand, and "it may be several weeks before a new patient/financial screening appointment is available" [5]. Conversely, Daily Planet Health Services operates as a Federally Qualified Health Center (FQHC) with a mandate that "ALL should have access to quality health services regardless of their financial, housing, or insurance status," and explicitly provides language assistance [13]. 

Hackathon teams must embed FPL thresholds and estimated wait-time expectations directly into resource cards to prevent failed referrals and manage user expectations.

## Community Anchors and Cultural Brokers
Adoption of any tech solution depends on champions embedded in the community. The Sacred Heart Center is a vital hub, offering adult education and youth programs specifically tailored to connect Latino families with tools to thrive [8]. The Asian American Society of Central Virginia (AASoCV) serves as the voice of the Asian community, hosting cultural events and fostering community empowerment [9]. ReEstablish Richmond focuses on equipping newcomers through culturally sensitive support, notably advocating for systemic improvements like language access at the DMV, where limited English proficiency causes significant delays in obtaining driver's licenses [14].

## Hackathon Champions and Weekend Engagement Plan
To secure momentum, teams should focus on three high-leverage champions:
1. **ReEstablish Richmond**: Engage them to validate referral workflows and utilize their primary-language resources (e.g., translated manuals) [14].
2. **YMCA of Greater Richmond**: Map the prototype's output directly to the YMCA Social Needs Navigators' intake forms to ensure the 48-hour callback SLA can be met [1].
3. **City OIRE**: Utilize their iSpeak Richmond tools and Language Access Plan guidelines to ensure the prototype meets municipal equity standards [4].

## Risks, Failure Cases, and Mitigations
Designing for the "messy middle" requires anticipating fragmentation and friction:
* **Platform Duplication**: Dual platforms create admin load. *Mitigation*: Design a data-light intake that defaults to Help1RVA self-search, only collecting PII when a user explicitly opts into a Unite Us closed-loop referral [1] [16].
* **Language Friction**: DMV language gaps can delay licenses for a year [14]. *Mitigation*: Ship the prototype Spanish-first, integrate OIRE's iSpeak tools [4], and prioritize transportation and legal pathways where language friction is highest.
* **Clinic Wait-Times**: Referring a patient to CrossOver may result in a multi-week wait [5]. *Mitigation*: Always provide a backup FQHC recommendation (like Daily Planet) [13] alongside expectation-setting text.

## Implementation Playbook (Weekend)
Ship a minimal but coherent flow that proves reduced time-to-service:
1. **Bilingual Intake**: Utilize OIRE language standards [4].
2. **Triage & Consent**: Ask basic eligibility questions (FPL, insurance, immigration status) without storing PII initially.
3. **Routing**: Match simple needs to Help1RVA open directory [1]; escalate complex needs to YMCA Navigators (48-hour callback) [1] or Unite Us [16].
4. **Expectation Setting**: Display wait times and eligibility rules clearly before the user clicks "connect."

## Measurement and Sustainability
To ensure the prototype survives post-hackathon, instrument it to capture metrics that funders and networks reward. Track time-to-contact, referral closure rates, and documented language supports used. Align these metrics with the Capital Region Workforce Partnership's benchmarks (e.g., job placement and retention rates) [11] and Unite Us Insights [2]. CRWP is currently establishing a non-profit foundation to diversify funding beyond federal sources [11]; a prototype that proves it can efficiently route ESL learners into WIOA programs will be highly attractive to this new funding vehicle.

## Appendices: Key Links
* **Help1RVA**: help1rva.org [1]
* **Unite Virginia**: uniteus.com/networks/virginia [2]
* **OIRE Services**: rva.gov/immigrant-engagement/services [3]
* **Reynolds ESL**: reynolds.edu/get_started/esl/esl.html [10]
* **CrossOver Eligibility**: crossoverministry.org/patients/eligibility-2 [5]
* **LAJC Immigration**: justice4all.org/what-we-do/immigration [6]
* **CVLAS**: cvlas.org [15]

## References

1. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/
2. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/
3. *Services | Richmond*. https://www.rva.gov/immigrant-engagement/services
4. *Language Access | Richmond*. https://www.rva.gov/immigrant-engagement/language-access
5. *Eligibility Information | CrossOver Healthcare Ministry*. https://www.crossoverministry.org/patients/eligibility-2
6. *   
                        Immigration - Legal Aid Justice Center
                *. https://www.justice4all.org/what-we-do/immigration/
7. *VaLegalAid.org -  A guide to free and low cost civil legal information and services in Virginia*. https://www.valegalaid.org/organization/central-virginia-legal-aid-society-richmond-b
8. *Sacred Heart Center: Home*. https://shcrichmond.org/
9. *Asian American Society of Central Virginia – Asian American ...*. https://aasocv.org/
10. *English as a Second Language (ESL)  | Reynolds Community College*. https://www.reynolds.edu/get_started/esl/esl.html
11. *CAPITAL REGION WORKFORCE PARTNERSHIP*. https://henrico.gov/pdfs/finance/ApprovedBudgetFY26/CRWP%20-%20Approved%20FY26.pdf
12. *Virginia Career Works, Capital Region – Empowering Careers & Businesses*. https://vcwcapital.com/
13. *Page not found - Daily Planet Health Services*. https://www.dailyplanetva.org/our-services/
14. *Language Access — ReEstablish Richmond*. https://www.reestablishrichmond.org/language-access
15. *Central Virginia Legal Aid Society (CVLAS)*. https://cvlas.org/
16. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/get-help/richmond-city-resources/