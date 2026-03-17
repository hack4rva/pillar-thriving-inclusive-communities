# Richmond's Social Care Stack: Making FindHelp, Help1RVA, and Unite Us Work Together

## Executive Summary
Richmond’s social care ecosystem is currently supported by two powerful but disconnected platforms: FindHelp (powering the local Help1RVA directory) and Unite Us (powering the Unite Virginia network). FindHelp excels at public-facing discovery, offering an open-access directory of over 1,800 local programs [1]. Unite Us provides a robust, closed-loop referral network that tracks patient outcomes and is utilized by major health systems and state agencies [2] [3]. 

However, the lack of interoperability between these platforms creates a fragmented experience. Residents and care navigators are forced to toggle between systems, leading to duplicated efforts, outdated information, and dropped referrals. For a 48-hour hackathon, teams cannot rely on backend API integrations due to gated developer access on both platforms; instead, they must focus on front-end UX solutions, deep-linking, and triage workflows that guide users to the right platform without handling Protected Health Information (PHI). Bridging this interoperability gap requires establishing local data governance, standardizing consent, and pursuing vendor-supported cross-linking pilots.

## Why This Matters Now

### Uneven resident experience today drives churn and inequity
Richmond already has both an open directory (Help1RVA/FindHelp) and a referral network (Unite Us). However, aligning when and how each is used is critical to reducing drop-offs and duplicated effort. Currently, residents face avoidable friction without aligned tools. A resident seeking help might find a service on Help1RVA, but the actual referral and outcome tracking might require a care navigator using Unite Us. This disconnect results in duplicated entries, varying language information, and an unclear "what next" after discovery versus referral. Ultimately, this fragmentation disproportionately impacts vulnerable populations, particularly those with Limited English Proficiency (LEP), who may abandon the process when navigating between disconnected systems.

## Platform Footprints in Richmond

### FindHelp/Help1RVA: 1,800+ local programs; City Health listings claimed
FindHelp is deeply embedded in Richmond via Help1RVA, a collaborative initiative that brings a catalog of services into one free platform [1]. Help1RVA advertises "over 1,800 local programs" [1]. Public-sector usage is highly visible: Richmond City Health District (RCHD) programs, such as their Resource Centers, are "claimed" and actively updated on FindHelp with addresses and hours [4] [5]. The City of Richmond's Department of Social Services explicitly directs residents to the Help1RVA directory on its website (URL: https://www.rva.gov/social-services/social-services-helpful-phone-numbers) [6]. 

### Unite Virginia (Unite Us): 85,174 clients served; free CBO access
Unite Virginia is a statewide care network connecting health, government, and community partners [7]. The network reports impressive metrics: 85,174 clients served, 174,229 needs identified, and 94,470 referrals sent [2]. It is built in partnership with the Virginia Department of Health and the Virginia Hospital & Healthcare Association [3]. In the Richmond area, VHC Health utilizes Unite Us to link directly with their Epic electronic health record system [3]. Furthermore, the Virginia Department of Health utilizes Unite Us for community resource assistance requests [8].

### City touchpoints signal both platforms are in the resident journey
The presence of both platforms in official government channels highlights the dual-system reality. While the City of Richmond points residents to Help1RVA for self-service discovery [6], state-level health departments (like the Roanoke Health District) route residents into Unite Us forms for coordinated community health worker contact [8]. 

## How They Work and Business Models

### FindHelp (Aunt Bertha): open search + enterprise "white label" tools
FindHelp (formerly Aunt Bertha) is a Public Benefit Corporation and a certified B Corporation [9]. Its core business model provides free, open access to search for social services [10]. For community-based organizations (CBOs), claiming listings and using basic tools is "100% free, forever" [10]. FindHelp monetizes through enterprise "white label" deployments and advanced care coordination tools sold to healthcare providers, governments, and health plans [11] [10]. Help1RVA is a prime example of a localized, white-labeled FindHelp deployment [1] [10].

### Unite Us: network software with closed-loop referrals
Unite Us operates as a closed-loop coordinated care network. Through the Unite Virginia program, community-based organizations receive access to the Unite Us platform and Insights at no cost [2]. The company generates revenue by selling optional, enhanced products to larger institutions (like health systems and MCOs), such as Integrations (e.g., EHR integrations like Epic), Data Delivery, Social Connector, and specialized Care Coordination features [2] [3]. 

## Privacy, Security, and Consent

### FindHelp safeguards: HITRUST, HIPAA posture, and minimal default data
FindHelp maintains a strong security posture. The platform is HIPAA compliant and a certified HITRUST provider [12]. Data is stored encrypted with AES-256 bit encryption on the Google CloudSQL platform [11]. By default, FindHelp only collects demographic information (name, phone number, email, zip code) and does not require clinical information [11]. The company explicitly states in its privacy policy that it will "never sell social care data" [12]. Access is controlled via role-based permissions and SSO (SAML 2.0) [11].

### Unite Us safeguards: HIPAA/HITRUST/SOC 2; mandatory multilingual consent
Unite Us protects social care information under the same strict security standards required for protected health information (PHI) under HIPAA [13]. The platform is HIPAA-compliant, HITRUST, SOC 2 Type 2, and NIST certified [13] [14]. A major differentiator is its human-centered infrastructure: consent is required and documented for every referral to care, and this consent is translated into 50+ languages [13]. Unite Us also features built-in protections to limit the visibility of highly sensitive information, such as substance use data subject to 42 CFR Part 2 [15] [14].

## Multilingual Access

### Gaps and fixes: English-only listings vs bilingual entries
Language access reveals a significant divergence between platform capabilities and local implementation. On FindHelp/Help1RVA, multilingual access is handled at the listing level, and the quality is uneven. For example, the Virginia Department of Social Services Medicaid program lists both "English, Spanish" [16], while many other Richmond-area listings default to English only [4]. Conversely, Unite Us has operationalized language access at the system level by offering its mandatory consent forms in over 50 languages and multiple formats (large print, secure text, email) [13]. 

## Closed-Loop Referrals in Practice

### Mechanics: statuses, outcomes, and inter-org visibility
The concept of a "closed-loop referral" solves the "what happened next" gap that open directories cannot address. In the Unite Us platform, a closed-loop referral provides deep insight into a client's care journey beyond simply confirming a referral was sent [17]. When a referral is closed, network partners select an outcome from service-specific options (e.g., "received clothing" rather than just "got help") [17]. Distinct fields for "resolved" and "unresolved" allow communities to identify exact gaps in local resources [17]. 

## Developer Access and Hackathon Feasibility

### What's feasible in 48 hours
**INFERENCE:** Based on the available documentation, neither FindHelp nor Unite Us offers a public, open API suitable for rapid, unauthorized hackathon use. FindHelp supports enterprise SSO and data exports for paying customers [11], and Unite Us offers paid integration modules [2], but developer access is gated behind enterprise contracts. 

For a 48-hour hackathon, teams should not attempt backend data synchronization. Instead, realistic deliverables include:
* Building a "choose your path" triage UX that routes users to either Help1RVA for self-service or Unite Us for navigator-assisted referrals.
* Creating deep-link generators that point to specific Help1RVA search categories (e.g., food, housing in ZIP 23223).
* Designing multilingual UI overlays or plain-language consent explainers that prepare residents before they click through to the official platforms.

### Constraints to respect
Hackathon teams must strictly avoid capturing, storing, or transmitting Protected Health Information (PHI). Teams must not scrape the directories, as this violates terms of service and risks utilizing outdated data. All prototypes should rely on linking out to the secure, vendor-hosted environments.

| Dimension | FindHelp / Help1RVA | Unite Us (Unite Virginia) |
| :--- | :--- | :--- |
| **Primary Use** | Public search and self-service discovery | Coordinated, closed-loop referrals and outcomes |
| **Local Presence** | >1,800 local programs; City DSS links here | 85K+ clients served statewide; VHC Health integration |
| **Privacy/Security** | HIPAA posture, HITRUST, AES-256 encryption | HIPAA, HITRUST, SOC 2 Type 2, NIST |
| **Multilingual** | Varies by individual listing (often English-only) | System-level consent available in 50+ languages |
| **API/Dev Access** | Gated/Enterprise (SSO SAML supported) | Gated/Paid Integrations (EHR, Data Delivery) |
| **Cost to CBOs** | Free to claim listings and use basic tools | Free platform and Insights access |

*Takeaway: FindHelp is optimized for broad, free public discovery, while Unite Us is engineered for secure, accountable care coordination among professionals. Both restrict open API access, requiring hackathon teams to focus on front-end routing rather than backend integration.*

## Interoperability Today

### Evidence of the interoperability gap
Currently, Help1RVA (FindHelp) and Unite Us do not natively exchange data in Richmond. **INFERENCE:** This lack of interoperability means that if a resident discovers a service on Help1RVA and needs a formal, tracked referral, their data must be manually re-entered into Unite Us by a care navigator. This gap creates duplicate work for CBOs, who must maintain their program information on FindHelp while managing their inbound referral pipeline on Unite Us. The resident experiences this as friction, often having to repeat their story and demographic information multiple times across different agency touchpoints.

## National Landscape and Standards

### Has anyone solved this?
**INFERENCE:** The national landscape of service directory interoperability remains highly fragmented. Vendors naturally prioritize the security, privacy, and integrity of their own networks over open data exchange. While data standards like the Human Services Data Specification (HSDS) / Open Referral exist to standardize directory data, widespread, automated, bi-directional API integration between competitors like FindHelp and Unite Us has not been solved at scale without heavy, custom enterprise middleware. 

## Richmond Interoperability Plan

### 6-step plan with owners and timelines
To make Richmond's service directories interoperable, the city cannot wait for a national vendor consensus. It requires local governance and a phased approach.

| Step | Owner | Timeline | Dependency |
| :--- | :--- | :--- | :--- |
| **1. Launch Governance WG** | RCHD / OCWB | 30 days | Invitations sent to key stakeholders |
| **2. Top-100 Crosswalk** | WG Data Stewards | 60 days | Program volume data identified |
| **3. Language Cleanup Sprint** | Help1RVA team + CBOs | 60-90 days | Organization engagement |
| **4. Triage Guide Published** | WG + Front-line leads | 45 days | Crosswalk draft completed |
| **5. Vendor Pilot (Crosslinks)** | Vendors + WG | 90-120 days | MOUs and Terms agreed upon |
| **6. Metrics Dashboard** | WG Analyst | 60 days | Data access scope defined |

*Takeaway: Interoperability must begin with human governance (a Working Group) to map the top 100 most-used services across both platforms before attempting any technical pilot.*

## Risk Register and Mitigations

### Avoid the common failure modes
* **Outdated Listings:** On FindHelp, unclaimed or outdated listings lead to misreferrals [4]. *Mitigation:* Set local SLAs for listing updates (e.g., 90-day checks) and assign stewards for the top 100 programs.
* **Network Rejections:** On Unite Us, out-of-network organizations require manual quality review, and inappropriate referrals cause friction [14]. *Mitigation:* Use Unite Us rejection-rate dashboards to target CBO outreach and training.
* **Language Drop-off:** English-only listings alienate LEP residents. *Mitigation:* Launch a bilingual outreach sprint to update Help1RVA language fields.
* **Consent Confusion:** Residents may not understand what they are agreeing to. *Mitigation:* Publish plain-language consent FAQs across all city touchpoints.

## Decisions and Next Steps

### What leaders should approve this quarter
To move from a fragmented ecosystem to a cohesive social care stack, Richmond leaders should immediately approve the formation of a "Directory Governance Working Group" comprising RCHD, OCWB, YMCA/Help1RVA, major CBOs, and health systems. Leaders must fund dedicated data stewardship to maintain the Help1RVA directory and greenlight a limited, read-only cross-linking pilot between the platforms. Finally, health systems and MCOs should budget for Unite Us EHR integrations, while CBOs should be directed to enroll in Unite Us at no cost to standardize the city's closed-loop referral pathways.

***

### Appendix: Facts and URLs
* **Help1RVA / YMCA:** https://www.ymcarichmond.org/resources/help1rva/
* **FindHelp Privacy:** https://company.findhelp.com/privacy-model/
* **FindHelp Terms:** https://go.findhelp.com/hubfs/OnlineCustomerTerms.pdf
* **Unite Virginia Network:** https://uniteus.com/networks/virginia
* **Unite Us Privacy:** https://uniteus.com/privacy/
* **Richmond DSS:** https://www.rva.gov/social-services/social-services-helpful-phone-numbers
* **VHC Health / Unite Us:** https://www.vhchealth.org/news-publications/press-releases/2023/vhc-health-partners-with-unite-us/

## References

1. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/
2. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia
3. *
	VHC Health Partners with Unite Us to Address Critical Community Needs with Coordinated Resources
*. https://www.vhchealth.org/news-publications/press-releases/2023/vhc-health-partners-with-unite-us/
4. *support network programs in Richmond, va | findhelp.org*. https://www.findhelp.org/care/support-network--richmond-va
5. *community support services programs in Richmond, va | findhelp.org*. https://www.findhelp.org/care/community-support-services--richmond-va
6. *Social Services Helpful Phone Numbers | Richmond*. https://www.rva.gov/social-services/social-services-helpful-phone-numbers
7. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/get-help/richmond-city-resources
8. *Community Resource Assistance Request Form - Unite Us - Roanoke Health District*. https://www.vdh.virginia.gov/roanoke/community-outreach-services/resource-request-form
9. *
        Aunt Bertha | Privacy Policy
    *. https://www.findhelp.org/legal/privacy
10. *Claim Programs, Help1RVA Greater Richmond Resource Directory, findhelp*. https://help1rva.org/claims
11. *Data Privacy & Security*. https://cdn.prod.website-files.com/689a7050bcaad62da3ab17d0/68b75772ce18b1ab7e53068b_Data_Privacy_%2526_Security_Policy.pdf
12. *Best Practice Model for Social Care Data Privacy - Findhelp*. https://company.findhelp.com/privacy-model/
13. *Privacy and Security*. https://uniteus.com/privacy/
14. *Unite-Us-FAQ-for-Network-Partners. ...*. https://okvetunited.org/wp-content/uploads/2021/03/Unite-Us-FAQ-for-Network-Partners.pdf
15. *Unite Us Privacy Policy - uniteus.com*. https://uniteus.com/privacy-policy/
16. *help pay for healthcare programs in Richmond, va | findhelp.org*. https://www.findhelp.org/health/help-pay-for-healthcare--richmond-va
17. *Unite Us Closed-Loop Referrals | SDOH Screening & Referrals*. https://uniteus.com/products/closed-loop-referral-system/