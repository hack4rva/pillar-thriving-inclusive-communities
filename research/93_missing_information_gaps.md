> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Unlocking RVA Service Tools: What to Research vs. What to Assume

## Executive Summary

When building service directory tools and multilingual interfaces for Richmond's immigrant and refugee communities, hackathon teams face critical information gaps. The most significant finding is that Help1RVA operates as a closed instance of the findhelp platform, stewarded locally by the YMCA of Greater Richmond. Teams should treat the core platform as closed and focus on building read-only integrations, verified data overlays, and rapid-language experiments. 

Instead of waiting for perfect datasets, teams must make strategic assumptions to de-risk their demos. This means shipping user interfaces in five priority languages (Spanish, Arabic, Dari, Pashto, and Portuguese) while relying on navigator backstops due to severe local staffing shortages in non-Spanish languages. Channel strategies should prioritize WhatsApp and Facebook using trusted community messengers. For high-risk data like immigration status requirements and real-time capacity, teams must default to manual verification and "call to confirm" safeguards rather than algorithmic assumptions.

## Gap 1: Help1RVA Data Structure and Export

**Current state:** Help1RVA is powered by the findhelp social care network [1] [2]. The YMCA of Greater Richmond acts as a local steward, providing a centralized intake form and navigator follow-up within 48 hours [3]. While there is no public API documented on the site, the underlying findhelp schema is visible through public print views, which expose structured fields including "Eligibility," "Hours," "Next Steps," "About," and "Program availability" [4] [5]. The YMCA also instructs organizations to build out services including "hours of operation, eligibility requirements and program language availability" [3].

**Can research fill it?** Partially. Teams can scrape public print views to understand the schema, but official API access or structured CSV/JSON exports are likely gated by findhelp and the YMCA.

**Pre-demo assumption:** Treat Help1RVA as a closed findhelp instance. Design read-only integrations via print/export views for the demo. Build your data model around the existing findhelp program schema (program, organization, eligibility, languages, hours, availability) and do not invent new core fields. Overlay custom tags (e.g., "no papers required") as a separate, verifiable layer.

## Gap 2: Priority Languages for Richmond Immigrant Population

**Current state:** Regional health actors are actively targeting specific languages beyond Spanish. Bon Secours provides its Community Health Needs Assessment (CHNA) paper surveys in English, Spanish, Portuguese, Arabic, Dari, and Pashto [6]. However, local organizational capacity to serve these languages is highly skewed. According to a 2025 Virginia Department of Health (VDH) survey, 81% of responding organizations have at least one staff member who speaks Spanish, but only 19% have Arabic-speaking staff, 8.3% have Dari-speaking staff, and 0% reported having Pashto-speaking staff [7]. 

**Can research fill it?** Yes, the priority languages are clear, but the gap in service capacity is the actual bottleneck.

**Pre-demo assumption:** Ship version 1 of the multilingual user experience in Spanish, Arabic, Dari, Pashto, and Portuguese. Because local organizations lack the staff to support these languages natively, teams must pair the UI translation with a navigator assist flow and interpretation backstops to offset limited in-language staffing.

### Language Prioritization and Capacity

| Language | Evidence of Need | Local Staff Capacity Signal |
| :--- | :--- | :--- |
| Spanish | Ubiquitous demand; 81% of organizations have Spanish staff [7]. | High |
| Arabic | Included in CHNA materials [6]; 19% staff capacity [7]. | Medium |
| Dari | Afghan arrivals; included in CHNA materials [6]; 8.3% capacity [7]. | Low |
| Pashto | Afghan arrivals; included in CHNA materials [6]; 0% capacity [7]. | Very low |
| Portuguese | Included in CHNA paper availability [6]. | Unknown; assume low-medium |

*Takeaway: While demand exists across multiple languages, the severe lack of Dari and Pashto speaking staff means tools must bridge the gap between translated information and actual service delivery.*

## Gap 3: Communication Channel Usage Patterns

> **STATUS: GAP CLOSED — 2026-03-26**
> Confirmed by Karla Almendarez-Ramos, Manager OIRE, City of Richmond NCS.
> **Confirmed channels:** Facebook (primary, groups), WhatsApp (direct/group messaging), Instagram (younger audiences), YouTube (video content), in-person networks and word of mouth via associations, local radio stations.

**Current state:** OIRE has directly confirmed community channel usage. This aligns with and validates prior research. Facebook groups and WhatsApp are the primary digital channels. Local radio reaches residents with limited digital access. In-person trust networks remain the most reliable channel for hard-to-reach populations.

**Can research fill it?** Yes — now confirmed from the authoritative local source.

**Pre-demo assumption (updated):** Use Facebook groups and WhatsApp as primary distribution channels. Radio and in-person outreach matter for older residents and those with limited digital access. Instagram content is appropriate for younger community members. All channels should be seeded via trusted community messengers, not government accounts.

### Channel and Messenger Hypotheses

| Community | Primary Channels | Trusted Messengers | Initial Content Format |
| :--- | :--- | :--- | :--- |
| Spanish-speaking | WhatsApp, Facebook | Clinicians, community organizers | 30–60s vertical video + WhatsApp cards |
| Arabic-speaking | WhatsApp, Facebook, mosque networks | Faith leaders, clinicians | Video + voice notes |
| Dari/Pashto | WhatsApp groups, in-person navigators | Afghan cultural brokers | Video + step-by-step carousels |
| Portuguese | WhatsApp, Facebook groups | Church leaders, community organizers | Video + event flyers |

*Takeaway: Content format must be tailored to the channel, prioritizing highly shareable, low-literacy-friendly media distributed by established community figures.*

## Gap 3b: Trusted Community Organization List

> **STATUS: GAP CLOSED — 2026-03-26**
> Provided by Karla Almendarez-Ramos, Manager OIRE, City of Richmond NCS.
> See **research/D2_data_community_org_directories.md** for the full verified list.

15 organizations confirmed, including IRC, ReEstablish Richmond, Sacred Heart Center, Afghan Association of Virginia, African Community Network, and others spanning Latino, Afghan, African, Asian, Eastern European, and Salvadorian communities. Also includes a multicultural church database (Google Maps) and Help1RVA + 211 Virginia as recommended service directory platforms.

---

## Gap 4: Organizations Serving Undocumented Residents

**Current state:** There is no consolidated, public dataset of Richmond-area organizations with explicit policies about not requiring immigration documentation. While platforms like FindHello exist to help undocumented people find resources [10], applying a blanket "no papers required" flag to local Help1RVA listings without verification is dangerous.

**Can research fill it?** Limited. It requires manual, case-by-case verification.

**Pre-demo assumption:** Only display a "No immigration documents required" flag when it can be sourced directly to a public policy page or written confirmation logged by an administrator. Otherwise, default to a "Status-neutral services: verify with provider" label and include a click-to-call script for navigators. Mislabeling this information could endanger clients and destroy trust.

## Gap 5: Cross-Agency Referral Pathway

**Current state:** No structured dataset exists mapping the exact sequence of organizations a resident visits. However, qualitative data from VDH notes that many foreign-born individuals struggle with navigating pathways to care [7], and community feedback highlights the need for centralized resource hubs and better navigation support [9].

**Can research fill it?** No. This must be conceptualized without hard data for the demo.

**Pre-demo assumption:** Build three archetype journey maps (e.g., housing crisis, workforce upskilling, reentry). Define explicit handoffs, required documents, and expected wait times based on logical assumptions. Embed a "handoff safeguard" (such as text/email reminders and checklists) and capture drop-off reasons as structured feedback to inform future iterations.

## Gap 6: Help1RVA Improvement Roadmap

**Current state:** The YMCA of Greater Richmond actively recruits programs and provides navigator intake for Help1RVA [3]. The underlying platform is controlled by findhelp, which manages the broader social care network [2]. There is no publicly visible roadmap for multilingual improvements or feature updates.

**Can research fill it?** Yes, through direct stakeholder outreach.

**Pre-demo assumption:** Frame any hackathon concepts as external interfaces, overlays, or data hygiene initiatives rather than core platform changes. Treat the findhelp platform as closed. Request a meeting with the YMCA's Social Needs Navigation lead to align on safe integration patterns.

## Gap 7: Current Service Capacity and Wait Times

**Current state:** Real-time capacity data is highly inconsistent. While some findhelp listings expose a "Program availability: waitlist" status [5], most organizations lack the bandwidth for consistent updates. Organizations report challenges in hiring bilingual staff [7], which further impacts their ability to process new clients efficiently.

**Can research fill it?** Partially, through lightweight manager pings.

**Pre-demo assumption:** Do not auto-rank search results by capacity, as the signal quality is too low. Instead, add a lightweight "capacity ping" form for case managers, display a "last verified" date on listings, and default user guidance to "call ahead" for high-variability services like housing and legal aid.

## Pre-Demo Decision Matrix

| Gap | Criticality | Current State | Can Research Fill Pre-Demo? | Pre-Demo Fallback / Assumption |
| :--- | :--- | :--- | :--- | :--- |
| 1. Help1RVA Data | High | Findhelp platform; print views expose schema [4]. | Partial | Use print views; model around findhelp fields. |
| 2. Priority Languages | High | Spanish, Arabic, Dari, Pashto, Portuguese indicated [6]. | Yes | Support 5 languages; rely on navigator backstops. |
| 3. Channels | High | WhatsApp/Facebook effective [8]. | Partial | Launch short-video pilot via trusted messengers. |
| 4. Undocumented Orgs | High | No consolidated list. | Limited | Verify manually; default to "verify with provider". |
| 5. Referral Pathways | Critical | No dataset; navigation friction exists [7]. | No | Prototype 3 journey maps with handoff safeguards. |
| 6. Help1RVA Roadmap | Medium | YMCA stewards [3]; findhelp controls platform [2]. | Yes | Treat platform as closed; build external overlays. |
| 7. Capacity/Waits | Medium | Inconsistent; occasional waitlist flags [5]. | Partial | Show last-verified date; avoid auto-ranking. |

*Takeaway: Teams must explicitly state these assumptions during their demos to demonstrate strategic thinking and risk mitigation.*

## Data Integration and Governance

To build a compliant, low-friction pipeline, teams should utilize whitelisted scraping of public print pages from Help1RVA, caching the data with clear provenance. The data model must map directly to the findhelp schema while maintaining strict audit trails for sensitive custom flags (like undocumented status). Teams must respect terms of service, implement rate limiting, and store minimal personally identifiable information (PII).

## Rapid Experiments

Teams should execute a 14-day validation plan:
* **Sprint 1 (Days 1–7):** Produce and transcreate two core FAQ videos per priority language. Distribute these via recruited trusted messengers and track share rates and click-throughs.
* **Sprint 2 (Days 8–14):** Deploy in-product prompts and QR codes at partner sites to collect language and channel preferences via a brief intercept survey.

## Risk Register and Mitigations

The most severe risks involve mislabeling immigration requirements, misrouting clients to out-of-region services (as findhelp can surface non-local programs [5]), and displaying stale capacity data. Mitigate these by enforcing strict geographic filtering, requiring manual verification for sensitive tags, displaying "last verified" timestamps, and establishing clear recruitment standards for trusted messengers.

## Stakeholder Map and Outreach Plan

Early alignment is critical. Priority contacts include the YMCA Social Needs Navigation team (for Help1RVA alignment), findhelp support, and local partners listed by the health district, such as the International Rescue Committee, Commonwealth Catholic Charities, and ReEstablish Richmond [10].

## Appendices

To accelerate fieldwork, teams should prepare:
* Call scripts for verifying "no papers required" status.
* Capacity ping micro-forms for case managers.
* Messenger agreement and micro-grant templates.
* Content templates for video scripts and WhatsApp cards.
* Journey map stencils featuring handoff safeguards.

## References

1. *
        Help1RVA Greater Richmond Resource Directory
            | Accessibility
    *. https://help1rva.org/legal/accessibility
2. *Claim Programs, Help1RVA Greater Richmond Resource Directory, findhelp*. https://help1rva.org/claims
3. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/
4. *Summer Out of School Time ,  | Help1RVA Greater Richmond Resource Directory*. https://ymcarichmond.findhelp.com/print_public_favorites_folder?id=5487226800701440
5. *Housing & Shelter,  | Help1RVA Greater Richmond Resource Directory*. https://ymcarichmond.findhelp.com/print_public_favorites_folder?id=4855446421372928
6. *Bon Secours Conducting Richmond Community Health Needs Assessment*. https://www.bonsecours.com/about-us/news/richmond/2025/january/bon-secours-seeks-input-from-richmond-residents-for-community-health-needs-assessment
7. *2025 Community Health Assessment*. https://www.vdh.virginia.gov/content/uploads/sites/114/2025/03/2025-Community-Health-Assessment_FINAL-DRAFT-for-comment.pdf
8. *How to Find and Collaborate with Trusted Messengers - New America*. https://www.newamerica.org/new-practice-lab/reports/communicating-with-immigrant-and-non-english-speakers-about-the-covid-19-vaccine/how-to-find-and-collaborate-with-trusted-messengers/
9. *Community Conversations*. https://www.vdh.virginia.gov/content/uploads/sites/24/2025-CHA-Appendix-D_Community-Conversations.pdf
10. *Office of New Americans-Refugee Services - Richmond City Health Department*. https://www.vdh.virginia.gov/richmond-city/sample-page/programs/new-americans-refugee-services/