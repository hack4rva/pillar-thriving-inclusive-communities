> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Trust Lessons from Failure: Avoiding Privacy and Adoption Pitfalls in Immigrant-Serving Tech

## Executive Summary

Digital gatekeeping backfires when tools are effectively mandatory but poorly designed for vulnerable populations. The CBP One app became the de facto gateway for asylum, receiving 64 million appointment requests compared to just 501,000 paroles between May 2023 and February 2024 [1]. Despite this volume, it only supported three languages and required facial recognition and geolocation, with undisclosed data sent to Google Firebase [2] [1]. 

Translation is not a "nice-to-have" feature; bad localization blocks access and erodes credibility. CuidadoDeSalud.gov launched two months late with "Spanglish" translations, broken links to English forms, and slow user experiences [3] [4]. Consequently, California saw fewer than 5,500 Spanish enrollments early on, despite having 4.3 million Spanish-only speakers [4]. Furthermore, machine translation for legal pathways creates harmful misguidance. U.S. immigration processes increasingly rely on AI translation, but translators report errors that jeopardize asylum applications [5]. 

Surveillance spillover destroys trust, even when technically "lawful." ICE has scanned DMV driver's license photos using facial recognition without residents' consent, accessing data on three in four adults and scanning one in three [6] [7]. Finally, "build it for them, not with them" approaches lead to abandonment. Of 169 "refugee tech" projects launched around 2015, the majority went inactive, including well-funded service mapping platforms like clarat and volunteer-run ones like metacollect, which were discontinued due to low use and shifting services [8].

## Why This Report Matters: Preventable Design Choices Repeatedly Undermine Immigrant-Serving Tools

Trust, privacy, and adoption failures in civic tech are patterned, not random. When building tools for immigrant and refugee communities, the stakes are exceptionally high. A poorly translated button or an opaque data-sharing agreement can result in deportation, loss of healthcare, or prolonged exposure to violence. By examining documented failures, organizations can engineer against these pitfalls early in the design process.

## Documented Failure Cases: What Broke, Why It Mattered, How to Prevent It

### CBP One as Digital Gatekeeper: Biometrics, Limited Languages, and Opaque Data Flows

The CBP One app demonstrates how effectively mandatory use, combined with biometrics and language gaps, creates exclusion and fear. Between May 2023 and February 2024, asylum seekers made 64 million requests for appointments, while only 501,000 were paroled [1]. The app requires facial recognition and GPS tracking, and device information is sent to Google's Firebase service without user disclosure [2]. The app is only available in English, Spanish, and Haitian Creole, excluding arriving asylum seekers who speak Indigenous languages, Arabic, French, or Russian [1]. Black and Brown asylum seekers reported trouble getting the facial recognition selfie to work due to darker skin tones [1] [9]. This prolonged exposure to harm in Mexico and contributed to irregular crossings [2] [1]. To prevent this, agencies must provide parallel non-digital channels, minimize biometrics, and publish independent privacy impact assessments [1] [9].

### CuidadoDeSalud.gov Spanish Site: Poor Translation and UX Broke Enrollment

Bad localization tangibly suppressed uptake and trust in a critical public benefit. CuidadoDeSalud.gov launched more than two months late and was riddled with grammatical mistakes and "Spanglish" [3] [4]. Links comparing insurance plans mistakenly took users to English versions [4]. The website translated "premium" into "prima," which commonly means female cousin [3] [4]. In New Mexico, where over 20 percent of the population lacked health insurance, fewer than 1,000 people signed up for coverage in October and November 2013 [4]. Prevention requires native-speaker quality assurance, glossary management, and performance parity with English sites.

### Machine Translation in Asylum Processes: Harmful Guidance Risks

Machine translation errors in legal contexts lead to misfilings and adverse outcomes. Translators report that the U.S. immigration system relies on AI-powered translations without grasping the limits of the tools, jeopardizing asylum applications [5]. Prevention requires human-in-the-loop reviews for rights-affecting content and direct referrals to accredited legal services.

### Refugee Service Mapping Platforms: Abandoned Due to Low Use and Scope Drift

Without co-design, maintenance plans, and integration into provider workflows, tools die on the vine. During the 2015 refugee arrivals in Europe, several digital social innovation projects tried to map NGO services [8]. The volunteer-run team at metacollect soldiered on for over two years before discontinuing in March 2018 due to a lack of resources [8]. Similarly, the well-funded initiative clarat concluded that mapping such a dynamic sector was an elusive goal, and their imagined use-case did not hold up in practice because few people were using it [8]. Prevention requires co-ownership with service providers, sustained funding, and strict usage KPIs.

### DMV Driver's License Data Access by ICE: Lawful Data Repurposing Shattered Trust

Secondary law-enforcement access to social-service data fuels a chilling effect. ICE agents have mined millions of driver's license photos for possible facial recognition matches, targeting undocumented immigrants who legally obtained driver's licenses in states like Washington, Utah, and Vermont [10]. ICE has scanned the driver's license photos of 1 in 3 adults and has access to the data of 3 in 4 adults [7]. This occurred without state residents' awareness or approval [10]. Prevention requires legal firewalls prohibiting secondary access, transparency reports, and community data oversight.

#### Table: Failure Cases Summary

| Tool/Program | Failure Mode | Evidence | Community Impact | Status | Preventable Design/Process Change |
| :--- | :--- | :--- | :--- | :--- | :--- |
| CBP One App | Mandatory use, biometrics, language exclusion | 64M requests vs 501k paroles; 3 languages; FRT bias [1] | Prolonged danger in Mexico; discriminatory exclusion [2] [1] | Verified | Parallel non-digital channels; minimize biometrics; independent PIA |
| CuidadoDeSalud.gov | Poor translation, broken UX | "Spanglish"; <5,500 CA enrollments early on [4] | Low enrollment among vulnerable Spanish speakers [4] | Verified | Native-speaker QA; performance parity with English site |
| AI Translation in Asylum | Machine translation errors | Translators report jeopardized applications [5] | Legal misfilings; denied asylum claims [5] | Verified | Human-in-the-loop for legal content; ban MT-only outputs |
| metacollect / clarat | Abandonment, low adoption | Discontinued after 2 years; low actual usage [8] | Loss of resources; wasted funding [8] | Verified | Co-design with providers; multi-year funding commitments |
| DMV Databases (ICE) | Law enforcement data repurposing | Scans of 1 in 3 adults; access to 3 in 4 [7] | Betrayal of trust; targeting of undocumented drivers [10] | Verified | Legal firewalls; ban on secondary law enforcement access |

*Key Takeaway: Every documented failure stems from a preventable design or process gap, ranging from inadequate localization to unchecked data sharing with law enforcement.*

## Pattern Synthesis: Seven Recurring Failure Modes Across Cases

Failures in immigrant-serving tech cluster around identity bias, data governance gaps, coercive design, and sustainability. 

### Pattern 1: Coercive Access (Mandatory or De Facto Mandatory)
When tools are the only way to access a right (like asylum via CBP One), technical glitches and device requirements become human rights violations [2] [1].

### Pattern 2: Language and Literacy Mismatch
Deploying tools in limited languages or using poor machine translation (CuidadoDeSalud.gov) immediately alienates the target user base and destroys institutional credibility [3] [4].

### Pattern 3: Harmful Automation Without Safeguards
Using facial recognition that fails on darker skin tones (CBP One) or AI translation for legal documents introduces systemic bias and life-altering errors [1] [5] [9].

### Pattern 4: Data Repurposing to Law Enforcement
When civic data (DMV photos) is accessed by immigration enforcement (ICE), it creates a massive chilling effect, discouraging immigrants from utilizing public services [10] [6].

### Pattern 5: No Co-Design and Weak Stewardship
Building tools without community input (refugee mapping apps) leads to products that solve the wrong problems and are quickly abandoned when volunteer energy fades [8].

### Pattern 6: Misleading Eligibility/Guidance UX
When tools act as eligibility checkers but provide poorly translated or inaccurate guidance, they expose users to severe legal and health risks [5] [4].

### Pattern 7: Opaque Allocation and Decision Logic
Randomized or opaque systems (CBP One appointment lottery) feel arbitrary, leaving users in limbo for months and forcing them into dangerous alternatives [2] [1].

#### Table: Pattern-to-Case Mapping

| Pattern | Affected Cases | Evidence | Primary Risk | Business/Operational Implication |
| :--- | :--- | :--- | :--- | :--- |
| Coercive Access | CBP One | Turn-backs at border without app [1] | Human rights violations | Must build parallel analog pathways |
| Language Mismatch | CuidadoDeSalud.gov, CBP One | "Prima" for premium; only 3 languages [1] [4] | Complete adoption failure | Budget for human translation and QA |
| Harmful Automation | CBP One, AI Asylum Translation | FRT fails on dark skin; AI translation errors [1] [5] | Discriminatory exclusion | Require bias testing and human review |
| Data Repurposing | DMV/ICE Facial Recognition | ICE scans 1 in 3 adults [7] | Chilling effect on civic participation | Implement strict data firewalls |
| Weak Stewardship | metacollect, clarat | Discontinued after 2 years [8] | Abandoned communities | Require 24-month funding pre-launch |

*Key Takeaway: These patterns highlight that technical functionality is secondary to trust, equity, and sustained community alignment.*

## Guardrails That Prevent Repeat Failures: Design, Policy, and Ops Controls

Specific, testable guardrails can be embedded before launch and audited post-launch to prevent these failure modes.

### Data Governance Guardrails
Implement strict data minimization and purpose limitation. Prohibit law enforcement access clauses, conduct vendor Data Privacy Impact Assessments (DPIAs), and ensure telemetry is encrypted and off-by-default.

### Access & Equity Guardrails
Design for the edge by supporting low-end Android devices, offline/SMS workflows, and accessible kiosks. Conduct identity bias testing with Black and Indigenous users before scaling [1] [9].

### Language & Comprehension Guardrails
Require community-reviewed translations and term glossaries. Ban machine-translation-only workflows for high-stakes legal or health content [5] [4].

### Automation & Biometrics Guardrails
Mandate risk assessments and bias audits for facial recognition and machine translation. Provide clear opt-outs and strict vendor constraints [9].

### Sustainability & Exit Guardrails
Require 24 months of operations and maintenance funding before launch. Establish clear ownership handoffs, open APIs, and public deprecation plans [8].

### Transparency & Fairness Guardrails
Publish allocation rules and capacity dashboards. Provide independent complaint channels and appeals processes for automated decisions [1].

#### Table: Guardrails by Pattern with Implementation Checkpoints

| Pattern | Guardrails | Pre-Launch Tests | Run-Time Monitors | Owner |
| :--- | :--- | :--- | :--- | :--- |
| Coercive Access | Parallel non-digital channels | Audit analog pathway capacity | Analog vs. digital wait times | Product/Ops |
| Language Mismatch | Community-reviewed translation | Comprehension testing | Drop-off rates by language | Localization |
| Harmful Automation | Bias audits, human-in-the-loop | FRT skin-tone testing | Error rates by demographic | Engineering |
| Data Repurposing | Legal firewalls, no LEA access | DPIA and vendor review | Data access request logs | Legal/Privacy |
| Weak Stewardship | 24-month funding, exit plan | Budget allocation check | Active user metrics | Exec Sponsor |

*Key Takeaway: Guardrails must be operationalized into specific pre-launch tests and run-time monitors to be effective.*

## What a Hackathon Team Must Prove Before Shipping: A Pre-Mortem Checklist

If a team cannot answer these questions with evidence, they should not launch the tool.

### Questions to Avoid Trust, Privacy, and Adoption Failures
* **Access:** What is the non-digital path with an equal service level?
* **Data:** What data is strictly necessary? Who can never access it (legally and technically)?
* **Vendors:** Where does data flow (e.g., SDKs like Firebase)? Is this disclosed and consented? [2]
* **Language:** Have two native speakers and community reviewers validated all critical copy?
* **Bias:** Did testing include Black/Indigenous users, older adults, and low-end devices? What were the results? [1]
* **Automation:** What content is MT-only? For which flows is MT strictly prohibited?
* **Allocation:** Are rules transparent and appealable? How do users verify fairness?
* **Sustainability:** Who maintains this for 24 months? What is the funded budget and exit plan? [8]
* **Legal:** Which MOUs/DPAs/PIAs are signed, published, and independently reviewed?
* **Community:** Which organizations co-own governance? Do they have veto power on data use changes?

## Measurement and Early Warning: Detect Exclusion and Distrust Fast

Monitor equity, comprehension, and data access incidents in real time to catch failures before they cause widespread harm.

#### Table: Metrics, Targets, and Triggers

| Metric | Target/Threshold | Data Source | Owner | Escalation Action |
| :--- | :--- | :--- | :--- | :--- |
| Equity of Access | <5% variance by device/language | App analytics | Product | Halt rollout; optimize for low-end devices |
| FRT Failure Disparities | <1% variance by skin tone | Bias audit logs | Engineering | Disable FRT; default to manual review |
| LEA Data Requests | Zero unauthorized requests | Legal logs | Privacy | Block access; notify community board |
| Complaint Rates | <1% of total users | Support tickets | Ops | Trigger UX review and community consultation |

*Key Takeaway: Early warning systems must be tied to immediate escalation actions, such as halting rollouts or disabling biased features.*

## Implementation Roadmap: Sequencing Guardrails into Delivery

Bake privacy, equity, and sustainability into sprints, rather than treating them as afterthoughts.

### Phases
1. **Discovery:** Co-design with community conveners and service providers.
2. **Privacy/Equity by Design Sprint:** Map data flows and establish legal firewalls.
3. **Red-Team Simulation:** Test with legal aid and community testers to find edge cases.
4. **Limited Pilot:** Launch with a parity non-digital channel.
5. **Independent Audit:** Conduct bias and privacy audits before scaling.
6. **Staged Scale-Up:** Monitor telemetry and complaint channels continuously.

## Appendices: Source Citations and Audit Artifacts

### Sources Cited
Evidence is drawn from Amnesty International (2024) [2], Human Rights Watch (2024) [1], EPIC comments (2024) [9], NBC News (2014) [4], The Nation (2014) [3], The Guardian (2023) [5], Georgetown Law "American Dragnet" (2022) [6] [7], NPR (2019) [10], and DSI4EU (2018) [8].

### Templates
Teams should utilize standardized templates for Privacy Impact Assessments (PIAs), vendor data flow maps, community translation rubrics, bias test protocols, sustainability charters, and deprecation/exit plans to reduce risk and speed approvals.

## References

1. *“We Couldn’t Wait”: Digital Metering at the US-Mexico Border | HRW*. https://www.hrw.org/report/2024/05/01/we-couldnt-wait/digital-metering-us-mexico-border
2. *CBP One Mobile Application Violates the Rights of People Seeking Asylum in the United States - Amnesty International*. https://www.amnesty.org/en/latest/news/2024/05/cbp-one-mobile-application-violates-the-rights-of-people-seeking-asylum-in-the-united-states/
3. *The Spanish-Language Version of Healthcare.gov Is a Mess | The Nation*. https://www.thenation.com/article/archive/spanish-language-version-healthcaregov-mess/
4. *Lost in translation: Spanish version of health insurance website beset by problems*. https://www.nbcnews.com/health/health-news/lost-translation-spanish-version-health-insurance-website-beset-problems-flna2d11909762
5. *Lost in AI translation: growing reliance on language apps jeopardizes some asylum applications | US immigration | The Guardian*. https://www.theguardian.com/us-news/2023/sep/07/asylum-seekers-ai-translation-apps
6. *American Dragnet | Data-Driven Deportation in the 21st Century*. https://americandragnet.org/
7. *American Dragnet | Center on Privacy and Technology | Georgetown Law*. https://www.law.georgetown.edu/privacy-technology-center/publications/american-dragnet-data-driven-deportation-in-the-21st-century/
8. *The Failings of “Refugee Tech”. Written by Ben Mason, betterplace lab… | by DSI4EU | DSI4EU | Medium*. https://medium.com/dsi4eu/the-failings-of-refugee-tech-eeb81cfac430
9. *EPIC-Comments-CBP-OMB-CBP-One-April-2024. ...*. https://epic.org/wp-content/uploads/2024/05/EPIC-Comments-CBP-OMB-CBP-One-April-2024.pdf
10. *ICE Uses Facial Recognition To Sift State Driver's License Records, Researchers Say | KUT Radio, Austin's NPR Station*. https://www.kut.org/2019-07-08/ice-uses-facial-recognition-to-sift-state-drivers-license-records-researchers-say