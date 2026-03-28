> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Virginia's Social Care Tech Stack: How to Leverage Unite Us and Close the Interoperability Gap in 2026

## Executive Summary

- **Virginia already runs on Unite Us:** The state allocated $10 million in federal CARES Act funding to launch Unite Virginia, a statewide e-referral infrastructure [1]. The network has achieved significant traction, reporting 85,174 clients served, 174,229 needs identified, and 94,470 referrals sent [2]. Help1RVA should integrate with this existing backbone rather than duplicating it.
- **Documented outcomes make the ROI case:** Closed-loop referrals through Unite Us correlate with measurable healthcare savings. A deployment by Ballad Health in collaboration with the Virginia Hospital & Healthcare Association (VHHA) showed a 16.2% average decrease in emergency department (ED) visits, which improved to a 24.8% decrease when patients were engaged by a community health worker (CHW) [3]. 
- **Non-English resident access is robust:** The Unite Us "Get Help" portal supports an extensive array of languages, ranging from Afrikaans and Amharic to Vietnamese and Zulu [4]. Help1RVA can immediately leverage this by deep-linking non-English speakers into these existing localized flows.
- **Privacy is locked down and U.S.-only:** Unite Us operates a HIPAA-compliant platform [5] that restricts access to within the United States [6]. Data is collected directly from network participants and online forms, with strict opt-out mechanisms [6]. Consequently, public APIs for open directory scraping are not available.
- **Market consolidation reduces vendor choice:** Unite Us acquired NowPow in 2021, absorbing its algorithms and network of over 1 million past screenings [7]. This consolidation means Virginia's social care landscape is heavily centralized under the Unite Us stack.
- **Standards are bifurcating:** Clinical data exchange is standardizing around HL7 FHIR and SMART on FHIR [8], while the Gravity Project is prioritizing the standardization of social care payment data, specifically enrollment, service documentation, and claim submission [9]. Bridging public directory data (like HSDS) with these clinical standards requires deliberate mapping.
- **Free for CBOs lowers participation barriers:** All non-profit, community-based organizations (CBOs) can use the Unite Us platform and its Insights tool free of charge [3] [10]. Advanced integrations and data delivery are paid optional products [10].

## Purpose and Decision Frame

Virginia's Unite Us network serves as the de facto statewide backbone for social care coordination. For Help1RVA, the strategic imperative is to complement this existing infrastructure rather than attempting to build a parallel, competing referral system. By leveraging the state's $10 million investment in Unite Virginia [1], Help1RVA can focus its immediate efforts on improving the resident-facing frontend, optimizing language access, and driving local CBO enrollment. Long-term, Help1RVA must budget for and architect standards-based interoperability to bridge open directory formats with the closed-loop, FHIR-based clinical networks dominated by Unite Us.

## Market Landscape: Virginia and National Context

### Unite Virginia dominates the state ecosystem
Virginia has heavily consolidated its social care technology under Unite Us. Backed by $10 million in CARES Act funding, the state established Unite Virginia to connect vulnerable populations to health and social services [1]. The scale of adoption is substantial: the network reports 85,174 clients served and 94,470 referrals sent [2]. Prior to the statewide rollout, Unite Us already powered regional networks in Hampton Roads and the Shenandoah Valley [1], and major players like Sentara Healthcare, Optima Health, and the United Way of South Hampton Roads have formally integrated into the network [11] [12]. 

### Measurable outcomes drive hospital adoption
The adoption of Unite Us is heavily driven by proven reductions in healthcare utilization. VHHA reports that since 2019, 68,353 individuals have been connected to social services through the platform [3]. More importantly, closed-loop referrals are directly tied to a 16.2% average decrease in ED visits in the six months following a referral, a figure that jumps to a 24.8% decrease when a community health worker is involved [3].

### National consolidation and standards momentum
Nationally, the market is consolidating. In 2021, Unite Us acquired NowPow, a major community resource network platform that had previously enabled 1 million screenings and millions of referrals [7]. Technologically, the industry is coalescing around specific interoperability standards. Unite Us leverages SMART on FHIR and HL7 protocols for electronic health record (EHR) integration [8]. Concurrently, the Gravity Project is working to standardize social determinants of health (SDOH) data, prioritizing the administrative workflows of CBOs, such as enrollment, service documentation, and claims [9] [13].

## Platform Deep Dives: What Matters for Help1RVA

### Unite Us / Unite Virginia
Unite Us is the dominant whole-person care platform in Virginia, connecting healthcare providers, government agencies, and social services [14]. 
- **Presence:** Statewide via Unite Virginia, including specific resource routing for Richmond City [1] [15].
- **Non-English UX:** The public "Get Help" interface features a comprehensive language selector supporting dozens of languages [4].
- **Privacy:** The platform is HIPAA-compliant [5]. Access is strictly limited to the United States, and the platform is not directed at children under 13 [6]. Users can request data removal or opt-out of network sharing [6].
- **API/Interoperability:** Unite Us utilizes APIs, SMART on FHIR, and HL7 protocols to integrate directly into EHRs and case management systems [8]. However, these are enterprise integrations, not open public APIs for directory scraping.
- **Costs:** The core platform and Insights data are provided at no cost to non-profit CBOs [3] [10]. Organizations must purchase optional products for advanced Integrations or Data Delivery [10].

### NowPow (Integrated into Unite Us)
NowPow, originally a University of Chicago spin-out focused on e-prescribing community resources, was acquired by Unite Us in September 2021 [7] [16]. Prior to the acquisition, NowPow had facilitated over 1 million screenings [7]. Its condition-based algorithms and community partners have been folded into the Unite Us ecosystem, meaning organizations previously relying on NowPow must now navigate the Unite Us infrastructure [7].

### 211 / United Way 211
While United Way operates the 211 network nationally, in Virginia, regional United Way chapters are actively partnering with the Unite Us infrastructure. For example, the United Way of South Hampton Roads partnered with Optima Health and Unite Us to connect Medicaid members to social services through a unified, accountable network [12]. 

### FindHelp, Healthify, CareDx, and Expound
*Note: Based on the current Virginia landscape, Unite Us has secured the primary state mandates and hospital partnerships (e.g., VHHA, VDH, Sentara) [11] [3] [1]. Alternative platforms like FindHelp or Healthify (WellSky) operate in the broader national market, but Help1RVA's immediate local environment is dictated by the Unite Virginia deployment.*

## Open Referral / HSDS

The Human Service Data Specification (HSDS), championed by the Open Referral initiative, solves the problem of fragmented, siloed community resource directories by providing a common schema for services, locations, and organizations. 

While Unite Us heavily promotes clinical interoperability standards like FHIR and SMART on FHIR for EHR integration [8], bridging the gap between open public directories (HSDS) and closed-loop clinical referrals (FHIR) remains a critical challenge. Help1RVA can adopt HSDS as its internal data standard to maintain a portable, vendor-neutral directory, but it will require a translation layer to map HSDS entities to FHIR standards when interacting with the Unite Us network.

## Comparison Tables

### Platform Comparison: Resident UX, Privacy, and Cost

| Platform | VA/Richmond Presence | Resident Language Support | Privacy Model | Public API | Cost for CBOs |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Unite Us / Unite Virginia** | Statewide mandate; Richmond City specific pages [1] [15] | Extensive (Afrikaans to Zulu) [4] | HIPAA-compliant; U.S. access only; Opt-out available [6] [5] | No (Enterprise EHR APIs only) [8] | Free for non-profits; paid add-ons [3] [10] |
| **NowPow** | Absorbed into Unite Us [7] | N/A (Legacy) | N/A (Legacy) | N/A (Legacy) | N/A (Legacy) |
| **United Way (Regional)** | Integrated with Unite Us in Hampton Roads [12] | Varies by local deployment | Governed by Unite Us network terms [12] | Restricted | Free via Unite Us [3] |

*Takeaway: Unite Us is the only viable primary target for Help1RVA integration in Virginia due to its statewide funding, free access for CBOs, and comprehensive language support.*

### Interoperability Matrix: Standards and Integration Paths

| Platform | Directory Standard | Clinical Exchange | Data Export Options | Integration Products |
| :--- | :--- | :--- | :--- | :--- |
| **Unite Us** | Proprietary / Mapped | HL7, SMART on FHIR [8] | Paid "Data Delivery" [10] | Paid "Integrations" [10] |
| **Gravity Project (Standard)** | N/A | SDOH Clinical Care IG [13] | N/A | N/A |
| **Help1RVA (Proposed)** | HSDS (Open Referral) | FHIR (via mapping) | CSV / API | Custom Translation Layer |

*Takeaway: To achieve true interoperability, Help1RVA must utilize HSDS for its directory foundation while building technical capacity to translate that data into the FHIR standards required by Unite Us and the Gravity Project.*

## Hackathon 48-Hour Playbook

During a 48-hour hackathon, teams cannot execute complex, authenticated EHR integrations or bypass closed APIs. Instead, the focus must be on public UX overlays and data scaffolding.

- **Deep-Link to Unite Virginia:** Build a resident-facing "one front door" that captures user intent and geo-detects Richmond users. Route these users directly to the Unite Virginia Richmond City resources page [15].
- **Leverage Existing Forms:** For users needing human assistance, deep-link to the Richmond City Health District's existing resource navigator form [17].
- **Language-Aware Routing:** Utilize the extensive language parameters available on the Unite Us "Get Help" page [4] to ensure non-English speakers are routed to pre-translated interfaces.
- **Build HSDS Scaffolding:** Create an HSDS-compliant database schema and a basic import/export pipeline. This ensures that when Help1RVA eventually secures authorized data exports from partners, the system is "integration-ready."

## The Interoperability Gap

Solving the interoperability gap in Richmond requires addressing technical, operational, and contractual hurdles.

- **Technical Alignment:** The Gravity Project has identified that CBOs face significant administrative burdens due to diverse payer requirements and data formats [9]. To solve this, the industry is prioritizing the standardization of enrollment, service documentation, and claim submission [9]. Help1RVA must align its data models with these Gravity Project standards to avoid creating bespoke fields that force CBOs into double-data entry.
- **Bridging HSDS and FHIR:** Help1RVA must architect a two-lane strategy: using HSDS as the source of truth for resource directories, and building a mapping layer to translate this into FHIR ServiceRequest or Task resources for clinical referrals [8].
- **Contractual Access:** Because Unite Us does not offer open public APIs, Help1RVA or its municipal partners must budget for and negotiate access to Unite Us's paid "Data Delivery" or "Integrations" products to achieve automated, bidirectional data flow [10].

## Implementation Roadmap

**0-3 Months: Frontend Overlays and Mobilization**
- Ship the Help1RVA lightweight frontend overlay that deep-links to Unite Virginia and Richmond City Health District forms [17] [15].
- Launch a CBO enrollment drive, emphasizing that the Unite Us platform is free for non-profits [3].
- Define the internal HSDS schema for Help1RVA.

**3-12 Months: Integration and Outcomes**
- Secure funding for Unite Us "Data Delivery" and "Integrations" modules [10].
- Deploy the HSDS-to-FHIR mapping layer to enable seamless data exchange with clinical systems [8].
- Launch a local Community Health Worker (CHW) pilot to replicate the 24.8% reduction in ED visits observed in the Ballad Health deployment [3].

## Risks and Cautionary Notes

- **Do not scrape data:** Unite Us enforces strict privacy policies, limits access to the U.S., and relies on consented data from network participants [6]. Scraping violates these terms and risks Help1RVA's standing with state partners.
- **Avoid bespoke data models:** Introducing unique data fields will exacerbate the administrative burden on CBOs, which the Gravity Project has already identified as a critical pain point in social care reimbursement [9].
- **Manage vendor lock-in:** The acquisition of NowPow by Unite Us highlights rapid market consolidation [7]. Help1RVA must negotiate data portability terms early to ensure municipal data remains accessible regardless of future vendor changes.

## References

1. *Virginia to Partner with Unite Us to Create Statewide Infrastructure Connecting Health and Social Services - uniteus.com*. https://uniteus.com/press/virginia-to-partner-with-unite-us-to-create-statewide-infrastructure-connecting-health-and-social-services-3/
2. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia
3. *VHHA Solutions Enters Partnership with Unite Us to Strengthen Community-Based Health Care Coordination Across Virginia*. https://uniteus.com/press/vhha-solutions-enters-partnership-with-unite-us
4. *Get Help - uniteus.com*. https://uniteus.com/get-help/
5. *Privacy and Security*. https://uniteus.com/privacy/
6. *Unite Us Privacy Policy - uniteus.com*. https://uniteus.com/privacy-policy
7. *NowPow scooped up by Unite Us to broaden its reach in health market | Fierce Healthcare*. https://www.fiercehealthcare.com/tech/unite-us-scoops-up-nowpow-to-broaden-its-reach-social-determinants-health-tech-market
8. *EHR Integration with Social Care Technology*. https://uniteus.com/report/ehr-integration-report/
9. *Payments Data & Exchange Standards: Gravity Project Discovery Findings*. https://uniteus.com/report/payments-data-and-exchange-standards/
10. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/
11. *Sentara Healthcare Optima Health and Unite Us join forces*. https://www.sentara.com/aboutus/news/articles/sentara-healthcare-optima-health-and-unite-us-join-forces-to-connect-patients-and-members-with-local
12. *Optima Health, Unite Us and United ...*. https://unitedwayshr.org/optima-health-unite-us-and-united-way-of-south-hampton-roads-announce-coordinated-care-network/
13. *SDOH and the Gravity Project - SDOH Clinical Care v3.0.0-ballot*. https://build.fhir.org/ig/HL7/fhir-sdoh-clinicalcare/sdoh_challenges_gravity.html
14. *Unite Us: Connecting Communities, Data, & Care*. https://uniteus.com/
15. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/get-help/richmond-city-resources
16. *UChicago Spin-Out NowPow Acquired by Unite Us to Scale, Add Greater Value to More Consumers - Polsky Center for Entrepreneurship and Innovation*. https://polsky.uchicago.edu/2021/09/23/uchicago-spinout-nowpow-acquired-by-unite-us/
17. *Richmond City Health District*. https://www.vdh.virginia.gov/richmond-city