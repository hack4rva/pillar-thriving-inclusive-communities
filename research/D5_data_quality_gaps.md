# Turning D3=1 Into Momentum: A standards-first playbook for cross-agency navigation prototypes in 48 hours

## Executive Summary

The D3=1 data readiness score for the Cross-Agency Navigation problem statement reflects a stark reality: there is essentially no usable, pre-packaged data available for hackathon teams. Evaluators found no mock intake datasets, no service directory exports from major vendors, and no process maps detailing resident journeys. However, this constraint is an opportunity to build a highly credible, standards-compliant prototype. 

The viable "minimum dataset" is directory-level, not intake-level. The Open Referral Human Services Data Specification (HSDS) 3.0.1 provides the exact schema needed to support basic search, intake checklists, and referrals without requiring individual Personally Identifiable Information (PII) [1] [2]. Attempting to bypass the data wall by scraping proprietary directories is a critical failure mode; vendors like Findhelp and Unite Us explicitly prohibit scraping, caching, and unauthorized data harvesting in their Terms of Service [3] [4] [5]. Furthermore, privacy regulations such as HIPAA, 42 CFR Part 2 (Substance Use Disorder records), VAWA, and FERPA severely restrict the sharing of individual-level journey data [6] [7] [8] [9]. 

To succeed, teams must curate a lean, public-source HSDS micro-directory or synthetic dataset. A useful cross-agency navigation tool can be built without any live cross-agency data by focusing on process and readiness—delivering a "case manager cockpit" that structures resident needs, generates agency-specific checklists, and outputs a consent-ready referral cover sheet. By explicitly acknowledging data limitations and demonstrating a standards-first architecture ready for authorized data post-event, teams can turn the D3=1 constraint into a winning pitch.

## Context and stakes — D3=1 means no safe, usable data; the win is a standards-first shell that can onboard real data post-event

The data wall is real, but standards exist. A credible prototype shows value without violating Terms of Service or privacy laws, proving it is "data-ready" for future integration.

### What D3=1 practically means for teams

A score of D3=1 means the evaluators found essentially no usable data for this problem statement. Specifically, teams lack a mock or anonymized intake dataset, a service directory export from platforms like Help1RVA, Findhelp, or Unite Us, and a process map showing how a resident moves between agencies. Practically, this implies you cannot demo with scraped vendor data or live PII. You must fabricate or curate compliant substitutes to demonstrate your application's logic and user experience.

### The minimum useful scope for cross-agency navigation

Despite the lack of data, a highly useful tool can still be built. Directory-level guidance (who, what, where, how), intake requirements, and referral handoff mechanisms—without automated eligibility or live capacity feeds—are enough to significantly help case managers. The focus should shift from automated data exchange to process optimization and readiness.

## Minimum viable dataset (MVD) — Lean HSDS profile that supports navigation and checklists

An HSDS-compliant micro-directory with 40–60 services can power search, checklists, and referral handoffs immediately, scaling to authorized feeds later.

### HSDS-backed data elements to include on day 1

The Open Referral HSDS 3.0.1 schema defines core objects that form the foundation of a minimum viable dataset [1] [2]:
* **Organization**: Name, website, contacts, phones [2].
* **Service**: Name, description, status, application_process, eligibility_description, required_documents, contacts, phones, schedules, last_modified [2].
* **Location**: Address, languages, accessibility, phones, schedules [2].
* **Service_at_location**: The joiner object detailing where a service is delivered [2].
* **Optional**: service_capacity (unit, max, available) for aggregate capacity bands [2].

### Field examples and thresholds for a 48-hour build

For a 48-hour hackathon, target a coverage of 10–20 organizations, 40–60 services, and 1–3 locations per organization. Populate the `required_documents` and `application_process` fields from public web pages. Add contacts, phones, and operating hours, and include languages if published. This volume is achievable manually and provides enough depth to demonstrate cross-agency navigation.

## Why the dataset doesn't exist today — Organizational, legal, technical barriers

Data exists, but its distribution is constrained by business models, licensing, and privacy risks, compounded by weak interoperability incentives.

### Organizational/business barriers: Proprietary directories and incentives

Proprietary directories actively block data extraction. Findhelp's Terms of Service explicitly ban screen-scraping, copying, or duplicating materials in any form [3]. Furthermore, Findhelp's CBO program terms forbid persisting or caching API data, requiring display to be based on real-time API use [4]. Unite Us similarly prohibits the harvesting, capturing, or collection of Site Materials without advance written consent [5]. While the 211 National Data Platform (NDP) aggregates data, it requires authorization, and external developers cannot access business intelligence or search tools without a 211.org account [10]. iCarol allows exports (including HSDS 1.1), but this is generally restricted to customers, with one automated monthly export included in standard subscriptions [11].

### Legal/regulatory barriers: Privacy and confidentiality

Privacy rules curb individual-level journey data sharing. While HIPAA may not directly apply to all Community-Based Organizations (CBOs), health care partners often require Business Associate Agreements (BAAs) to share Protected Health Information (PHI) [7]. The 42 CFR Part 2 regulations impose strict confidentiality restrictions on Substance Use Disorder (SUD) patient records [6] [12]. The Violence Against Women Act (VAWA) prohibits the disclosure of personally identifying information of victims without informed, written, reasonably time-limited consent [8] [13]. FERPA sets strict conditions for sharing student education records with community-based organizations, requiring written consent in most cases and threatening a five-year ban for inappropriate redisclosure [9].

### Technical/standards gaps

While HSDS solves directory exchange [1], automated cross-eligibility logic is not fully standardized. The HL7 FHIR Human Services Directory (STU 1) explicitly states that assessing eligibility for services is currently out of scope [14]. Additionally, taxonomy licensing is a hidden blocker. The Inform USA (formerly AIRS) 211 LA Taxonomy requires a license for organizations that maintain records using the taxonomy as an indexing system [15] [16]. Open Referral recognizes this barrier and supports multiple taxonomies, allowing implementers to use any taxonomy without prescribing a specific one [17].

## Data sources feasibility — What you can and cannot use in 48 hours

Do not scrape vendors. Curate public organization pages, use HSDS examples, and synthesize compliant placeholders.

| Source | Public export? | ToS/license barrier | 48h feasibility | Notes |
| :--- | :--- | :--- | :--- | :--- |
| Findhelp (Aunt Bertha) | No | ToS bans scraping/copying; API licensed, no caching [3] [4] | Not feasible | Use only public viewing for research; do not ingest or cache content. |
| Unite Us | No | ToS prohibits harvesting/collection [5] | Not feasible | Network data is gated; exports exist only for partners under contract. |
| 211 NDP | Limited | Requires 211 authorization; tools locked to 211 [10] | Low | Possible only with prior 211 partner and provisioned keys. |
| iCarol | Yes (customers) | Licensed; one automated monthly export standard [11] | Low | Feasible only if your partner is a current customer with export configured. |
| Local org websites | N/A | Public content; respect robots.txt and fair use | High | Curate HSDS fields manually from official pages. |

*Takeaway: Rely entirely on manual curation of public websites and synthetic data generation to avoid severe IP and ToS violations during the hackathon.*

## Anonymized/aggregate substitutes for hackathon prototypes

Use de-identified, aggregate, or synthetic data that aligns with HSDS and privacy guidance to demonstrate value without risk.

| Substitute type | What it enables | Source/method | Privacy status |
| :--- | :--- | :--- | :--- |
| Synthetic HSDS micro-directory | Search, detail pages, contact/visit guidance | HSDS schema + curated public info | No PII |
| Aggregate capacity bands (0–25…) | Triage hints without real-time feeds | HSDS service_capacity with synthetic bands | No PII |
| Eligibility/checklist rules (text) | Universal intake checklists per service | application_process, required_documents fields | No PII |
| Journey templates (anonymized) | Cross-agency process visualization | Public process pages; expert input | No PII |
| Consent form templates | Patient-driven sharing workflows | Legal templates; configurable PDFs | No data until signed; compliant path |

*Takeaway: These substitutes provide enough structural realism to build functional UI components and logic flows without triggering HIPAA, FERPA, or VAWA compliance issues.*

## Three credible prototype approaches despite the data gap

Pick one approach and execute deeply; all three are standards-true, privacy-safe, and demo well.

| Approach | Data required (48h) | What judges will see | Key risks to manage | Post-hackathon path |
| :--- | :--- | :--- | :--- | :--- |
| A. HSDS Micro-Directory + Intake Checklist | 40–60 services; HSDS fields; synthetic capacity | Search by need; service pages; auto-generated checklists | Data freshness; limited coverage | Swap synthetic with authorized 211/iCarol feed |
| B. Process-First "Referral Handoff" Wizard | Journey templates; consent form templates | Guided flow creating referral cover sheet + attachments | No live status/capacity | Integrate secure fax/email/API with partners |
| C. Rules-Light "Eligibility Q&A" Builder | Textual eligibility and docs; no automated eligibility | Step-by-step questions narrowing candidate services | False precision if rules overfit | Add formal rules engine post-MVP; partner review |

*Takeaway: Approach A is the most direct translation of the HSDS standard, while Approach B directly addresses the workflow pain points of case managers.*

## 48-hour execution plan — From zero to credible demo

Timebox curation, automate schema validation, and ship a polished, compliant demo.

### Timeline and roles

* **Hours 0–6**: Define the HSDS profile. Set up the repository and build a content entry spreadsheet. Assign service verticals to team members.
* **Hours 6–30**: Curate public info. Assign 6–8 curators to map 5–8 providers each. Conduct daily QA at hours 18 and 30.
* **Hours 18–36**: Transform spreadsheet data to HSDS JSON/CSV. Run validators, fill gaps, and add 10–20 synthetic capacity entries using the `service_capacity` object [2].
* **Hours 30–44**: Build the UI (search, detail views, checklists, referral cover sheets). Instrument basic analytics.
* **Hours 44–48**: Polish the demo. Prepare compliance and roadmap slides.

### Quality gates and tooling

Implement strict quality gates. Use HSDS schema validation tools to check UUIDs and data types. Run link checks and PII scans to ensure no accidental live data is included. Maintain a ToS/IP checklist to verify no proprietary taxonomy codes (like AIRS) or scraped vendor data slipped in. Ensure basic WCAG AA accessibility and use language tags from the HSDS `languages` array [2].

## Building without cross-agency data — What the tool looks like

A case manager cockpit can deliver real utility using only public and synthetic data. The tool should feature a need intake form that generates a "best match" shortlist based on curated HSDS data. It should provide printable checklists derived from the `required_documents` and `application_process` fields [2]. Include directions, hours, and multi-language notes. Crucially, it should generate a referral cover sheet with consent instructions, saving the case session locally to ensure no server-side PII storage.

## What public data individual organizations publish—and how to compile it

Most providers publish the essentials needed for HSDS fields; structure and normalize them. Typical public fields include services offered, eligibility descriptions, application steps, documents required, fees/cost notes, hours, locations/addresses, phones, emails, languages, access notes, and alerts. 

To compile this, record the source-of-truth URLs and capture the `last_modified` date [2]. Perform light copyediting for clarity and attribute provenance via HSDS metadata objects [2].

## Compliance and IP guardrails — Preempt skepticism

Make compliance a feature of the demo. Explicitly state that no scraping or caching of Findhelp or Unite Us occurred [3] [4] [5]. Confirm that no AIRS-coded data was redistributed without a license [15] [16]; use open tags or plain-language categories instead. Emphasize that no PII is present in the demo, utilizing a patient-driven consent model that respects 42 CFR Part 2, VAWA, and FERPA limitations [6] [8] [9].

## What to tell judges — Honest, confident constraints narrative

"We respected data governance; we're standards-ready and partner-ready."

Use this script framework:
* "We used Open Referral HSDS and HL7 HSD guidance to shape a minimal, exchange-ready dataset."
* "We did not scrape or cache proprietary directories; all data is curated from public pages or synthetic."
* "No PII is in our system; we model consent-driven, compliant referrals for future integration."
* "Our architecture swaps in authorized 211/iCarol feeds post-event; we've lined up X partners for pilots."
* "We published our HSDS sample and validators to accelerate future teams."

## Risk register and mitigations

Name the risks, show the controls.

* **Risk**: Data freshness. **Mitigation**: Present an update cadence plan and highlight the `last_modified` HSDS field [2].
* **Risk**: Taxonomy mismatch. **Mitigation**: Build a taxonomy mapping layer to translate open tags to licensed taxonomies post-event.
* **Risk**: Perceived lack of "real" data. **Mitigation**: Provide clear disclaimers and emphasize the structural readiness of the HSDS schema.
* **Risk**: Over-promising eligibility. **Mitigation**: Keep eligibility rules light and text-based, aligning with HL7 HSD STU 1 scoping [14].

### Appendix A — HSDS field checklist for curators
* **Organization**: name, website, contacts, phones [2]
* **Service**: name, description, status, application_process, eligibility_description, required_documents, contacts, phones, schedules, last_modified [2]
* **Location**: address, languages, accessibility, phones, schedules [2]
* **Service_at_location**: join, optional service_capacity (unit, max, available) [2]

### Appendix B — Sample consent language and referral cover sheet outline
Focus on a patient-driven sharing model. Include fields for patient information, specific records to be disclosed, purpose of disclosure, signatures, and a clear retention/revocation policy, aligning with HIPAA patient-driven sharing guidelines [7].

### Appendix C — Post-hackathon 30-60-90 day data roadmap
* **30 days**: Secure MOUs; expand dataset to 150–250 services; pilot with one agency.
* **60 days**: Request 211/iCarol authorized exports [11]; integrate HSDS ingestion; add taxonomy mapping.
* **90 days**: Soft-launch with two cross-agency workflows; measure time-to-service and handoff success.

## References

1. *Human Services Data Specification (HSDS) — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/overview.html
2. *Schema Reference — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/schema_reference.html
3. *
        Aunt Bertha | Terms of Service
    *. https://www.findhelp.org/legal/terms
4. *Terms for Organizations - Findhelp*. https://company.findhelp.com/cbo-terms/
5. *Terms of Service - uniteus.com*. https://uniteus.com/terms-of-service/
6. *Fact Sheet 42 CFR Part 2 Final Rule | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/regulatory-initiatives/fact-sheet-42-cfr-part-2-final-rule/index.html
7. *HIPAA Compliance in Community Partnerships*. https://healthlawlab.org/wp-content/uploads/2019/10/How-HIPAA-Affects-your-Health-Care-Partnership-2017.pdf
8. *FAQ on the VAWA Confidentiality Provision*. https://www.justice.gov/ovw/page/file/1006896/dl
9. *FERPA and Volunteer and Partnership Organizations*. https://studentprivacy.ed.gov/sites/default/files/resource_document/file/ferpa-and-community-based-orgs_2021.pdf
10. *How to Log Into the API Developer Portal!*. https://register.211.org/Home/LogIntoApiPortal
11. *Share, Collaborate, and Integrate | iCarol*. https://www.icarol.com/software-features/share-collaborate-and-integrate/
12. *
    eCFR :: 42 CFR Part 2 -- Confidentiality of Substance Use Disorder Patient Records
  *. https://www.ecfr.gov/current/title-42/chapter-I/subchapter-A/part-2
13. *34 U.S. Code § 12291 - Definitions and grant provisions | U.S. Code | US Law | LII / Legal Information Institute*. https://www.law.cornell.edu/uscode/text/34/12291
14. *Home - FHIR Human Services Directory v1.0.0*. https://build.fhir.org/ig/HL7/FHIR-IG-Human-Services-Directory/
15. *AIRS STANDARDS AND QUALITY INDICATORS FOR ...*. https://www.211texas.org/wp-content/uploads/AIRS_Standards_9_0_Final-1.pdf
16. *Commonly Asked Questions - AIRS 211 LA Taxonomy*. https://211la.wordpress.com/commonly-asked-questions/
17. *Frequently Asked Questions – Open Referral*. https://openreferral.org/faq/