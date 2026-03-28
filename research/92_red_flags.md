> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Red Flags Playbook for Immigrant-Service Tools in Richmond

## Executive Summary

Building civic technology for immigrant and refugee communities in Richmond requires navigating a minefield of hidden risks. Good intentions are insufficient when a single data leak or mistranslation can jeopardize a resident's safety, legal status, or access to essential services. This playbook identifies the critical "red flags" that must trigger immediate concern during the research, design, and build phases of any service access tool.

The most severe risks stem from invisible metadata leaks, where tools claiming to be "anonymous" transmit IP addresses and behavioral data to third parties. Furthermore, reliance on machine translation without human oversight introduces safety-critical errors, such as flipping eligibility requirements or misstating legal statuses. Finally, design choices that mimic government surveillance or over-claim a prototype's readiness can trigger severe "chilling effects," causing vulnerable populations to avoid services altogether. By implementing strict data minimization, mandatory human translation reviews, and transparent community governance, teams can build useful tools safely and honestly.

## Why This Playbook Matters Now — Prevent harm while improving access

In Richmond’s immigrant and refugee context, the highest risks come from invisible metadata leaks, mistranslation, and design that triggers chilling effects. Vulnerable residents often navigate a complex web of fear regarding immigration enforcement and public charge rules. When civic tech tools fail to protect privacy or communicate accurately, they do not just fail to deliver a service—they actively cause harm. We can build useful tools safely, but it requires strict guardrails, honest scoping, and a refusal to compromise on privacy and language quality.

## Risk Area 1: False Sense of Safety — Stop invisible data exhaust

**Description of the specific risk:**
"Anonymous" claims collapse when IP addresses, cookies, or hosting providers can reveal users' identities. Tools that market themselves as requiring "no papers" or being "completely private" often still utilize third-party trackers, analytics SDKs, or content delivery networks (CDNs) that log identifiable metadata. This creates a false sense of safety, encouraging undocumented residents to engage with a tool that is quietly leaking their location and behavior. Furthermore, under the U.S. CLOUD Act, technology companies can be required to provide data in their possession in response to a warrant, regardless of where the data is stored [1] [2]. 

**Real-world example:**
A major investigation by The Markup found that 33 of Newsweek's top 100 hospitals in America had the Meta Pixel tracker installed on their websites [3]. When patients clicked buttons to schedule doctor's appointments, the pixel sent Facebook a packet of data connected to an IP address, creating an intimate receipt of the appointment request [3]. In some cases, the pixel transmitted first names, last names, email addresses, and phone numbers entered into booking forms [3]. HIPAA explicitly lists IP addresses as one of the 18 identifiers that can qualify data as protected health information [3]. Additionally, common practices like IP address truncation fail to provide actual anonymization; truncated IPs remain personal data because they can be combined with other metadata to enable user identification [4].

**Design or process guardrail:**
Ban third-party pixels, trackers, and external analytics by default. Self-host analytics with logging turned off. Publish a plain-language threat model and a "what we don't collect" banner. For high-risk use cases, offer a no-log access path, such as a paper form, a phone hotline, or guidance on using privacy-enhanced browsers.

### Hidden Identifiers and Safer Defaults

| Data/Mechanism | Typical Leak Path | Real-World Risk Evidence | Safer Default |
| :--- | :--- | :--- | :--- |
| **IP Address** | Server, CDN, and analytics logs | HIPAA lists IP as an identifier; IP truncation fails to anonymize [3] [4]. | Disable logs; use cryptographic hashing with strict key management; cap retention at ≤7 days. |
| **Third-Party Pixels (e.g., Meta Pixel)** | Browser-level exfiltration | 33 of top 100 hospitals leaked appointment clicks and PII to Facebook [3]. | Remove third-party scripts; implement strict Content Security Policy (CSP) blocks. |
| **Error Monitoring SDKs** | Background telemetry | Often capture IP, device state, and user inputs by default. | Self-host monitoring tools with IP collection disabled; aggressively scrub PII fields. |

## Risk Area 2: PII Exposure & Data Collection — Minimize, encrypt, delete

**Description of the specific risk:**
Collecting personal information from undocumented or recently arrived immigrant residents carries immense risk. Even "Non-PII" like IP addresses, precise geolocation, device fingerprints, and search queries linked to sensitive topics can expose individuals when combined. Current evidence shows a high re-identification rate for health data that is not properly de-identified [5]. In Virginia, strict legal frameworks govern data handling; for example, the unlawful disclosure of confidential social services records is a Class 1 misdemeanor [6].

**Real-world example:**
Organizations often believe they are protecting users by truncating IP addresses (e.g., changing `192.168.1.42` to `192.168.1.0`). However, European data protection authorities have repeatedly ruled that truncated IPs remain personal data because they reveal ISP, geography, and organization information, and can be combined with timestamps and user agents to identify specific individuals [4]. Treating this data as "anonymous" creates significant compliance and exposure risks [4].

**Design or process guardrail:**
Design for data minimization: collect zero identifiers by default. If network data is necessary, cryptographically hash it with strict key management and implement short retention periods (e.g., 7 days). Provide an offline or on-device mode where feasible. Explicitly state "no SSN/papers required" but pair it with truthful caveats about inherent network risks.

### Data Types vs. Exposure Risk vs. Mitigation

| Data Type | Why It's Risky | Evidence / Source | Mitigation |
| :--- | :--- | :--- | :--- |
| **IP Address** | Linkable to specific households; subject to law enforcement access. | HIPAA identifier list; CLOUD Act data access [3] [1]. | Turn logging off; use proper encryption instead of truncation [4]. |
| **Precise Location** | Infers sensitive visits (clinics, legal aid, shelters). | High re-identification rates in datasets [5]. | Do not collect; if needed for routing, round to a large geohash locally on the device. |
| **Device Fingerprint** | Creates a persistent cross-site ID without cookies. | Enables user identification when combined with metadata [4]. | Disable fingerprinting scripts; utilize user agent reduction; block cross-site scripts. |
| **Sensitive Search Queries** | Reveals immigration status or specific medical/legal needs. | Meta Pixel transmitted search terms like "pregnancy termination" [3]. | Do not include search terms in URLs; use POST instead of GET requests; scrub referrers. |

## Risk Area 3: Mistranslation & Language Quality — Safety-critical content needs humans

**Description of the specific risk:**
Relying on low-quality machine translation in civic service contexts causes documented harms. AI translation models frequently struggle with context, nuance, and domain-specific terminology. The most dangerous errors involve eligibility misrepresentation, incorrect phone number or date formats, and inaccurate intake requirements. These errors are not merely cosmetic; they can result in denied services, legal jeopardy, or severe health consequences.

**Real-world example:**
A 2025 study comparing AI translation to professional human translation for hospital discharge instructions found that AI translations were consistently inferior in Simplified Chinese, Somali, and Vietnamese [7]. The AI-translated instructions had clinically impactful errors in 88.2% of Chinese sets, 82.4% of Vietnamese sets, and 97.1% of Somali sets, compared to only 23.5% for Spanish [7]. In civic contexts, machine translation has translated "polling place" to "Electoral College," and flipped the meaning of legal statements from "I am not in federal prison" to "I am in a federal prison" [8]. Reviewing and correcting these AI mistakes creates an "extra layer of work" for human translators who must "clean up the mess" [9].

**Design or process guardrail:**
Do not ship auto-translated civic content without human quality assurance. Adopt a minimal verification loop: (1) establish a glossary/word bank for local civic terms; (2) require native-speaker review; (3) conduct back-translation spot checks; and (4) perform community validation on critical flows like intake and eligibility. Prioritize human review for languages of lesser diffusion that are common in Richmond.

### Language Risk Profile for Richmond

| Language | Evidence of AI Error Risk | Stakes in Local Services | Required Review Steps |
| :--- | :--- | :--- | :--- |
| **Spanish** | AI performance is similar to professional translators in some domains, but fluency remains inferior [7]. | High volume of users; errors impact broad populations. | 1 human review + glossary check; spot back-translation. |
| **Simplified Chinese** | 88.2% of AI-translated instruction sets contained clinically impactful errors [7]. | High risk of critical eligibility or medical misunderstandings. | 2 human reviewers + back-translation + community testing. |
| **Vietnamese** | 82.4% of AI-translated instruction sets contained clinically impactful errors [7]. | High risk of critical eligibility or medical misunderstandings. | 2 human reviewers + back-translation + community testing. |
| **Somali** | 97.1% of AI-translated instruction sets contained clinically impactful errors [7]. | Extreme risk of severe miscommunication. | Human-first translation; avoid machine drafts entirely. |

## Risk Area 4: Data Walls & Cross-Agency Sharing — Build without privileged access

**Description of the specific risk:**
Hackathon teams and rapid-prototyping groups often assume they can easily integrate data across different government agencies to create a "seamless" user experience. However, strict legal and policy barriers prevent cross-agency client data sharing in Virginia. Attempting to bypass or ignore these walls risks severe legal penalties and project failure.

**Real-world example:**
Under Virginia Code § 63.2-104, records and information concerning applicants for and recipients of social services are confidential; unlawful disclosure by any person is a Class 1 misdemeanor [6]. Accessing the Virginia Longitudinal Data System (VLDS) is restricted to researchers with an approved study and agency sponsorship, and requires signing a Data Sharing Memorandum of Agreement and going through a formal Data Governance Council approval process [10]. Similarly, the Commonwealth of Virginia Data Trust requires formal User Agreements [11]. 

**Design or process guardrail:**
Scope hackathon solutions to operate without cross-agency PII. Rely exclusively on public open data, synthetic data, or client-controlled, consent-based referrals. If the concept truly requires data exchange, map out a multi-year policy and agreement pathway in the project roadmap rather than attempting to demo with live client data.

### Access Reality Check (Hackathon vs. Production)

| Data / Capability | Hackathon Access | Needs MOU / Agreement | Multi-Year Policy Effort |
| :--- | :--- | :--- | :--- |
| **DSS Client Data** | No access | Yes (Subject to Va. Code § 63.2-104) [6] | Yes |
| **School Records (FERPA)** | No access | Yes | Yes |
| **Health Scheduling Data** | No access | Yes (HIPAA Business Associate Agreements) | Possibly |
| **VLDS Cross-Agency Linkage** | No access | Yes (Sponsor + MOA + Council Approval) [10] | Yes |

## Risk Area 5: Trust Erosion Through Bad Design — Avoid patterns that feel like surveillance

**Description of the specific risk:**
Even if a tool is technically secure, design patterns that mimic government surveillance or law enforcement can erode trust and trigger "chilling effects" within immigrant communities. Forms that look like official government applications, demand too many required fields, or use surveillance-coded language (e.g., "we track your progress") cause users to abandon the service out of fear.

**Real-world example:**
The "public charge" rule created widespread chilling effects, causing eligible immigrant families to avoid public benefit programs for fear of immigration consequences [12]. In 2019, 15.6% of adults in immigrant families, and 26.2% of adults in low-income immigrant families, reported avoiding noncash government benefit programs (like Medicaid, CHIP, or SNAP) for fear of risking future green card status [12]. Furthermore, USCIS actively warns immigrants about common scams involving websites that look like official government portals, meaning lookalike designs inherently trigger suspicion [13].

**Design or process guardrail:**
Co-brand tools with trusted community-based organizations (CBOs). Avoid government-form aesthetics for non-government tools. Eliminate surveillance-coded language. Minimize mandatory fields to only what is strictly necessary. Place a prominent "not connected to immigration enforcement" statement on the landing page, vetted by local legal partners.

### Design Do's and Don'ts for Immigrant Trust

| Pattern | Why It's Risky | Evidence | Safer Alternative |
| :--- | :--- | :--- | :--- |
| **Government-Style Seals** | Triggers fear of enforcement or confusion with scams. | USCIS scam warnings regarding lookalike sites [13]. | Use clear community co-branding and distinct, welcoming aesthetics. |
| **"We track your progress"** | Surveillance-coded language triggers public charge fears. | 15.6% to 26.2% benefit avoidance due to chilling effects [12]. | Use empowering language: "Save your spot" or "Resume later." |
| **Extensive Required Fields** | Feels like an interrogation or official intake. | General privacy fears among undocumented users. | Ask only for what is needed for the immediate next step; allow skipping. |

## Risk Area 6: Over-Claiming Impact — Demo responsibly or lose credibility

**Description of the specific risk:**
Claiming to solve complex service access issues at scale based on a weekend hackathon prototype undermines confidence in the work and sets up community partners for disappointment. Prototypes are not production-ready systems; they lack the security, compliance, and operational maturity required for public deployment.

**Real-world example:**
The 18F De-risking Government Technology guide explicitly states that a prototype is a "disposable artifact of the process, not something that will ever be deployed for public use" [14]. Furthermore, the NIST Artificial Intelligence Risk Management Framework (AI RMF) emphasizes the necessity of documenting limitations, mapping context, and measuring risks before deployment (via the GOVERN, MAP, MEASURE, and MANAGE functions) [15].

**Design or process guardrail:**
Frame demos strictly as "concept validation." Publish a one-page risk register that outlines the tool's limitations: who it is for, who it is not for, which languages have been human-validated, and exactly what data is or isn't collected. Define clear success metrics and a staged rollout plan that includes human safeguards.

## Implementation Guardrails & Checklists — Make it easy to do the right thing

To institutionalize safety, teams must implement strict pre-launch checks, release gates, and ongoing audits. 

* **Pre-launch:** Conduct tracker scans to blocklist pixels, review log settings to ensure IPs are disabled, obtain language QA sign-off, and secure legal review on all disclaimers.
* **Release gates:** Require a formal "no live PII" assertion for all prototypes, update the Software Bill of Materials (SBOM), and mandate a community oversight review.
* **Ongoing:** Run privacy regression tests, re-verify privacy settings after dependency updates, and conduct incident response drills.

### Pre-Launch Red Flag Checklist

| Risk Area | Specific Red Flag | Evidence / Source | Mitigation Owner | Status |
| :--- | :--- | :--- | :--- | :--- |
| **False Safety** | Third-party trackers present | Meta Pixel hospital leaks [3] | Lead Developer | [ ] Pending |
| **PII Exposure** | IP logs enabled or truncated | Truncation fails GDPR/privacy tests [4] | DevOps / Infra | [ ] Pending |
| **Mistranslation** | Unreviewed AI translations | High error rates in Asian/African languages [7] | Content Strategist | [ ] Pending |
| **Trust Erosion** | Gov-lookalike UI or seals | USCIS scam warnings [13] | UX Designer | [ ] Pending |
| **Over-Claiming** | Claims beyond tested scope | 18F prototype guidelines [14] | Product Manager | [ ] Pending |

## Community Governance & Transparency — Build with, not for

Pairing tools with trusted messengers and visible oversight is the only way to counter misinformation and fear. Adults in immigrant families report high levels of trust in government agencies and legal professionals, but rarely get their information from them, relying instead on media and personal networks [12]. 

To bridge this gap, establish a standing advisory group consisting of CBOs and legal aid representatives. Publish meeting notes and rotate community testers to ensure continuous feedback. Provide plain-language privacy labels ("we do not collect X; logs disabled") and publish data request transparency reports to build and maintain trust.

## Appendices — Resources and Templates

To accelerate safe delivery, teams should utilize ready-to-use artifacts:
* **Risk Register:** Aligned with the NIST AI RMF [15].
* **Translation QA Checklist:** Informed by Center for Civic Design guidelines [8].
* **Threat Model One-Pager:** Clearly defining data flows and protections.
* **Demo Transparency Script:** Ensuring limitations are communicated during presentations.
* **Referral Token Pattern Spec:** A technical guide for consent-based, tokenized warm-handoffs that do not expose PII.

## References

1. *Cross-Border Data Sharing Under the CLOUD Act | Congress.gov | Library of Congress*. https://www.congress.gov/crs-product/R45173
2. *Frequently Asked Questions about the U.S. CLOUD Act – Cross-Border Data Forum*. https://www.crossborderdataforum.org/cloudactfaqs/
3. *Facebook Is Receiving Sensitive Medical Information from Hospital Websites – The Markup*. https://themarkup.org/pixel-hunt/2022/06/16/facebook-is-receiving-sensitive-medical-information-from-hospital-websites
4. *Why IP address truncation fails at anonymization - Frank DENIS random thoughts.*. https://00f.net/2025/10/27/ip-anonymization/
5. *
            A Systematic Review of Re-Identification Attacks on Health Data - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC3229505/
6. *§ 63.2-104. Confidential records and information concerning social services; penalty*. https://law.lis.virginia.gov/vacode/title63.2/chapter1/section63.2-104/
7. *Accuracy of Artificial Intelligence vs Professionally Translated Discharge Instructions | Equity, Diversity, and Inclusion | JAMA Network Open | JAMA Network*. https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2839035
8. *Making sure the translation is right: a guide and checklist for reviewing machine translation | Center for civic design*. https://civicdesign.org/subtopics/machine-translation/
9. *AI and Government Workers: Use Cases in Public Administration - Roosevelt Institute*. https://rooseveltinstitute.org/publications/ai-and-government-workers/
10. *VLDS BOOK OF DATA GOVERNANCE VERSION 2.2 Feb. 3 ...*. https://vlds.virginia.gov/media/Pdfs/BookOfDataGovernance.pdf
11. *Commonwealth of Virginia Data Trust User Agreement*. https://www.odga.virginia.gov/media/governorvirginiagov/chief-data-officer/pdf/Commonwealth-Data-Trust-User-Agreement-v1.14.pdf
12. *Amid Confusion over the Public Charge Rule, Immigrant ...*. https://www.urban.org/sites/default/files/publication/102221/amid-confusion-over-the-public-charge-rule-immigrant-families-continued-avoiding-public-benefits-in-2019_3.pdf
13. *Common Scams | USCIS*. https://www.uscis.gov/scams-fraud-and-misconduct/avoid-scams/common-scams
14. *De-risking Government Technology: Federal Agency Field ...*. https://digitalgovernmenthub.org/wp-content/uploads/2022/07/federal-field-guide-4dccc06e01cd56773eb140ff6e6b2805cc517a460d6bff6689e7edd0ef349598.pdf
15. *Artificial Intelligence Risk Management Framework (AI RMF 1.0)*. https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf