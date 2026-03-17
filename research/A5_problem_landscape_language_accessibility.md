# Closing the Gap: Concrete Language Access Wins for Richmond’s Immigrant Communities

## Executive Summary

Richmond's immigrant and refugee populations face systemic barriers to accessing civic and health services, extending far beyond simple English proficiency. While the federal landscape shifted in 2025 with Executive Order 14224 designating English as the official language and revoking prior language access mandates, the legal floor remains intact: Title VI of the Civil Rights Act still prohibits national-origin discrimination for any entity receiving federal funds. Furthermore, health programs are bound by strict Section 1557 rules requiring human review of machine translations for vital content. 

For a hackathon team or civic tech initiative, the most effective intervention is not building new translation AI, but rather building seamless bridges to existing infrastructure. Richmond already contracts with 24/7 telephonic interpretation vendors supporting over 240 languages. The strategic priority is creating phone-first, low-literacy-friendly interfaces that route users to these existing human interpreters, while strictly avoiding unreviewed machine translation for any rights- or health-critical information.

## 1) Compliance Reality Check

Federal nondiscrimination law still requires meaningful access; only the guidance landscape has shifted. 

### Title VI applicability to Richmond City and nonprofits receiving federal funds
Title VI of the Civil Rights Act of 1964 prohibits discrimination on the basis of race, color, or national origin in any program or activity receiving federal financial assistance [1] [2]. This applies directly to the City of Richmond and any nonprofit organizations receiving federal grants. Failure to provide meaningful access to individuals with limited English proficiency (LEP) can constitute national origin discrimination [2].

| Entity Type | Federal Funding Status | Language Access Obligation |
| :--- | :--- | :--- |
| City of Richmond Agencies | Receives federal funds | Bound by Title VI and local Administrative Regulation 5.24 [1] [2] |
| Health Clinics & Hospitals | Receives HHS/Medicare/Medicaid | Bound by Title VI and Section 1557 of the ACA [3] [4] |
| Local Nonprofits | Receives federal grants (e.g., ORR) | Bound by Title VI nondiscrimination mandates [2] |

*Takeaway: Language access is not optional for federally funded entities, regardless of recent executive branch policy shifts.*

### EO 14224’s impact vs. ongoing obligations
On March 1, 2025, President Trump issued Executive Order 14224, designating English as the official language of the United States and revoking Executive Order 13166 (which had previously mandated federal agencies to improve LEP access) [5] [6]. The DOJ subsequently rescinded its 2002 LEP guidance [7] [8]. However, EO 14224 explicitly states it must be implemented consistent with applicable law [7] [6]. The City of Richmond has voluntarily chosen to uphold the principles of the rescinded EO 13166 and the DOJ's Four-Factor Analysis as best practices for structuring services and advancing equity [2].

### Section 1557 health programs: notices, coordinators, training, MT rules
The May 2024 final rule implementing Section 1557 of the Affordable Care Act outlines specific requirements for health programs [3]. Covered entities must not rely on unqualified adults or minors to interpret, except in extreme emergencies [3] [9]. Furthermore, if a covered entity uses machine translation for critical documents, those translations must be reviewed by a qualified human translator [3] [4].

## 2) Richmond’s Language Landscape

To effectively serve Richmond's LEP residents, services must target the languages actually spoken by recent arrivals.

### Refugee arrivals and likely languages
In the last five years, Richmond has welcomed over 3,500 refugees from countries including Afghanistan, Iraq, Syria, and the Democratic Republic of Congo [10]. 

| Origin Region/Country | Indicative Languages | Local Demand Signal |
| :--- | :--- | :--- |
| Latin America | Spanish | Meets the City's 5% translation threshold [2] |
| Afghanistan | Dari, Pashto | High recent refugee resettlement [10] |
| Middle East (Syria, Iraq) | Arabic | High recent refugee resettlement [10] |
| Democratic Republic of Congo | Swahili, Kinyarwanda | High recent refugee resettlement; local manual translated to Kinyarwanda [10] [11] |

*Takeaway: While Spanish is the most prominent, Arabic, Dari, Pashto, Swahili, and Kinyarwanda represent critical, fast-growing needs.*

### ACS and RPS data plan
The City of Richmond relies on American Community Survey (ACS) data and Richmond Public Schools (RPS) enrollment statistics to evaluate language services annually [2]. Spanish currently meets the 5% threshold requiring translation of vital documents [2].

## 3) What LEP Looks Like in Practice

Language needs intersect heavily with digital, phone, and in-person access capabilities.

### Phone and in-person interaction capacity
For many LEP individuals, navigating complex English-only web directories is impossible. Phone-first access is a proven model; for example, the Richmond City Health Department explicitly notes that "Telephone interpretation services are available" for newcomer health screenings [12]. 

### Tracking and triage gaps
A major barrier to improving services is the lack of consistent data. The City's 2025 Language Access Plan notes that a standardized tracking system for identifying the primary language of LEP individuals is still "in development," currently relying on self-reported data, intake processes, and vendor reports [2].

## 4) Machine Translation: Risks and Minimum Standards

Machine translation (MT) offers speed but introduces severe risks if used improperly in civic and health contexts.

### 1557’s MT human-review requirement and interpreter restrictions
Under Section 1557, if an entity uses machine translation for text that is critical to the rights, benefits, or meaningful access of an LEP individual, or when accuracy is essential, a qualified human translator must review it [3] [4] [13]. 

| Content Type | Machine Translation Allowed? | Requirements / Guardrails |
| :--- | :--- | :--- |
| Health Eligibility & Legal Rights | No (without review) | Must be reviewed by a qualified human translator [3] [4] |
| Complex Medical Instructions | No (without review) | Must be reviewed by a qualified human translator [3] [4] |
| General Informational Webpages | Yes | Must include a warning that the document may contain errors [3] [9] |

*Takeaway: Unreviewed machine translation is legally and ethically unacceptable for vital service information.*

### Current state practice and risk
State agencies like the Virginia Department of Social Services currently use Google Translate widgets accompanied by a "Translation Disclaimer" [14] [15]. While acceptable for general browsing, this approach fails Section 1557 standards if applied to critical health or benefits applications without human oversight [3].

## 5) Interpreter/Translation Supply in Richmond

Richmond has existing infrastructure that civic tech projects should leverage rather than duplicate.

### City infrastructure
The City of Richmond provides 24/7 access to telephonic interpretation in over 240 languages through Language Line Solutions (LLS) and The Language Group (TLG) [2]. Video remote interpretation (VRI) is available for over 200 languages, including ASL [2]. Staff must pass a professional fluency assessment to deliver services in a non-English language [2].

### Health department and resettlement ecosystem
Virginia's Refugee Resettlement Program operates through several contracted agencies in the Richmond area.

| Organization | Services | Contact / Notes |
| :--- | :--- | :--- |
| Commonwealth Catholic Charities | Resettlement, Foster Care | Richmond office [15] |
| International Rescue Committee | Resettlement | Richmond office [15] |
| ReEstablish Richmond | Language Access, Resources | Provided Kinyarwanda driver's manual [11] |
| Richmond City Health Dept | Health Screenings | Offers telephone interpretation [12] |

*Takeaway: Hackathon teams should build tools that route users to these existing agencies and vendor phone lines.*

## 6) Language Gap Map

Based on refugee inflows and current city thresholds, we can map the most critical language gaps.

| Language | Demand Signals | Current Supports | Gap Severity | Priority Rank |
| :--- | :--- | :--- | :--- | :--- |
| Spanish | Meets 5% City threshold [2] | High (City vital documents translated) [2] | Low | 1 (Baseline) |
| Arabic | High refugee arrivals (Syria/Iraq) [C0TE:10] | Vendor phone lines [2] | Medium | 2 |
| Dari / Pashto | High refugee arrivals (Afghanistan) [10] | Vendor phone lines [2] | High | 3 |
| Kinyarwanda | High refugee arrivals (DRC) [10] | Community translation (ReEstablish) [11] | High | 4 |

*Takeaway: Beyond Spanish, resources must be aggressively targeted toward Afghan, Middle Eastern, and Central African languages.*

## 7) Hackathon Playbook

For a team with limited time and budget, focus on connecting users to existing human infrastructure.

### Minimal viable multilingual entry points
Do not build a custom AI translation engine. Instead, build a one-click "Call with Interpreter" button that dials the City's existing LanguageLine Solutions account or a designated community partner. Use simple, universally recognized icons and audio prompts for low-literacy users.

### Content triage and QA
Implement a strict "vital vs. informational" content matrix. Use machine translation (with clear disclaimers) only for basic directory navigation. For any text detailing eligibility, legal rights, or medical services, flag the content to require human translation review before publishing, aligning with Section 1557 [3] [4].

### Volunteer and staff enablement
Create a 1-page digital script for volunteers on how to properly conference in a telephonic interpreter, explicitly banning the use of children or unverified bilingual bystanders as interpreters [3] [9].

## 8) Risk Flags and Failure Cases

Avoid these common pitfalls that create legal liability and harm vulnerable users.

| Risk / Failure Mode | Evidence / Rule | Mitigation Strategy |
| :--- | :--- | :--- |
| Unreviewed MT for vital info | Sec 1557 prohibits unreviewed MT for critical rights/benefits [3] [4] | Implement human-in-the-loop QA for all vital directory listings. |
| Using minors as interpreters | Sec 1557 restricts using unqualified adults/minors [3] [9] | Hardcode routing to professional telephonic interpreters. |
| Relying on self-assessed staff | Self-identified proficiency is insufficient [3] [9] | Require formal fluency assessments (as Richmond City does) [2]. |

*Takeaway: Convenience cannot override accuracy when civil rights and health access are at stake.*

## 9) Measurement, Governance, and Compliance

To prove impact and maintain compliance, projects must track language data meticulously.

### Metrics and feedback loops
Because the City's standardized tracking is still in development [2], any new civic tech tool should mandate a "preferred language" field upon user intake. Track abandonment rates by language to identify where the interface fails LEP users.

### Governance
Align with Section 1557 requirements for health-related directory partners.

| Requirement | Responsible Party | Artifact |
| :--- | :--- | :--- |
| Nondiscrimination Notice | Covered Entity | Posted notice in top 15 languages [3] [4] |
| Section 1557 Coordinator | Entities with 15+ employees | Designated staff member [4] [13] |
| Language Access Procedures | Covered Entity | Written policies for accessing interpreters [4] [13] |

*Takeaway: Build compliance tracking directly into the service directory's backend.*

## 10) Appendices

### Facts with URLs
* HHS OCR Section 1557 Guidance: https://www.hhs.gov/sites/default/files/ocr-dcl-section-1557-language-access.pdf
* Richmond Language Access Plan 2025: https://rva.gov/sites/default/files/2026-01/City%20of%20Richmond%20Language%20Access%20Plan%202025.pdf
* EO 14224 (Designating English as Official Language): https://www.federalregister.gov/documents/2025/03/06/2025-03694/designating-english-as-the-official-language-of-the-united-states

### Partner/Contact List
* **Office of Immigrant and Refugee Engagement (OIRE):** Manages language services for Richmond community events [2].
* **ReEstablish Richmond:** Provides newcomer resources and translations [11].
* **Resettlement Agencies:** CCC, IRC, CWS [15].

## References

1. *LANGUAGE ACCESS POLICY A.R. Number: 5.24 Effective ...*. https://rva.gov/sites/default/files/2023-05/Administrative%20Regulation%205.24%20Language%20Access%20Policy_19MAY2023.pdf
2. *Fetched web page*. https://rva.gov/sites/default/files/2026-01/City%20of%20Richmond%20Language%20Access%20Plan%202025.pdf
3. *ocr-dcl-section-1557-language-access.pdf*. https://www.hhs.gov/sites/default/files/ocr-dcl-section-1557-language-access.pdf
4. *The Biden administration's Final Rule for Sec. 1557*. https://cchicertification.org/uploads/2024-Section-1557-Final-Rule-CCHI-Webinar-Handouts.pdf
5. *
      Federal Register
       :: 
      Designating English as the Official Language of the United States
    *. https://www.federalregister.gov/documents/2025/03/06/2025-03694/designating-english-as-the-official-language-of-the-united-states
6. *Designating English as the Official Language of The United States – The White House*. https://www.whitehouse.gov/presidential-actions/2025/03/designating-english-as-the-official-language-of-the-united-states/
7. *Implementation of Executive Order No. 14224 Designating ...*. https://www.justice.gov/ag/media/1407776/dl
8. *
      Federal Register
       :: 
      Notice of Rescission of Guidance to Federal Financial Assistance Recipients Regarding Title VI Prohibition Against National Origin Discrimination Affecting Limited English Proficient Persons
    *. https://www.federalregister.gov/documents/2026/03/04/2026-04218/notice-of-rescission-of-guidance-to-federal-financial-assistance-recipients-regarding-title-vi
9. *HHS Letter Reiterates Expectations for Language Accessibility | McDermott Will & Schulte - JDSupra*. https://www.jdsupra.com/legalnews/hhs-letter-reiterates-expectations-for-3838502/
10. *Who Are 'Newcomers'? — ReEstablish Richmond*. https://www.reestablishrichmond.org/who-are-newcomers
11. *Language Access — ReEstablish Richmond*. https://www.reestablishrichmond.org/language-access
12. *Office of New Americans-Refugee Services - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/sample-page/programs/new-americans-refugee-services/
13. *Sec. 1557 Requirements for Decision Support Tools & AI*. https://www.amnhealthcare.com/siteassets/language-services/section-1557-compliance-materials/guidance-on-ai-patient-care-decisions-support-tools.pdf
14. *Refugee Resettlement Reports & Statistics - Virginia Department of Social Services*. https://www.dss.virginia.gov/geninfo/reports/community_partners/refugee.cgi
15. *Refugee Services - Virginia Department of Social Services*. https://www.dss.virginia.gov/community/ona/refugee_services.cgi