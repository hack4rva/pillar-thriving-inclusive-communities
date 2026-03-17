# Richmond Social Services Access for Immigrant and Refugee Residents: What Works Now and What Needs Integration

## Executive Summary
The City of Richmond has established a formalized language access framework, but navigating social services and housing programs remains complex for immigrant and refugee residents due to state and federal eligibility gates. The City adopted Administrative Regulation 5.24, effective July 1, 2023, which mandates language access responsibilities and oversight by the Office of Immigrant and Refugee Engagement (OIRE) [1]. While the City guarantees free interpretation services and prioritizes Spanish translation based on demographic data (6,537 Spanish-speaking Limited English Proficiency residents) [2], actual benefit eligibility is largely dictated by state (VDSS) and federal (HUD) rules. 

Undocumented adults face significant barriers to direct assistance, though mixed-status families can often access child-centric benefits like the Child Care Subsidy if the child is a citizen or legal resident [3]. Housing assistance is siloed under the Richmond Redevelopment and Housing Authority (RRHA), requiring separate applications and strict immigration status checks [4] [5]. For a hackathon team building a navigation solution, the immediate opportunity lies in designing a Spanish-first, interpreter-aware intake process that routes users to the correct portals (CommonHelp, RRHA) while clearly setting expectations around eligibility and required documentation.

## Scope and User Value
The primary objective is to build an immigrant-ready navigation pathway using existing City of Richmond channels while planning for future state and RRHA integrations. By delivering a Spanish-first, interpreter-aware experience, the solution can route residents through the Department of Social Services (DSS), CommonHelp, and RRHA with clear eligibility cues. This approach minimizes the friction Limited English Proficiency (LEP) residents face when seeking aid and sets realistic expectations about data access and wait times.

## DSS Services Residents Can Access Now
Core DSS benefits are accessible through multiple public channels, though immigrant eligibility varies significantly by program and legal status. 

### City-Listed DSS Benefits Align to Common Immigrant Family Needs
The Richmond DSS portfolio is broad. Publicly listed benefits include the Supplemental Nutrition Assistance Program (SNAP), Medicaid/Health Insurance, Child Care Subsidy, Energy Assistance, General Relief, Auxiliary Grant, TANF/VIEW, and Refugee Assistance [6]. Family services encompass Adult Protective Services (APS), Child Protective Services (CPS), Foster Care, Family Preservation, and Homeless Services [6]. 

### Application Channels and Physical Locations
Residents have multiple avenues to apply for DSS benefits. Applications can be submitted online via the state's CommonHelp portal, by phone at 855-635-4370, or by fax at 804-646-7018 [6] [7]. For in-person assistance or document drop-off, residents can visit the Downtown office at the 300 E. Franklin Building or the South Richmond location at the Southside Community Services Center (4100 Hull Street Road) [6] [7]. General inquiries can be directed to the City's 3-1-1 Customer Care Center [6].

## Eligibility for Non-Citizens
Navigating eligibility is one of the most critical challenges for immigrant families. Children in mixed-status families often qualify for services even when their undocumented parents do not, provided the child meets citizenship or legal residency requirements.

### Program Eligibility for Non-Citizens

| Program | Administered by | Non-citizen eligibility notes | How to apply |
| :--- | :--- | :--- | :--- |
| **SNAP** | VDSS via City DSS | Must be citizens or "qualified immigrants"; undocumented adults generally ineligible [8]. | CommonHelp; Phone: 855-635-4370 [7] |
| **Child Care Subsidy** | VDSS/Child Care VA via City DSS | Requires documentation of the child's citizenship or legal residence in the U.S. [3]. | CommonHelp [9] [10] |
| **Public Housing / HCV / PBV** | RRHA | Applicants must be U.S. citizens or eligible immigrants [4] [5]. | RRHA Applicant Portal [4] |

*Key Takeaway*: A critical failure case to anticipate is undocumented parents applying for child care without realizing they only need to provide the child's status documentation. Navigation tools must explicitly highlight child-only eligibility rules to prevent eligible families from self-selecting out of the process.

## Housing Assistance Landscape
Housing assistance in Richmond is primarily operated by the Richmond Redevelopment and Housing Authority (RRHA), not the City's DSS. RRHA acts as the operational hub, while the City's role is largely limited to enablement and referral.

### RRHA Controls Waitlists and Eligibility
RRHA administers the Housing Choice Voucher (HCV) Program (formerly Section 8), Project Based Vouchers (PBV), and Public Housing [11] [4] [5]. Eligibility for these programs requires applicants to earn less than the HUD income limit for their family size and be U.S. citizens or eligible immigrants [5]. 

### Application Mechanics and Wait Times
Applications must be submitted through RRHA's specific applicant portals [4]. For the HCV program, participating families are generally required to pay approximately 30% of their adjusted monthly income toward rent and utilities [11]. Wait times and list positions are strictly managed by RRHA, meaning the City cannot provide real-time status updates without formal data-sharing agreements.

## Language Access Framework
The City of Richmond has a formalized policy guaranteeing residents the right to free interpretation services, with Spanish prioritized due to demographic needs. OIRE centralizes this policy and its operations.

### Policy Backbone and Title VI Compliance
Administrative Regulation 5.24, effective July 1, 2023, ensures compliance with Title VI of the Civil Rights Act of 1964 [1]. The policy mandates that departments designate a Language Access Liaison, offer translation of vital documents, and provide methods for LEP individuals to request interpretation [1]. The City prohibits discrimination based on national origin and provides a complaint pathway via CityWebManager@rva.gov or directly to OIRE [12] [13].

### LAP 2025 and iSpeak Richmond Tools
Under the Language Access Plan, the City provides free interpretation and translation services [13]. OIRE staff provides Spanish/English interpretation during office hours, while interpretation in other languages and after-hours Spanish support are available through the United Language Group [13]. The "iSpeak Richmond" initiative serves as the official portal for promoting language access tools, including Language Identification Guides and "I Speak" cards [13].

### Evidence Base for Spanish Prioritization
Historical data from the City's Language Access Plan indicates there are 6,537 LEP residents who speak Spanish as a primary language, representing 3.36% of the City's population [2]. Furthermore, Spanish accounted for more than 96% of the calls to the City's language line, justifying the translation of all vital documents into Spanish [2].

## Access Channels and the LEP Journey
Designing a seamless journey for LEP residents requires proactive measures to prevent drop-offs, particularly regarding interpreter availability and document verification.

### Contact Flow and Friction Points
Residents typically initiate contact via 3-1-1, the DSS application line (855-635-4370), or by visiting DSS offices [6] [7]. For language support, they can contact OIRE at 804-646-0145 [13]. A major pitfall in the LEP journey is arriving for a non-emergency visit without a pre-scheduled interpreter. The City's policy states that for non-emergency situations, offices should seek to make an appointment when an in-person interpreter can be present [2]. Navigation tools should embed interpreter booking prompts and document checklists to reduce front-desk friction.

## What the Hackathon Team Can Use Now vs. What Needs Cross-Agency Access
To build an effective prototype, teams must distinguish between publicly available resources and data that requires formal Memorandums of Understanding (MoUs).

### Capability and Data Source Matrix

| Capability | Data Source | Publicly Usable Now | Requires Agreement |
| :--- | :--- | :--- | :--- |
| Program descriptions & eligibility links | rva.gov / virginia.gov | Yes | No |
| Interpreter requests & iSpeak tools | OIRE | Yes (contact-based) | No |
| Real-time application status (SNAP/Medicaid) | VDSS / CommonHelp | No | Yes (State integration) |
| RRHA waitlist position/status | RRHA Portals | No | Yes (RRHA integration) |
| LEP interaction metrics by department | OIRE / Departments | Limited public | Yes (De-identified aggregate) |
| Interpreter scheduling across departments | OIRE internal | No | Yes (Process integration) |

*Key Takeaway*: The team should build around public information and OIRE's existing services, while designing placeholder interfaces for state and RRHA status data that would require future API integrations.

## Cross-Agency Navigation Pathway
*(Inference)* Based on the structure of City services, the hackathon rubric likely references a pathway connecting DSS benefits (SNAP, Medicaid, Child Care), OIRE language access support, and RRHA housing programs. Because these entities operate on different systems (City, State, and independent Authority), a successful cross-agency navigation pathway must act as a unified triage layer that hands users off to the correct specific portal (e.g., CommonHelp or RRHA SecureCafe) with the right preparatory information.

## Referral Ecosystem
*(Inference)* While explicit nonprofit referral maps are not comprehensively detailed on the public rva.gov pages provided, OIRE is tasked with developing community resources, partnerships, and relationships to assist with outreach to LEP individuals [2]. It is highly likely that homeless and housing crisis navigation involves regional nonprofit partners. Hackathon teams should confirm formal referral protocols for immigrant-serving Community-Based Organizations (CBOs) directly with OIRE.

## Data and Measurement
The City mandates internal tracking of LEP interactions, though public-facing dashboards are sparse.

### Tracking Requirements and App Instrumentation
Effective November 1, 2016, each City Department was required to track contacts with LEP individuals [2]. Under AR 5.24, OIRE is responsible for analyzing demographics and maintaining updated information regarding language access needs [1]. 
*(Actionable Inference)*: Hackathon teams should request aggregated, de-identified LEP contact counts from OIRE to establish baseline metrics. The proposed application should be instrumented to capture anonymous language-need flags and interpreter modality requests to feed data back into the City's continuous improvement cycles.

## Office of Community Wealth Building (OCWB)
*(Inference)* The provided research context does not contain specific data regarding the Office of Community Wealth Building's current programs or their explicit relevance to immigrant and refugee residents. Generally, OCWB focuses on workforce development and economic mobility. Hackathon teams will need to conduct targeted follow-up research to map OCWB's specific language access alignment and eligibility criteria for non-citizens.

## Key City Contacts
Maintaining accurate contact information is vital for front-line navigation. The following table centralizes the current single sources of truth for City services.

### Centralized Contact Directory

| Service | Contact Information | Source |
| :--- | :--- | :--- |
| **OIRE (Language Access, Complaints)** | 804-646-0145; askoire@rva.gov; 4100 Hull St Rd | [13] |
| **DSS General / Customer Care** | 3-1-1; (804) 646-7212 (Outside RVA) | [6] [7] |
| **Apply for Benefits (SNAP/Child Care)** | 855-635-4370; commonhelp.virginia.gov | [6] [7] |
| **DSS Fax / Drop Box** | Fax: 804-646-7018; Drop Box: 4100 Hull St | [6] [7] |
| **DSS Office Locations** | 300 E. Franklin St; 4100 Hull St Rd | [6] [7] |
| **Adult Protective Services** | 804-646-7405; After-hours: 888-832-3858 | [6] [7] |
| **Virginia EBT Help Line** | 866-281-2448 | [7] [14] |
| **RRHA (Housing Portals)** | rrha.com | [11] [4] |

*Key Takeaway*: Legacy documents may list outdated coordinators (e.g., Olivier Faye from the 2020 LAP) [2]. Teams must standardize on the current OIRE contact data (askoire@rva.gov / 804-646-0145) [13] to prevent misrouting of LEP residents.

## References

1. *LANGUAGE ACCESS POLICY A.R. Number: 5.24 Effective ...*. https://rva.gov/sites/default/files/2023-05/Administrative%20Regulation%205.24%20Language%20Access%20Policy_19MAY2023.pdf
2. *1 Revised Version April 2020 LANGUAGE ACCESS PLAN ...*. https://rva.gov/sites/default/files/2022-05/LANGUAGE%20ACCESS%20PLAN%20FINAL-%20APR2020.pdf
3. *
	
    Paying for Child Care | Child Care VA

*. https://www.childcare.virginia.gov/families/paying-for-child-care
4. *Public Housing Program | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/housing/public-housing/
5. *Project Based Vouchers (PBV) | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/housing/vouchers/pbv/
6. *Social Services Main | Richmond*. https://www.rva.gov/social-services/social-services-main
7. *ESI - SNAP/SNAPET | Richmond*. https://www.rva.gov/social-services/esi-snapsnapet
8. *SNAP Eligibility Checklist*. https://www.vplc.org/content/uploads/2023/02/VPLC-SNAP-Checklist-PDF.pdf
9. *ESI - Child Care | Richmond*. https://www.rva.gov/social-services/esi-child-care
10. *
	
    Subsidy Information for Families | Child Care VA

*. https://www.childcare.virginia.gov/families/paying-for-child-care/english-subsidy-resources
11. *Vouchers | Richmond Redevelopment & Housing Authority*. https://www.rrha.com/housing/vouchers/
12. *Accessibility | Richmond*. https://www.rva.gov/Accessibility
13. *Language Access | Richmond*. https://www.rva.gov/immigrant-engagement/language-access
14. *Social Services FAQ's | Richmond*. https://www.rva.gov/social-services/social-services-faqs