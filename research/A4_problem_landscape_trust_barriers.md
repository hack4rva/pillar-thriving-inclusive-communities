# Trust, Not Access: How Safety Signals Determine Immigrant Service Use

## Executive Summary
For immigrant and refugee communities, the primary barrier to service access is no longer a lack of information; it is a profound, structurally reinforced lack of safety. In 2025 and early 2026, intensified immigration enforcement and policy shifts created a massive "chilling effect." Surveys reveal that 30% of all immigrants—and up to 74% of likely undocumented immigrants—have limited their participation in activities outside the home, including seeking medical care, due to fears of enforcement [1] [2]. Furthermore, 51% of immigrant adults (and 78% of likely undocumented adults) are concerned that health care providers will share their information with immigration enforcement officials [3]. 

To build tools for these communities, technologists must shift from an "inform and enroll" mindset to a "protect and reassure" framework. This report outlines the documented abandonment triggers, the practices of trusted community organizations, and the immediate design choices a hackathon team can implement to signal safety.

## Problem Landscape — Safety perceptions, not information access, drive service avoidance
The enforcement climate and fears of data-sharing create persistent "chilling effects," making trust the core barrier even where services exist. The KFF/New York Times 2025 Survey of Immigrants found that 41% of immigrants fear they or a family member could be detained or deported, up sharply from 26% in 2023 [2]. This fear directly impacts health and well-being: 40% of immigrant adults overall and 77% of likely undocumented immigrants report experiencing negative health impacts due to immigration-related worries since January 2025 [3]. 

**INFERENCE:** Information campaigns that focus solely on eligibility will fail if they do not first address the user's primary question: "Will using this service get me or my family deported?"

## How People Decide "Is It Safe?" — Risk calculus among undocumented and newly arrived refugees
Safety assessments hinge on enforcement proximity, data exposure risk, messenger identity, and setting. Direct experiences with enforcement (surveillance, policing, deportation) have a negative relationship with health care access, leading to delayed care [4]. Reluctance to access care is heavily driven by concerns about data sharing; 51% of immigrant adults are concerned about health care providers sharing information with Immigration and Customs Enforcement (ICE) or Customs and Border Protection (CBP) [3].

### Table: Safety Cues vs. Behavioral Impact vs. Design Countermeasures

| Safety Cue / Trigger | Observed Behavioral Impact | Design Countermeasure | Source |
| :--- | :--- | :--- | :--- |
| Fear of provider data sharing with ICE | 51% of all immigrants and 78% of undocumented immigrants express concern | Prominent, plain-language "We do not share data with ICE" banners | [3] |
| Direct encounters with enforcement/policing | Delays in seeking timely health care | Anonymous pre-screeners; offsite/community pop-up locations | [4] |
| Requirement of sensitive PII | Avoidance of noncash government benefits (13.6% of immigrant adults in 2020) | Data minimization; optional address/SSN fields | [5] |

*Takeaway:* Users actively scan for data-sharing risks. Mitigating these risks requires explicit, upfront policy declarations and the removal of unnecessary data collection.

## Enforcement Climate -> Behavior Change — Policy shifts and local programs shape access
Restrictive policies expand avoidance beyond those directly affected. The 2019 Trump administration public charge policy changes contributed to disenrollment from Medicaid and CHIP among immigrant families, including citizen children [6]. Even after the Biden administration reversed these changes, fears persisted; in 2023, 8% of immigrant adults still avoided applying for assistance [6]. 

### Table: Policy/Signal vs. Documented Behavioral Effect vs. Affected Population

| Policy / Signal | Documented Behavioral Effect | Affected Population |
| :--- | :--- | :--- |
| 2019 Public Charge Rule | 18% drop in Medicaid/CHIP participation (2016-2019) | Low-income U.S. citizen children with a noncitizen in the household [6] |
| 2025 CMS-ICE Data Sharing Plan | Exacerbated fears of accessing health coverage and care | Noncitizen Medicaid enrollees and mixed-status families [6] [3] |
| 287(g) Agreements | Threatens welcoming communities and increases fear of local authorities | Immigrant communities in participating jurisdictions [4] [7] |

*Takeaway:* Policy signals have a long half-life. Trust recoveries lag behind policy reversals, requiring sustained reassurance campaigns.

## Abandonment Triggers in Service Journeys — What causes people to stop seeking help
Data-sharing language, sensitive PII fields, and language gates are high-friction trust breakers. Digital exclusion and the fear of surveillance deter migrants from seeking care [8]. Furthermore, language access remains a critical barrier; among non-English speakers who skipped or postponed care, 24% cited language access challenges [3].

### Table: Trigger Patterns, Evidence, Risk Level, Design Alternatives, Metrics to Track

| Trigger Pattern | Evidence | Risk Level | Design Alternative | Metrics to Track |
| :--- | :--- | :--- | :--- | :--- |
| Mandatory Address/SSN | Drives benefit avoidance [5] | High | Progressive disclosure; optional fields | Drop-off rate at PII form fields |
| Government-lookalike UI | Associated with surveillance fears [8] | Medium | Neutral branding; community co-branding | Time-on-page; bounce rate |
| English-only interfaces | 24% cite language barriers for delayed care [3] | High | Multilingual interfaces by default | Conversion by language toggle |

*Takeaway:* Every field that asks for identifying information is a potential exit point. Services must justify every piece of data they collect.

## What Trusted Community Orgs Do Differently — Replicable and non-replicable elements
Success comes from proximity, feedback closure, and multilingual moderators. The IRC's "Client Voice and Choice Initiative" in Greece highlighted that "closing the loop"—explaining to clients how their feedback was used—is extremely important for creating trust [9]. Similarly, the Refugee.Info project in Italy utilizes social media moderators who communicate with clients in six languages, fostering happiness and peer-to-peer recommendations [10].

### Table: Practice vs. Replicability

| Trusted Practice | What it Solves | What Tech Can Replicate | What Requires Time/Humans |
| :--- | :--- | :--- | :--- |
| "Closing the Loop" on feedback | Shows respect and builds ongoing trust [9] | Automated changelogs; "You said, we did" UI panels | Genuine policy adjustments based on feedback |
| Multilingual Social Moderators | Overcomes language barriers and institutional mistrust [10] | Multi-language support; WhatsApp integrations | Hiring trusted community members as moderators |
| Trauma-informed care delivery | Addresses stress from enforcement encounters [4] | Empathetic UX copy; clear exit buttons | In-person Community Health Workers (CHWs) |

*Takeaway:* Technology can facilitate feedback and translation, but the actual trust is built by the humans operating the system and closing the loop.

## Communication That Signals Trust — Messengers, channels, and formats that work
Using in-language messaging on familiar channels with community faces is vital. Refugee.Info successfully uses social media platforms to deliver accurate information in languages clients understand, prompting them to recommend the page to others [10]. 

**INFERENCE:** Formatting matters. Plain-language privacy assurances placed *above the fold* and delivered via familiar channels like WhatsApp signal safety far better than dense, legalistic Terms of Service pages.

## Digital Tools: Trust Wins and Cautions — What's actually working
Tools win trust with human backstops and minimal data, but outcomes are mixed where ethics lag. The Hera app successfully bridges gaps for Syrian refugee women by allowing them to carry medical records on their smartphones and sending immunization reminders [8]. However, mental health apps for refugees carry risks; they can harvest and store sensitive trauma data, making firewalls against immigration enforcement imperative [8].

### Table: Digital Tools vs. Trust Choices vs. Impact vs. Risks vs. Replicable Tactics

| Tool / Approach | Trust-Driving Design Choices | Impact / Evidence | Risks | Replicable Tactics |
| :--- | :--- | :--- | :--- | :--- |
| Refugee.Info (Signpost) | Multilingual social media moderators | High user satisfaction and peer recommendation [10] | Misinformation on social platforms | Meet users on platforms they already use |
| Hera App | Portable medical records; emergency info | Bridges care gaps for refugee women [8] | Data privacy if phone is confiscated | Offline-first capabilities; data portability |
| Mental Health Apps | Anonymity; remote access | Mixed evidence on stigma reduction [8] | Data harvesting; surveillance [8] | Strict data firewalls; explicit consent flows |

*Takeaway:* Digital tools must be "safe and beneficial by design and in operation," prioritizing GDPR-compliant privacy-enhancing technologies [8].

## Key Design Principles
1. **Data Minimization:** Never ask for an SSN or exact address unless legally required for the specific transaction.
2. **Explicit Non-Cooperation:** Display clear, legally-backed statements that data will not be shared with ICE/CBP.
3. **Human-in-the-Loop:** Provide easy off-ramps to human navigators or community health workers.
4. **Close the Loop:** Visibly show how user feedback changes the service.
5. **Jurisdiction-Aware Safeguards:** Adapt data collection based on local enforcement climates (e.g., 287(g) counties).

## 48-Hour Hackathon Playbook
**INFERENCE:** In a 48-hour build, prioritize trust signals over complex features.
* **Hour 1-12:** Draft and publish a "No-ICE Data-Sharing" pledge. Have it reviewed by a legal mentor and translated into the top 3 local languages.
* **Hour 12-24:** Build the intake form using strict data minimization. Make all PII fields (name, address) optional. Add a "Why we ask for this" tooltip next to any required field.
* **Hour 24-36:** Integrate a WhatsApp API for support, ensuring the interface clearly states that messages are encrypted and handled by community moderators.
* **Hour 36-48:** Create a "Community Feedback" page that demonstrates the "Close the Loop" principle, showing a mock changelog of how user input improves the tool.

## Beyond Technology
Sustained trust requires policies, people, and time. Technology cannot replace the relational capital of faith communities or immigrant advocacy groups. It requires:
* **Human Relationships:** Hiring and paying Community Health Workers (CHWs) and promotoras to act as bridges [4].
* **Community Endorsement:** Securing MOUs with local providers to establish "safe spaces" and co-branding with trusted cultural organizations.
* **Time:** Trust recovers slower than policy changes. Consistent, repeated reassurance over months and years is necessary to overcome the deep-seated fears documented in 2025 and 2026 [3] [2].

## Measurement & Risk Management
Track leading trust indicators:
* Abandonment rates at PII fields.
* Conversion rates by language toggle.
* Dwell time on privacy FAQs.
Set red lines on privacy: Conduct regular audits to ensure no accidental data leakage to third-party trackers that could be subpoenaed by enforcement agencies.

## Policy Watch & Scenario Planning
Anticipate fear spikes from federal/state moves. The 2025 CMS-ICE data-sharing plan and proposed public charge changes immediately spiked fear and avoidance behaviors [6] [3]. Service providers must pre-bake response playbooks, including rapid reassurance scripts, reinforced privacy banners, and community briefings, to deploy the moment restrictive policies are announced.

## References

1. *KFF/New York Times 2025 Survey of Immigrants: Worries and Experiences Amid Increased Immigration Enforcement | KFF*. https://www.kff.org/racial-equity-and-health-policy/kff-new-york-times-2025-survey-of-immigrants-worries-and-experiences-amid-increased-immigration-enforcement/
2. *Immigrants Report Rising Fear, Negative Economic and Health Impacts, and Changing Political Views During the First Year of President Trump’s Second Term | KFF*. https://www.kff.org/racial-equity-and-health-policy/immigrants-report-rising-fear-negative-economic-and-health-impacts-and-changing-political-views-during-the-first-year-of-president-trumps-second-term/
3. *KFF/New York Times 2025 Survey of Immigrants: Health and Health Care Experiences During the Second Trump Administration | KFF*. https://www.kff.org/immigrant-health/kff-new-york-times-2025-survey-of-immigrants-health-and-health-care-experiences-during-the-second-trump-administration/
4. *
            Beyond “chilling effects”: Latinx and Asian immigrants’ experiences with enforcement and barriers to health care - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC10079615/
5. *immigrant-families-continued-avoiding-the-safety-net- ...*. https://www.urban.org/sites/default/files/publication/103565/immigrant-families-continued-avoiding-the-safety-net-during-the-covid-19-crisis.pdf
6. *Potential “Chilling Effects” of Public Charge and Other Immigration Policies on Medicaid and CHIP Enrollment | KFF*. https://www.kff.org/medicaid/potential-chilling-effects-of-public-charge-and-other-immigration-policies-on-medicaid-and-chip-enrollment/
7. *287(g) Agreements With ICE Threaten Welcoming Communities - American Immigration Council*. https://www.americanimmigrationcouncil.org/blog/287g-agreements-ice-threaten-communities/
8. *Digital solutions for migrant and refugee health: a framework for analysis and action - ScienceDirect*. https://www.sciencedirect.com/science/article/pii/S2666776224003594
9. *Client Voice and Choice Initiative / Ground Truth case study – Greece, Women’s Protection & Empowerment (WPE) and Water, Sanitation & Hygiene (WASH) | The IRC*. https://www.rescue.org/report/client-voice-and-choice-initiative-ground-truth-case-study-greece-womens-protection
10. *The Impact of Signpost: Bridging the Information Gap for People in Crisis | The IRC*. https://www.rescue.org/article/impact-signpost-bridging-information-gap-people-crisis