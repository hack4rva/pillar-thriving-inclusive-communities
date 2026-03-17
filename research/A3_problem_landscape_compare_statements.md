# Hackathon Readiness: Service Discovery vs. "Don't Repeat Your Story" in Community Support

## Executive Summary
When evaluating the "Thriving and Inclusive Communities" pillar for a weekend hackathon, the two targeted problem statements present fundamentally different challenges. **Statement 1 (Service Discovery)** is highly "software-shaped" and ready for immediate prototyping. It relies on public-facing data and standard screening tools to connect residents to care. **Statement 2 (Don't Repeat Your Story)**, while incredibly valuable, is constrained by a critical data gap (D3=1). It is primarily a governance, consent, and interoperability challenge rather than a pure software problem. 

To maximize a 48-hour hackathon, teams should prioritize Statement 1 by building a trusted discovery and guided referral MVP. However, Statement 2 holds massive long-term economic and social potential if a post-hackathon champion can navigate the necessary cross-agency data sharing and consent frameworks. A hybrid approach—centering the resident with a self-sovereign, exportable "story packet"—can bridge both statements without requiring immediate backend integration across siloed government systems.

## Context and Decision Frame

### The Two Targeted Statements and Scores
The provided scoring framework signals distinct readiness levels for the two problem statements. Statement 1 is primed for rapid development, while Statement 2 flags a critical barrier to entry.

| Problem Statement | Score | Primary Constraint | Hackathon Readiness |
| :--- | :--- | :--- | :--- |
| **Statement 1:** Help Residents Safely Discover and Connect to Trusted Support Services | 24/32 (Strong) | Maintaining accurate capacity and eligibility data | High: Can be built using existing public directories and standard screeners. |
| **Statement 2:** Helping Residents Navigate the Right Support Services Without Repeating Their Story | 22/32 (Needs Work) | D3=1 Critical Data Gap (Interoperability & Consent) | Low/Medium: Requires cross-agency data integration, shared consent, and policy alignment. |

### Who the User Really Is (and Isn't)
The primary users for both statements are residents with multi-system needs and the frontline workers (navigators, peers, and caseworkers) who assist them. In Washington State's No Wrong Door (NWD) pilot, data revealed that out of 1,261,853 individuals served, approximately 120,165 were "intensely shared clients" requiring services from multiple programs [1]. 

Furthermore, Ohio's behavioral health crisis system emphasizes a continuum of "Connect, Respond, Stabilize, and Thrive," noting that peer support specialists and care navigators are essential team members to bridge the gap between stabilization and long-term thriving [2]. Therefore, the software must not attempt to replace human relationships; rather, it should scaffold the work of peer navigators and empower residents to make informed choices [2] [3].

## Data Reality Check

### Available Building Blocks You Can Use This Weekend
Hackathon teams have access to proven, standardized screening tools and public service directories that can be operationalized immediately. For example, South Carolina successfully deployed the GAIN-SS (Global Assessment of Individual Needs – Short Screener) across multiple agencies to identify youth needing services [1]. By September 2010, they screened 5,595 clients, finding that 91% had at least one positive indicator requiring treatment [1]. Teams can easily digitize similar plain-language screeners to drive targeted referrals. Additionally, Washington State's early NWD efforts succeeded by starting with a simple client registry and a shared consent form before attempting to build custom, complex IT applications [1].

### What's Missing (and Why It Matters)
The "D3=1 critical data gap" in Statement 2 exists because interoperable client histories and automated capacity signals are not turnkey. South Carolina's NWD pilot revealed average wait times of four to five days for appointments after referrals were made, highlighting that software cannot invent provider capacity [1]. Furthermore, Washington State teams cited inflexible funding and the inability to redirect program savings as major disincentives for staff to invest time in coordinated care [1]. Finally, lawful data reuse across organizations requires complex consent management that does not currently exist in a unified format.

## Software-Shapedness Assessment

### Statement 1: Discovery/Connection
This problem is highly software-shaped. Centralized help desks are emerging as a primary way to connect people to scarce resources [4]. Software can meaningfully address discovery by providing plain-language eligibility criteria, filtering options, and direct connections to peer navigators without requiring sweeping policy changes. It enhances the "Connect" pillar by making help visible and accessible [2].

### Statement 2: Don't Repeat Your Story
This problem is policy- and governance-shaped. Avoiding repeated storytelling requires navigating strict privacy laws and segmenting sensitive data. For instance, the HHS 2024 final rule for 42 CFR Part 2 allows a single consent for all future uses and disclosures for treatment, payment, and health care operations, but implementing this technically remains difficult [5]. Pilot evaluations of tools like Consent2Share show that accurately segmenting sensitive data requires complex logic [6] [7]. Furthermore, the HL7 Gravity Project's Social Determinants of Health (SDOH) Clinical Care Implementation Guide emphasizes that gathering SDOH information and exchanging referrals must be done "with appropriate patient consent" [8]. Software alone cannot force agencies to trust each other's intake forms.

## Comparative Analysis & Recommendations

### Side-by-Side Decision Table

| Assessment Dimension | Statement 1: Discover & Connect (Score: 24/32) | Statement 2: Don't Repeat Story (Score: 22/32; D3=1) |
| :--- | :--- | :--- |
| **1. Clarity of the User** | High. Residents seeking help and peer navigators guiding them. | High. "Intensely shared clients" navigating multiple siloed agencies. |
| **2. Data Availability** | High. Public service directories, standard screeners (e.g., GAIN-SS). | Low (D3=1). Lacks interoperable client histories and unified consent APIs. |
| **3. Software-Shapedness** | High. Triage, filtering, and directory UX are classic software problems. | Low. Requires cross-agency legal agreements, shared consent, and data segmentation. |
| **4. Weekend Feasibility** | High. A functional directory with a guided screener is easily achievable in 48 hours. | Low. True backend integration is impossible in a weekend. Must be scoped to a resident-held export. |
| **5. Post-Hackathon Path** | Medium. Requires ongoing maintenance of service capacity and eligibility data. | High Complexity / High Reward. Requires a massive governance champion, but yields massive ROI. |

### Recommendation with Rationale
**Recommendation:** Prioritize Statement 1 for the hackathon, but design the data model to eventually support Statement 2. 

**Rationale:** Statement 1 is stronger for a 48-hour hackathon because it relies on data that is currently available (service directories, screening questionnaires) and solves an immediate user pain point (finding help) without requiring inter-agency legal agreements. Statement 2 has a critical data gap (D3=1) because backend interoperability and consent management (like 42 CFR Part 2 compliance) cannot be solved with code alone [5] [7]. 

However, **Statement 2 has significantly more post-hackathon potential** if a champion is identified. Mature coordination delivers massive economic and social outcomes. Humboldt County's integrated service delivery system decreased group home expenditures by more than 72% since 1997, dropped group home placements for abused/neglected youth by 82%, and reduced youth recidivism to 22% (compared to a nationwide average of 50% to 80%) [1]. Furthermore, their elderly caseload for In-Home Supportive Services decreased by 8.5% while the statewide caseload increased by 70% [1].

### MVP Concept 1: Addressing the Stronger Statement (Statement 1)
**Concept: "Trusted Navigator" Discovery Portal**
* **What it is:** A mobile-first web app that pairs a plain-language, structured screener with a directory of community services and peer navigators.
* **How it works:** The user answers a brief, GAIN-SS-style questionnaire to identify needs [1]. The app filters a directory of local services, displaying plain-language eligibility requirements and "what to expect" guides. Crucially, it features a "Connect with a Peer" button, allowing users to reach out to lived-experience navigators who can guide them through the stabilization process [2] [3].
* **Weekend Feasibility:** High. Teams can hardcode a database of 20-30 local services, build the screening logic, and create a clean, accessible UI.

### MVP Concept 2: Addressing Both Statements Partially
**Concept: The "Tell It Once" Resident Story Packet**
* **What it is:** A self-sovereign, resident-owned intake application aligned with HL7 Gravity Project SDOH standards [8]. 
* **How it works:** Instead of trying to integrate government backend systems (which is impossible in a weekend), the software empowers the *resident* to be the integration point. The resident fills out a comprehensive, structured SDOH intake form on their own device. The app generates a secure, exportable "Story Packet" (as a PDF and a FHIR QuestionnaireResponse) [8]. When the resident discovers a trusted service (solving Statement 1), they can securely share their Story Packet via a time-expiring link or QR code with the intake worker, preventing them from having to repeat their trauma or basic history (solving Statement 2).
* **Weekend Feasibility:** Medium/High. It avoids the D3=1 data gap by keeping the data entirely in the user's hands. It demonstrates an understanding of consent and interoperability without requiring actual cross-agency APIs.

## Post-Hack Path: What It Takes to Operationalize

To transition a prototype into a durable tool used by real residents, the following milestones must be achieved:

| Domain | Requirement for Real-World Use | 90-Day Milestone |
| :--- | :--- | :--- |
| **Governance** | Cross-agency leadership commitment to honor the tool's outputs. | Establish a Joint Council (similar to South Carolina's model) to oversee implementation [1]. |
| **Legal & Consent** | Shared consent forms approved by legal counsel. | Draft a universal consent form compliant with 42 CFR Part 2 for basic SDOH data sharing [5] [1]. |
| **Workforce Training** | Staff must be trained to accept the new digital intake and trust the screeners. | Conduct cross-training for frontline workers on the new workflow to reduce staff resistance [1]. |
| **Data Standards** | Alignment with national interoperability frameworks. | Map the application's data payload to the HL7 Gravity Project SDOH Clinical Care IG [8]. |

**Risks and Mitigation:** The primary risk is staff resistance and inflexible funding, as seen in Washington State's early pilots [1]. To de-risk this, the post-hackathon phase must start with low-risk domains (e.g., food and housing insecurity) before expanding into highly regulated behavioral health data, and must involve frontline workers in the co-design process to ensure the tool actually saves them time.

## References

1. *The County No Wrong Door Feasibility Study*. https://hfwcny.org/wp-content/uploads/NYSAC_No_Wrong_Door_Feasibility_Study_2012_11_2__2____KM.pdf
2. *Landscape Analysis - Ohio Department of Behavioral Health*. https://dbh.ohio.gov/get-help/crisis-systems/landscape-analysis
3. *Leaning on Experience, Care Navigators Help Those on the Rough Path to Stability | County of San Mateo, CA*. https://www.smcgov.org/ceo/news/leaning-experience-care-navigators-help-those-rough-path-stability
4. *Help Desk Are Emerging As a Way To Connect People to Homeless Services*. https://nextcity.org/urbanist-news/help-desk-are-emerging-as-a-way-to-connect-people-to-homeless-services
5. *Fact Sheet 42 CFR Part 2 Final Rule | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/regulatory-initiatives/fact-sheet-42-cfr-part-2-final-rule/index.html
6. *
            Pilot Evaluation of Sensitive Data Segmentation Technology for Privacy - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC7229704/
7. *Pilot evaluation of sensitive data segmentation technology for privacy - ScienceDirect*. https://www.sciencedirect.com/science/article/abs/pii/S1386505619313681
8. *IG Home - SDOH Clinical Care v3.0.0-ballot*. https://build.fhir.org/ig/HL7/fhir-sdoh-clinicalcare/