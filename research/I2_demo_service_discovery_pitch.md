> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.


# Designing a trust-first, 4-minute demo for Richmond's privacy-safe service finder

## Executive Summary
This report provides a comprehensive, 4-minute pitch script and strategic framework for a privacy-first service discovery tool designed for Richmond's immigrant community. The core insight driving this strategy is that the primary barrier to service discovery is not UX polish, but trust and privacy. By anchoring the narrative in a specific user persona and leveraging established local organizations like Sacred Heart Center [1] and Commonwealth Catholic Charities [2], the demo directly addresses the fear of exposure. The script integrates specific demographic data from the American Community Survey (ACS) [3] and aligns with the City of Richmond's Language Access Plan [4] to satisfy judge criteria for clarity, impact, and accessibility.

## Demo Objectives mapped to Judge Criteria

To maximize impact, the demo explicitly addresses the three core judging criteria within the first 90 seconds.

### D1 Clarity: User and Problem
Our user is María, a mother in Southside with limited English proficiency. Her primary problem is the fear of being exposed, misdirected, or misunderstood when seeking services online. By naming a specific person and fear, we focus the judges on the core trust gap rather than generic statistics.

### D5 Population and Impact: Richmond Demographics
Richmond has a population of 215,961 residents aged 5 and over, of whom 26,090 speak a language other than English [3]. A subset of this population reports limited English proficiency. This tool could help them find services faster and privately, serving as a starting point for community integration.

### D8 Accessibility: Phone-First Design
We designed this specifically for a phone screen, without requiring English, and without requiring a login. This aligns directly with the City of Richmond's commitment to providing meaningful access to persons with Limited English Proficiency (LEP) through initiatives like iSpeak Richmond [4].

## Local Trust Anchors

To reduce discovery risk and bootstrap credibility, the tool surfaces verified information from known-trusted local organizations.

| Organization | Core Mission & Services | Role in Demo | Source |
| :--- | :--- | :--- | :--- |
| Sacred Heart Center (SHC) | Connects Latino families with tools to thrive; offers adult education, youth programs, and a community hub. | Demonstrates Spanish-first programming and strong community trust. | [1] |
| Commonwealth Catholic Charities (CCC) | Largest immigrant service organization in VA; provides refugee resettlement and immigration counseling. | Validates refugee intake and legal navigation pathways. | [2] [5] |
| ReEstablish Richmond | Committed to providing refugee and immigrant communities with resources; curates local legal assistance. | Validates referral-based discovery since they do not provide direct legal services. | [6] |

## Evidence Base and Numbers

The demographic claims in the script are grounded in recent U.S. Census data to ensure accuracy and avoid overclaiming.

### ACS S1601 Essentials for Richmond City
According to the 2020 to 2024 American Community Survey 5-Year Estimates for Richmond city, Virginia, the total population aged 5 years and over is 215,961 [3]. Of this population, 189,871 speak only English, while 26,090 speak a language other than English [3]. 

### City Language Access Context
The City of Richmond has implemented a Language Access Plan and the iSpeak Richmond portal to ensure equitable access to city services for LEP individuals [4]. This institutional context validates the need for multilingual, accessible digital tools.

## Trust Barriers and Design Responses

Each design choice in the application maps directly to a specific user fear and includes a deliberate tradeoff.

| Design Decision | Trust Risk Mitigated | Tradeoff | Mitigation Strategy |
| :--- | :--- | :--- | :--- |
| On-device search, no login, no PII | Fear of exposure and status risk. | Limited personalization and user history. | Optional local-only cache with a manual clear button. |
| Source-first result cards with org logos | Fear of misinformation and scams. | Potential coverage gaps if only verified partners are used. | "Suggest an edit" feature routed directly to partner organizations. |
| "What we don't collect" banner | Fear of hidden tracking and data harvesting. | Less analytics data for the development team. | Rely on partner-led feedback and lightweight, aggregated event counts. |

## 4-Minute Demo Flow

This script provides the exact spoken text, stage directions, and fallback plans for a 4-minute live presentation.

### 0:00-0:30: The User Situation (D1)
**Spoken Text:** "Meet María. She's a mother living in Southside Richmond with limited English proficiency. When she needs to find an after-school program or legal clinic, her biggest barrier isn't just finding a website—it's trust. Our user is María, and her problem is the fear of being exposed, misdirected, or misunderstood online."
**Screen Notes:** Show a simple, clean mobile interface on the projector. No login screen.
**Action:** *Pause for 2 seconds to let the judges connect with the persona.*

### 0:30-1:00: The Trust Barrier and Impact (D5)
**Spoken Text:** "Richmond has 215,961 residents over age five, and over 26,000 speak a language other than English at home. A subset of these residents has limited English proficiency. The real discovery gap is fragmentation across reputable organizations. We built a privacy-first wayfinding tool that could help them find trusted services safely."
**Screen Notes:** Display the home screen with clear language toggles (English/Español).
**Action:** *Presenter toggles the app to Spanish.*

### 1:00-2:30: Realistic Scenario (D8)
**Spoken Text:** "We designed this specifically for a phone screen, without requiring English, without requiring login. Let's say María needs legal help. She types 'legal' in Spanish. Instead of scraping the whole web, our tool searches a curated directory of trusted local anchors. Here, she immediately sees the Sacred Heart Center's Community Hub, and Commonwealth Catholic Charities, the largest immigrant service organization in Virginia. She can tap to call directly, without ever typing her name or address into our app."
**Screen Notes:** Type "ayuda legal" into the search bar. Show result cards featuring the SHC logo [1] and CCC logo [2]. Demonstrate the tap-to-call button.
**Action:** *Pause for 3 seconds after the first result card appears.*
**Fallback Text (if live demo fails):** "Switching to our screenshot backup—as you can see on this slide, the search instantly returns verified cards..."

### 2:30-3:30: Three Design Decisions
**Spoken Text:** "We made three specific design decisions to address trust. First, all searches happen on-device with zero login required, protecting her identity. Second, we use source-first cards displaying the organization's logo and languages served, so she knows exactly who she is calling. Third, we placed a prominent 'What we don't collect' banner at the bottom, alongside a one-tap 'clear history' button."
**Screen Notes:** Scroll down to show the privacy banner. Tap the "Clear History" button and show the screen reset.
**Action:** *Pause to let the judges read the privacy banner.*

### 3:30-4:00: Honest Scope and Continuation Path
**Spoken Text:** "To be clear about our scope: this is a starting point. We did not build an intake system, case tracking, or provide legal advice. This is strictly a directory and wayfinding aid. For our continuation path, we are proposing a 90-day pilot with the Sacred Heart Center as our community champion, and we plan to share our learnings with the City's iSpeak Richmond team to align with their Language Access goals. Thank you."
**Screen Notes:** Show a final slide with the SHC logo, iSpeak Richmond mention, and a QR code to the prototype.
**Action:** *Final pause and transition to Q&A.*

## Content Sourcing and Data Freshness

To prevent stale or unsafe listings, the tool relies on a restricted dataset. The initial database is populated by caching public information from Sacred Heart Center, Commonwealth Catholic Charities, and ReEstablish Richmond. Each result card displays a "last verified" timestamp. A "Report a problem" button is included on every card, which routes directly to a partner inbox, supported by a 48-hour takedown policy for inaccurate listings.

## Scope, Non-Scope, and Compliance

It is critical to state what the tool does not do to avoid overclaiming. This application is a directory and wayfinding tool; it is not a platform for legal advice or case management. It is designed to be a starting point that could help users connect with established services. For compliance, the application avoids collecting Personally Identifiable Information (PII) entirely and clearly shows the provenance of all data displayed.

## Continuation Path and Champion

The proposed continuation path focuses on community integration rather than immediate commercial scaling. The plan involves a 90-day pilot program championed by program leads at the Sacred Heart Center. Success metrics will focus on privacy-safe task completion, such as the number of outbound calls initiated and language toggles used, rather than user retention. Additionally, the team will seek a meeting with the City of Richmond's immigrant engagement team to align the tool with the iSpeak Richmond initiative [4].

## Appendix

**Data References for Live Q&A:**
* **Richmond Population (5+):** 215,961 (ACS 2020 to 2024 5-year, Table S1601) [3].
* **Speak Language Other Than English:** 26,090 [3].
* **City Initiative:** iSpeak Richmond / Language Access Plan [4].
* **Partner Orgs:** Sacred Heart Center [1], Commonwealth Catholic Charities [2], ReEstablish Richmond [6].

## References

1. *Home - Sacred Heart Center*. https://shcrichmond.org/
2. *Refugee Resettlement | Commonwealth Catholic Charities | Virginia| Richmond | Roanoke | Hampton Roads*. https://www.cccofva.org/refugees
3. *S1601: Language Spoken at Home - Census Bureau Table*. https://data.census.gov/table/ACSST5Y2024.S1601?g=0500000US51760
4. *Language Access | Richmond*. https://www.rva.gov/immigrant-engagement/language-access
5. *Commonwealth Catholic Charities (Richmond Office)*. https://www.immigrationadvocates.org/nonprofit/legaldirectory/organization.810948-Commonwealth_Catholic_Charities_Richmond_Office
6. *Immigration Resources — ReEstablish Richmond*. https://www.reestablishrichmond.org/immigration-support