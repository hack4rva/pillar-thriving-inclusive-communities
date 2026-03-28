> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Help1RVA as Richmond's Service Backbone — What Works, What Breaks, What To Build Next

## Executive Summary
Help1RVA is the de facto digital service directory for the Greater Richmond area, functioning as a collaborative initiative to connect residents with free or reduced-cost social services [1]. Crucially, Help1RVA is not a bespoke, standalone database; it is a white-labeled instance of the national **Findhelp** (formerly Aunt Bertha) platform [2] [3] [4]. It boasts significant local scale, featuring over 1,800 local programs [1]. 

For a hackathon team building solutions for immigrant and refugee communities, the strategic imperative is to **leverage Help1RVA's existing infrastructure rather than attempting to rebuild or scrape it**. While the platform offers extensive breadth and built-in multilingual support (100+ languages) [2] [5], it suffers from the brittleness of machine translation [6], lacks a public bulk data export [6], and relies entirely on provider self-service for data freshness [7]. Teams should focus on building lightweight, culturally competent UX overlays, curated deep-links, and pre-filled intake flows that bridge the gap between limited-English proficient (LEP) residents and the Help1RVA/Findhelp backend.

## What Help1RVA Is and Who Runs It
Help1RVA operates as a localized portal powered entirely by Findhelp's proprietary software-as-a-service platform [4] [6]. 

While the platform is a "collaborative initiative" [1], the **YMCA of Greater Richmond** acts as a primary operational convenor and navigator hub. The YMCA heavily promotes Help1RVA, offering "Social Needs Navigators" who promise to contact users within 48 hours of completing an intake form on the site [1]. Furthermore, local government partners like Henrico Prevention Services list Help1RVA as a distinct entity with a dedicated phone number (804-360-8767) and a physical address in Richmond (2244 John Rolfe Parkway) [8]. 

Because Help1RVA utilizes Findhelp's infrastructure, all legal governance, terms of service, and privacy policies are dictated by Aunt Bertha/Findhelp, a certified B Corporation [4] [6]. 

## Data Footprint and Categories
Help1RVA provides a massive footprint of regional social safety net data, making it highly valuable for immediate referrals.

The platform hosts **over 1,800 local programs** [1]. The main service categories cover critical social determinants of health, including:
* Housing & Shelter [9]
* Food Insecurity [8]
* Employment and Childcare [1]
* Clothing, Hygiene & Household Essentials [8]
* Out-of-school Time Programming and Extracurriculars [8]

Because the database is so vast, hackathon teams should focus on curating "favorites" folders (a native Findhelp feature) specifically tailored to immigrant and refugee priorities, such as ESL classes, immigration legal aid, and emergency housing [9].

## UX for Limited English Speakers
Help1RVA offers extensive but potentially fragile multilingual support. The platform features a language selector that supports over 100 languages, including critical local immigrant languages like Amharic, Arabic, Dari/Persian, Pashto, Spanish, Swahili, Ukrainian, and Vietnamese [2] [5].

However, this localization appears to rely heavily on automated machine translation. The interface creates barriers through translation artifacts and errors; for example, the platform's own legal footer displays an "Error translating language" message [6]. For a resident with limited English, navigating complex eligibility requirements, intake forms, or PDF attachments via machine translation can lead to critical misunderstandings. 

**Hackathon Action:** Do not rely solely on the native translation toggle. Pre-translate the top 5–8 local languages with human review for your prototype's landing pages, and use plain-language glossaries for complex eligibility terms before deep-linking the user into Help1RVA.

## Adding/Updating Listings and Data Freshness
Help1RVA's data currency is entirely dependent on a decentralized, self-service model. 

Organizations must proactively manage their own data. The process involves searching for a program and clicking a "Claim" button, or using the "Suggest a Program" feature if it is not listed [7]. Once an account is created and verified, organization admins gain access to a suite of tools to edit program listings, update hours and locations, manage inbound referrals, and customize screening forms [7]. 

Because there is no central data-entry team manually verifying all 1,800+ listings, data freshness varies wildly from agency to agency. If an organization experiences turnover and loses its Findhelp login, its listing may stagnate.

## Access, Apps, and Integrations
Help1RVA does not offer a public API or structured data export (like a CSV download) for developers. The Terms of Service explicitly reference a proprietary "Aunt Bertha API," which requires a formal enterprise agreement to access [6]. 

However, mobile and SMS interfaces are robustly supported through the parent company:
* **Mobile Apps:** Residents can use the official "findhelp" app, available on both the Apple App Store (rated 4.3/5) and Google Play [10] [11] [12]. These apps are branded as Findhelp, not Help1RVA, which may require user education.
* **SMS Interface:** The platform supports a Short Message Service (SMS) program. Users can receive text messages to connect to programs, schedule appointments, and receive 24-hour appointment reminders [13]. 

## Ecosystem Comparison
Understanding how Help1RVA fits into the broader landscape is critical. Help1RVA (Findhelp) and Unite Us are often confused but serve fundamentally different purposes and are competing systems [14]. They do not share the same data.

| Platform | Access Model & Data Scope | API / Export | Best Use Case | Key Risks / Limitations |
| :--- | :--- | :--- | :--- | :--- |
| **Help1RVA (Findhelp)** | Public web/app search; 1,800+ local programs [1]. | Proprietary API; no public bulk export [6]. | Public discovery, broad directory search, and quick referrals. | Machine translation errors [6]; data freshness relies on providers [7]. |
| **Unite Us** | Closed-loop referral network among contracted providers [14]. | Partner APIs; enterprise integrations. | Tracking patient outcomes and secure, closed-loop clinical handoffs. | Limited public-facing directory; data is siloed to contracted network partners. |
| **211 Virginia** | Statewide phone helpline and web directory [15]. | Varying export capabilities. | Statewide coverage and immediate phone-based crisis triage. | May lack granular, niche local programs compared to community-curated lists. |

*Takeaway:* If your hackathon solution requires public search and broad resource discovery, use Help1RVA. If it requires HIPAA-compliant outcome tracking between hospitals and shelters, that is Unite Us territory.

## Privacy, Consent, and Trust for Immigrant Users
Privacy is a paramount concern for immigrant and refugee populations. Because Help1RVA uses Findhelp's infrastructure, it is governed by Aunt Bertha's Privacy Policy [4]. 

Key data handling disclosures include:
* **Aggregated Data:** The platform monitors use and compiles "Aggregated Statistics" which it retains sole ownership of and may make publicly available [6].
* **SMS Risks:** The privacy policy explicitly warns that if users communicate via text message, the messages may include Protected Health Information (PHI). Because SMS is unencrypted, there is a risk of interception, and users opt-in "at your own risk" [16].
* **Opt-Outs:** Users can opt out of SMS by texting STOP, END, QUIT, CANCEL, or UNSUBSCRIBE [16].

**Hackathon Action:** Keep your prototype stateless. Do not collect Personally Identifiable Information (PII) in your app; instead, route users directly to Help1RVA for the actual referral to keep sensitive data off your stack. Ensure explicit consent copy is visible before users trigger SMS features.

## Hackathon Assessment: What to Build vs. What to Avoid
Based on the infrastructure limitations, here is a strategic roadmap for a hackathon team.

**What you CAN build using Help1RVA data:**
* **Curated, Translated Pathways:** Build bilingual, plain-language landing pages that deep-link directly into specific Help1RVA category searches or public "favorites" folders [9].
* **Navigator Handoffs:** Create a streamlined mobile UI that pre-fills the YMCA's Help1RVA intake form, ensuring the user gets into the 48-hour callback queue [1].
* **QA Micro-Tools:** Build a tool for volunteers to phone-verify listings and easily submit updates via the platform's native "Report A Change" button [16].

**What requires going around it (or formal partnerships):**
* **Bulk Data Ingestion:** You cannot scrape the site or download a CSV of all 1,800 programs. You must manually curate a static list for your demo or secure an MOU for the Aunt Bertha API [6].
* **Closed-Loop Tracking:** You cannot build a dashboard showing if a user actually received the bed or the food; that requires enterprise access or Unite Us [14].

## Pre-Demo Verification Checklist
Before presenting your solution, verify the following to ensure a flawless demo:
* **Intake Reliability:** Confirm the live intake flow (`/forms/help1rva-intake`) is functional and doesn't return platform error messages [2].
* **Service Currency:** Manually call 10-15 critical programs (e.g., emergency housing, legal aid) featured in your demo to verify their phone numbers and hours are accurate.
* **Language Flags:** Spot-check your deep links in 3-4 target languages to ensure the Help1RVA translation engine doesn't break the page layout or display "Error translating language" [6].
* **SMS Consent:** If demoing the Findhelp app or SMS features, ensure you can clearly explain the PHI risks associated with unencrypted text messages [16].

## Documented Evaluations or Improvement Plans
Extensive searches reveal **no publicly documented evaluations, UX audits, or formal improvement plans** for Help1RVA's specific implementation in Richmond. 

This lack of public evaluation presents a massive opportunity. A hackathon team can add immediate value by conducting a rapid 1-2 day usability audit with LEP residents, documenting translation failures and dead-ends, and presenting this as a prioritized bug-fix report to the YMCA and Findhelp.

## Appendix

### Facts (with URLs)
* Help1RVA is powered by Findhelp (formerly Aunt Bertha) and utilizes its Terms of Service and Privacy Policy (https://help1rva.org/terms, https://help1rva.org/privacy) [4] [6].
* The YMCA of Greater Richmond utilizes Help1RVA for its Social Needs Navigation, citing over 1,800 local programs and a 48-hour contact window (http://ymcarichmond.org/resources/help1rva) [1].
* The platform supports over 100 languages via a translation toggle (http://help1rva.org/claims) [5].
* Organizations can self-manage data via "Claim Programs" and "Suggest Program" workflows (http://help1rva.org/claims) [5] [7].
* Findhelp offers iOS and Android mobile applications (http://apps.apple.com/us/app/findhelp/id970641273) [10] [11].
* The platform's SMS features carry explicit warnings regarding unencrypted Protected Health Information (PHI) (http://findhelp.org/legal/privacy) [16].

### Inferences (Clearly Labeled)
* *Inference:* The YMCA of Greater Richmond is the primary operational owner/funder of the local Help1RVA initiative, given their heavy integration of the platform into their core navigator services and intake flows.
* *Inference:* The multilingual support is highly susceptible to failure for complex legal or eligibility terminology, as it relies on automated machine translation rather than human-localized content.
* *Inference:* The directory contains a significant amount of stale data, as the self-service "claim" model historically results in abandoned listings when nonprofit staff turn over.

## Timeline and Roles for Hackathon Execution
* **Day 1:** Curate a static list of 20-30 high-priority immigrant services. Do not attempt to scrape the API.
* **Day 2:** Build plain-language, human-translated landing pages that deep-link to these specific Help1RVA profiles.
* **Day 3:** Test the YMCA intake handoff and run the Pre-Demo Verification Checklist (phone checks, translation artifact checks). Compile the UX audit to hand back to the YMCA.

## References

1. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/
2. *Help1RVA Greater Richmond Resource Directory*. https://help1rva.org/forms/help1rva-intake
3. *Aunt Bertha is Now Findhelp: Aligning Our Brand to Our Mission*. https://company.findhelp.com/blog/2021/11/21/aunt-bertha-is-now-findhelp/
4. *
        Aunt Bertha | Privacy Policy
    *. https://help1rva.org/privacy
5. *Claim Programs, Help1RVA Greater Richmond Resource Directory, findhelp*. https://help1rva.org/claims
6. *
        Aunt Bertha | Terms of Service
    *. https://help1rva.org/terms
7. *FindHelp-claiming.pdf*. https://www.aapdc.org/wp-content/uploads/2024/05/FindHelp-claiming.pdf
8. *Henrico Prevention Services  – Service Partner Detail*. https://prevention.henrico.gov/partner/?org=sneadk
9. *Housing & Shelter,  | Help1RVA Greater Richmond Resource Directory*. https://ymcarichmond.findhelp.com/print_public_favorites_folder?id=4855446421372928
10. *FindHelp - App Store - Apple*. https://apps.apple.com/us/app/findhelp/id970641273
11. *findhelp - Apps on Google Play*. https://play.google.com/store/apps/details?id=com.auntbertha.webapp.ab&hl=en_US
12. *Frequently Asked Questions (FAQ) - More About findhelp [EXTERNAL FACING PORTAL] - Confluence*. https://auntbertha.atlassian.net/wiki/spaces/PORTAL/pages/2579071066/Frequently+Asked+Questions+FAQ?parentProduct=JSM-Portal&parentProductContentContainerId=10172&initialAllowedFeatures=&locale=en-US
13. *
        Aunt Bertha | Terms of Service
    *. https://www.findhelp.org/legal/terms
14. *findhelp (fka Aunt Bertha) vs Unite Us*. https://marketplace.aviahealth.com/compare/24875/25265
15. *Community Resources Updates August 2025*. https://www.hanovercounty.gov/CivicSend/ViewMessage/message/267163
16. *
        Aunt Bertha | Privacy Policy
    *. https://www.findhelp.org/legal/privacy