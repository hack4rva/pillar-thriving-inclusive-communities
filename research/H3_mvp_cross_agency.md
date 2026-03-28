> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Building a Honest-Value Navigator MVP in Richmond Without PHI

## Executive Summary

The D3=1 constraint—no cross-agency intake data, no directory exports, no process maps, and strict HIPAA walls—presents a significant but surmountable challenge for building a cross-agency navigation MVP in Richmond. By shifting the product focus from "backend integration" to "intake preparation and transparent wayfinding," the team can deliver immediate value to case managers and residents. 

**Key Strategic Insights:**
* **Public program pages already expose intake-critical details:** FindHelp listings for Richmond show structured fields like "Documents Required" (e.g., photo ID, proof of income/residency, DD214), "Eligibility" (e.g., age bands like 16–29), "Next Steps," "Hours," and "Last Reviewed" dates (e.g., Mar 12, 2026; Nov 14, 2025) [1]. Focusing the MVP on extracting and normalizing "What to bring + How to apply + Who to call" delivers immediate utility without crossing HIPAA boundaries.
* **State portals standardize the "official" path for core benefits:** VDSS and CommonHelp publicly centralize SNAP, TANF, Medicaid, and Energy Assistance with dedicated helplines (833-5CALLVA, 855-635-4370) and comprehensive verification checklists spanning identity, residence, income, resources, and expenses [2] [3]. Anchoring the MVP's eligibility prep to these official pages reduces misinformation risk.
* **Data gap visibility is a feature, not a flaw:** Public pages frequently omit key details. For example, a 211 Virginia Housing Voucher page simply states, "Call for eligibility criteria" and "Specific documents are required" [4]. By utilizing UX best practices like USWDS Alerts [5] and GOV.UK's emphasis on showing when content was last updated [6], the MVP can build trust by explicitly showing what is known, what is missing, and when it was last verified.
* **A lightweight taxonomy can credibly route needs to agencies now:** FindHelp categories (e.g., help pay for housing, government benefits) [7] [8] and CommonHelp's benefit types provide a ready-made, public-facing need taxonomy [3]. Furthermore, the Unite Us "Get Help" form promises navigator outreach within two business days without requiring a directory export [9]. 

## Context and Constraints: Delivering Useful Navigation Without PHI

The D3=1 constraint prohibits data sharing, but Richmond's public program pages and state portals expose enough intake-critical information to build a credible, honest MVP. 

### What D3=1 Means in Practice
Under this constraint, the team cannot access anonymized intake data, cannot export structured service directories from Help1RVA/FindHelp/UniteUs, and cannot map how a resident moves between agencies using backend case data. We must rely solely on public-facing content and avoid any storage or processing of case-level Protected Health Information (PHI).

### User Value Under Constraint
When backend integration is impossible, preparation and routing become the primary value drivers. Providing a consolidated view of "What to bring + where to go + how to apply" reduces friction for case managers and residents today. The MVP acts as a transparent overlay that helps users navigate the fragmented ecosystem without pretending to be a centralized, real-time database.

## Recommended MVP: Intake Prep + Pathway Map + Needs Router

To deliver immediate value while making the data gap visible, the recommended approach is an integrated MVP that combines a lightweight service taxonomy, visual pathways, and an intake guide. 

### Why This Combination Works in Richmond Now
Public fields on FindHelp, 211 Virginia, VDSS, CommonHelp, and Unite Us cover documents, eligibility, next steps, and contacts—everything needed for preparation and wayfinding. For instance, VDSS explicitly lists acceptable verification documents for identity (driver's license, voter card), expenses (leases, utility bills), and income (pay stubs, award letters) [2]. By aggregating these public requirements, the MVP helps users gather the right paperwork before they ever make a phone call or step into an office.

### Scope the MVP to High-Impact Scenarios
To prove feasibility, the MVP should be scoped to 3–4 high-volume pathways that show cross-agency movement without data sharing:
1. **Pregnant parent:** WIC + SNAP
2. **Unemployed adult:** Unemployment Insurance + SNAP
3. **Senior or disabled adult:** Auxiliary Grant + Housing Voucher

## Comparative Approaches: What to Build, Data Needed, and Limitations

All three viable approaches identified in the research phase have strengths and weaknesses. The integrated MVP blends their strengths and mitigates their gaps.

| Approach | What the team builds | Public data needed (how to get it) | What the demo shows | Honest limitations |
| :--- | :--- | :--- | :--- | :--- |
| **1) Pathway map (public info only)** | Visual flows for 3–4 scenarios (e.g., WIC+SNAP, UI+SNAP) with steps, required docs, and contacts. | VDSS/CommonHelp verification and apply pages [2] [3]; FindHelp/211 program pages with "Documents Required" and "Next Steps" [4] [1]. | Click-through journey: steps, "what to bring," official apply links, contacts; dotted lines for unknowns; "Last checked" badges. | No live status/capacity; some steps are generic and vary by provider; phone calls are still required. |
| **2) Intake guide for case managers** | Structured checklists per org/program (docs, eligibility, hours, language, best contact). | FindHelp/211 pages (e.g., SNAP interview proof list [10]); agency pages. | Search program → see intake checklist; confidence tier; "Update at source" links. | Coverage is partial; details may change; relies on external owners to update. |
| **3) Service taxonomy tool** | Need-to-program router (10–12 need categories) mapping to public pages and official portals. | FindHelp categories [8]; CommonHelp benefits taxonomy [3]; Unite Us public "Get Help" intake [9]. | User selects need → top programs + apply routes/screeners (e.g., mRelief SNAP screener [11]). | No personalization without PHI; risk of false positives if eligibility nuances are missing. |

*Takeaway: By combining the visual flow of the pathway map with the structured checklists of the intake guide and the routing capability of the taxonomy tool, the MVP provides a comprehensive, albeit manual, navigation aid.*

## Data Acquisition Plan: Zero-PHI, Public-Only Harvesting

The data acquisition strategy relies entirely on compiling structured fields from public directories and state portals, storing only public content and provenance data.

### Sources and Fields to Compile

| Source | Confirmed public fields (examples) | Notes |
| :--- | :--- | :--- |
| **FindHelp / Help1RVA** | Documents Required (proof of residency, income, DD214), Eligibility (age/income), Next Steps (apply link/phone), Hours, Languages, Cost, Coverage Area, Last Reviewed dates [1] [11]. | Provider claim/update flows exist [12] [13]; shows "Best way to connect" [1]; claims large coverage. |
| **211 Virginia** | Eligibility (often "Call for eligibility criteria"), Application Process (appointment/written app/docs), Hours, Phone, Email, Language (e.g., Spanish) [4]. | Summaries vary in detail; use contact info as the authoritative fallback. |
| **VDSS / CommonHelp** | Program categories, apply links, helplines (833-5CALLVA, 855-635-4370), verification checklists (identity, residence, income, resources, expenses), forms (PDF) [2] [3] [10]. | Aligns users to official processes; lowest misinformation risk. |
| **Unite Us (public)** | "Get Help" confidential form; navigator outreach within two business days; privacy statement [9]. | No directory export available; provide as an escalation/assistance option for users needing human help. |

*Takeaway: Prioritize extracting documents, eligibility, next steps, contacts, and last-updated timestamps to build the core database for the MVP.*

### Harvesting Method and Guardrails
Data will be gathered through manual curation and semi-automated capture of public pages. The system will store the provenance (source URL) and a "last checked" timestamp for every data point. Absolutely no PHI collection or intake will occur within the MVP itself; all applications will be routed to official state portals or provider websites.

## Product Design: Making the Data Gap Visible and Helpful

To build trust, the MVP must use transparency patterns to communicate uncertainty without eroding confidence. 

### UX Patterns to Implement
* **"Last Checked" Badges:** GOV.UK research highlights that users need to know how up-to-date content is and what has changed [6]. Every program listing must display a "Last checked: [Date] via [Source]" badge.
* **Confidence Tiers:** Programs with complete data (docs, eligibility, next steps, recent date) get a "High" confidence tier. Programs with only a phone number get a "Low" tier.
* **Null vs. Error vs. Empty States:** As UX best practices dictate, distinguish between these states [14]. If a program's eligibility is unknown, use a neutral empty state (e.g., "Eligibility details not published. Call to confirm.") rather than an error state.
* **Skeleton Screens:** Use skeleton screens as placeholders while users wait for data to load, indicating that the system is working but data is being retrieved [15].
* **"Update at Source" Links:** Since FindHelp offers "Claim Programs" and "Suggest Program" flows [12] [13], include links directing providers to update their information at the source directory, reinforcing that the MVP is an overlay, not a shadow directory.

### Accessibility and Plain Language
Utilize USWDS components, such as Alerts for system status messages [5], and maintain a 6th-grade reading level. Include bilingual prompts where sources indicate Spanish availability, as seen in 211 Virginia listings [4].

## Demo Script Outline: An Honest, Useful Walkthrough

The demo must show immediate value (prep and routing) while explicitly calling out what will improve once data-sharing agreements are in place.

### Scene 1: Pregnant parent seeking food support (WIC + SNAP)
* **Action:** User selects "Food Assistance" and "Pregnant."
* **Display:** The MVP shows a combined checklist. For WIC, it lists required ID, proof of income, proof of residency, and a proof of pregnancy letter [1]. For SNAP, it notes that an interview and proof of identity/residence are required [10].
* **Honest Framing:** Point out the "Last checked" dates. Show the link to the CommonHelp portal to apply [3]. Explicitly state: *"Because we don't have backend integration, we can't submit the application for them, but we ensure they have the exact documents VDSS requires before they click apply."*

### Scene 2: Unemployed adult (UI + SNAP)
* **Action:** User selects "Unemployment" and "Food Assistance."
* **Display:** The MVP outlines the Virginia Employment Commission steps (registering for work within 5 days, maintaining an active search) [1] alongside SNAP proofs. 
* **Honest Framing:** Highlight the "Best way to connect" phone numbers. Show a clear disclaimer: *"No live capacity data available. Call to confirm availability."* Explain that without a permitted data export, capacity data is often stale.

### Scene 3: Senior/disabled adult (Auxiliary Grant + Housing)
* **Action:** User selects "Housing" and "Senior/Disabled."
* **Display:** Show Auxiliary Grant eligibility (65+, blind, or disabled; living in an assisted living facility or adult foster care home) [1]. For the Housing Voucher, show the 211 Virginia pattern: "Call for eligibility criteria," "An appointment is required," and the phone number [4].
* **Honest Framing:** Point to the dotted lines and empty states for the Housing Voucher's missing eligibility specifics. State: *"This is the data gap made visible. We route the user to the right phone number, but future data-sharing partnerships will fill in these blanks."*

## Honest Limitations Framing: Turning Constraints into a Roadmap

When presenting to judges or stakeholders, frame the limitations constructively. We will not claim integration or real-time capacity. Instead, we show what is known, what is missing, and what partnerships would unlock next.

### What We Can't Show Yet
We cannot show case linking, real-time program capacity, or cross-agency data flow. We cannot guarantee that a user won't have to repeat their story to multiple agencies.

### What We're Doing About It
We are mitigating these gaps through clear data provenance, providing update pathways back to the source directories, offering navigator escalation (e.g., linking to the Unite Us "Get Help" form [9]), and prioritizing manual coverage of the top 50–100 most critical programs.

## Success Metrics for MVP Pilot

To prove evidence of value without PHI, track the following metrics during the pilot:
* **Time-to-apply reduced:** Are case managers spending less time searching for requirements?
* **Contact success rates:** Are users reaching the right agency on the first try?
* **Checklist completeness:** Are users arriving at appointments with the correct documents?
* **User trust signals:** Positive responses to "Was this helpful?" prompts.
* **Provider update submissions:** Number of clicks on "Update at source" links.

## Roadmap to Full Navigator: From Honest Overlay to Integrated Routing

### Next 90 Days
* Cover the top 50–100 high-volume programs manually.
* Build and refine the 3–4 visual pathways.
* Ship the needs router and instrument analytics to track usage and drop-offs.

### 6–12 Months
* Secure MOUs with 211 Virginia, FindHelp, and Unite Us to align on taxonomy and explore data freshness APIs.
* Automate freshness checks for public pages.
* Begin piloting closed-loop referrals with explicit user consent, moving toward a fully integrated, HIPAA-compliant navigator.

## References

1. *financial assistance programs in Richmond, va | findhelp.org*. https://www.findhelp.org/money/financial-assistance--richmond-va
2. *Benefits - Verification Requirements - Virginia Department of Social Services*. https://www.dss.virginia.gov/benefit/verification.cgi
3. *CommonHelp - Virginia.gov*. https://commonhelp.virginia.gov/
4. *Housing Voucher - Richmond, Richmond Redevelopment and Housing Authority*. https://search.211virginia.org/search/18fe0f28-fb08-57bd-b698-b326e2f88faf
5. *Alert | U.S. Web Design System (USWDS)*. https://designsystem.digital.gov/components/alert/
6. *Service manual discovery findings - Data in government*. https://dataingovernment.blog.gov.uk/2015/09/16/service-manual-discovery-findings/
7. *government benefits programs in Richmond, va | findhelp.org*. https://www.findhelp.org/money/government-benefits--richmond-va
8. *help pay for housing programs in Richmond, va*. https://www.findhelp.org/housing/help-pay-for-housing--richmond-va
9. *Unite Virginia – Closed-Loop Coordinated Care Network | Unite Us*. https://uniteus.com/networks/virginia/get-help/get-help-6/
10. *Supplemental Nutrition Assistance Program (SNAP) - Virginia Department of Social Services*. https://www.dss.virginia.gov/benefit/snap.cgi
11. *help fill out forms programs in Richmond, va | findhelp.org*. https://www.findhelp.org/care/help-fill-out-forms--richmond-va
12. *Join the Network - Help1RVA*. https://help1rva.org/claims
13. *Fetched web page*. https://help1rva.org/suggest-program
14. *Filling the Void: Designing for Data Visualization’s Quiet Moments | by Prerna Shaurya | Medium*. https://medium.com/@prernashaurya1/filling-the-void-designing-for-data-visualizations-quiet-moments-ec7dff31b8f5
15. *Skeleton Screens 101 - NN/G*. https://www.nngroup.com/articles/skeleton-screens/