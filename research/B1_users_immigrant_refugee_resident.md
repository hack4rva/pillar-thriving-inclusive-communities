# Meet B1: The WhatsApp-first Newcomer Navigating 90-Day Windows and 180-Day Clocks

## Executive Summary

The primary user of a service discovery tool in the Thriving and Inclusive Communities pillar—Persona B1—is navigating a highly compressed, status-dependent integration timeline with limited English proficiency and high bureaucratic friction. Their legal status dictates their service map: formally resettled refugees face shrinking federal aid windows (reduced to four months for new arrivals), while asylum seekers must survive a 180-day waiting period for work authorization. 

Digital engagement for B1 does not happen through traditional web browsing. It occurs primarily on WhatsApp and is mediated by trusted community nodes ("information grounds") such as faith centers, local charities, and caseworkers. Furthermore, language and administrative barriers are severe: complex forms and English-only notices lead to massive drop-off rates, with limited English proficient (LEP) individuals facing up to a 5x higher risk of benefit disenrollment. To succeed, a service discovery tool must abandon text-heavy, web-first assumptions. Instead, it must offer status-aware triage, WhatsApp integration, multilingual audio/visual interfaces, and seamless pathways to human interpreters and caseworkers.

## Why B1 Matters Now — Early decisions lock in 12–36-month outcomes

The first year of arrival is decisive for long-term integration, but the windows for assistance are narrow and unforgiving. Formally resettled refugees receive initial Reception and Placement (R&P) services that typically last only 90 days [1]. Furthermore, recent policy shifts have compressed the timeline for federal financial survival: individuals with an eligibility date on or after May 5, 2025, are now only eligible for four months of Refugee Cash Assistance (RCA) and Refugee Medical Assistance (RMA) [2] [3]. 

Conversely, asylum seekers face a mandatory waiting period, generally becoming eligible to receive an Employment Authorization Document (EAD) only after their application has been pending for 180 days [4] [5]. Because early English proficiency is remarkably low, newcomers are forced to navigate these strict countdowns while unable to comprehend complex systemic requirements. Missing a deadline or a biometric appointment stops the clock entirely [4]. Therefore, early, accurate, and status-specific service routing is critical to preventing long-term poverty and undocumented status.

## Arrival Contexts and Eligibility Matrix — Route by legal status, not just need

Different entry pathways confer distinct benefits, documentation, and provider relationships. Misrouting a user wastes their scarce eligibility windows and damages trust. A service discovery tool must ask for status and arrival date upfront to filter out dead-ends.

| Legal Status | Documentation & Timeline | Eligible Benefits | Primary Providers | Risks & Vulnerabilities |
| :--- | :--- | :--- | :--- | :--- |
| **Refugee / Asylee / SIV / Cuban-Haitian Entrant** | I-94, EAD codes; 90-day R&P window [2] [1] | RCA/RMA (4 months post-May 2025), Matching Grant (120-240 days), Refugee Support Services (up to 5 years) [2] [3] [6] | Resettlement Agencies, ORR-funded CBOs [2] | Shrinking cash/medical aid windows require immediate employment linkage [3]. |
| **Asylum Seeker** | Pending I-589; 150-day file / 180-day EAD clock [4] [5] | Ineligible for ORR cash/medical until asylum is granted; rely on state/local safety nets. | Pro-bono legal, local charities, faith groups [7] | Clock stops if biometrics or interviews are missed; high risk of exploitation during 180-day wait [4]. |
| **Undocumented / Non-Qualified** | Lack of formal status; no EAD. | Emergency medical, immunizations, state-specific expansions (e.g., CA SB 75) [8]. | FQHCs, County hospitals, undesignated community grounds [8] | Fear of deportation; FQHCs face pressure to verify status for federal funds, creating care gaps [8]. |

**Takeaway:** The tool must feature a status-aware triage engine. By asking "What is your current status and arrival date?", the platform can display accurate countdowns (e.g., 90-day R&P, 4-month RCA, 180-day EAD) and hide services for which the user is legally ineligible.

## Technology Access and Digital Practices — WhatsApp-first, low-friction, community-amplified

Service discovery succeeds when it rides on existing digital habits rather than expecting traditional web search literacy. For B1, WhatsApp is the undisputed center of the digital ecosystem. 

The International Rescue Committee (IRC) has successfully modeled this by launching ALMA, an AI-powered virtual assistant available 24/7 via WhatsApp, fluent in Dari/Farsi, English, Spanish, and Swahili [9] [10]. ALMA helps users navigate social services, employment, and documentation directly on their phones [9]. Similarly, the IRC's Signpost project packages online resources into formats that are easy to distribute and navigate on WhatsApp and Facebook, reaching over 1.5 million people [11]. 

| Channel | Typical Comfort Level | Best Use Cases | Risks & Limitations |
| :--- | :--- | :--- | :--- |
| **WhatsApp** | Very High | Primary entry point, conversational triage, document sharing, peer-to-peer forwarding [9] [11]. | Requires data/Wi-Fi; AI chatbots cannot provide legal advice [9]. |
| **Web Browsing** | Low to Medium | Deep research by caseworkers or highly educated immigrants. | High abandonment due to language barriers and complex navigation [12]. |
| **Phone Calls** | Medium (High Anxiety) | Urgent needs, interpreter-assisted warm handoffs [13]. | IVR trees without language routing cause hang-ups; interpreter delays [12] [13]. |
| **In-Person (CBOs/Faith)** | High | Building trust, complex form completion, emotional support [7]. | Limited by transportation, operating hours, and childcare [14]. |

**Takeaway:** The product must offer a WhatsApp conversational entry point, shareable QR codes for community boards, and one-tap handoffs to human help.

## Language Trajectory and Literacy — Design for audio/visual at 0–12 months; simple text at 12–36

English proficiency among recent arrivals starts very low and improves slowly, meaning text-heavy interfaces will fail in the first year. According to the 2021 Annual Survey of Refugees, 49 percent of refugees indicated they did not speak English when they arrived in the U.S., and 19 percent still did not speak English at the time of the survey [14]. While 68 percent participated in English language classes [14], only 40 to 52 percent of refugees rated their English proficiency as "well" or "very well" at the time of the survey across recent years (2016-2023) [15].

Furthermore, native-language literacy impacts digital tool use. Translated materials often fail because they are written at inaccessible reading levels; for example, one study found that Medicaid applications translated into Spanish had reading levels equivalent to "at least fifteen years of schooling" [12]. 

**Takeaway:** Default to a multilingual, low-literacy UX. Use voice notes, audio prompts, and clear iconography for users in their first 0-12 months. Keep translated microcopy at a plain-language reading level and avoid text-heavy pages.

## Trust and Risk Perception — Lead with safety, privacy, and community signals

Trust is relational and place-based. "Official" or government-branded platforms can trigger fear, especially for undocumented migrants or asylum seekers who fear deportation or public charge repercussions. Recent federal restrictions and reinterpretations regarding Federally Qualified Health Centers (FQHCs) have heightened these fears, as clinics are encouraged to verify immigration status before delivering non-exempt services [8]. This creates a chilling effect where undocumented immigrants may avoid seeking care due to fear of immigration consequences [8].

**Takeaway:** Co-brand the tool with known local CBOs and faith organizations. Offer anonymous browsing, make data-use promises explicit, and avoid government-looking UI elements to mitigate fear and increase help-seeking behavior.

## Information-Seeking Paths — Caseworkers and community spaces beat cold outreach

Newcomers do not typically find services through isolated web searches; they rely on "information grounds"—environments where people gather and spontaneously share information [7]. 

Research divides these into two categories:
* **Designated information grounds:** Refugee-specific places created by host societies, such as resettlement agencies, the Red Cross, and refugee councils. These are integral for navigating the formal integration system [7].
* **Undesignated information grounds:** Non-refugee-specific places like mosques, churches, community centers, and playgrounds. Religious centers are particularly critical, providing practical support, emotional support, and information to families [7].

**Takeaway:** Seed the discovery tool in these physical spaces. Geo-index community venues, provide printable share cards for mosques and churches, and integrate onboarding into ESL classes.

## Barriers Beyond Discovery — Remove friction at contact, completion, and childcare

Finding a service is only the first step; executing the connection is where most failures occur. Bureaucracy, language, and family constraints are massive blockers.

| Barrier | Evidence & Impact | Design Response |
| :--- | :--- | :--- |
| **Forms & Bureaucracy** | LEP Medicaid enrollees in Illinois were over five times more likely to be disenrolled. 99% received English notices, 85% needed help reading them, and 94% needed help completing them [12]. | Provide status-specific document checklists, auto-generate forms, and offer live completion assistance. |
| **Phone Anxiety & IVR** | Telephonic interpretation is vital, but nuances are lost, and finding interpreters for less common languages causes long wait times [12] [13]. | Embed "call me in my language" defaults; bypass English IVR trees; provide 3-way warm calls with interpreters. |
| **Childcare Constraints** | Only 50% of refugee women participate in the labor force (vs. 76% of men), with women most citing childcare as the reason [14]. | Filter services by onsite childcare availability; surface remote/WhatsApp-based services for caregivers. |
| **Documentation Rules** | Asylum EAD clocks stop if applicants miss biometrics or fail to provide competent interpreters at interviews [4]. | Send proactive deadline alerts and progress tracking for time-sensitive steps (biometrics, SSN). |

## Definition of Success — Warm handoffs within 48 hours in the user’s language

From B1's perspective, a successful service connection is not a list of search results or a link to a website. Success is a completed intake, a scheduled appointment, or a warm handoff to a human being who speaks their language. 

The Signpost model proves that pairing digital content with moderators from affected communities drives actual resolution [11]. Similarly, designated information grounds succeed because they pair information with human caseworkers [7]. 

**Takeaway:** Define success metrics around connection quality. Implement Service Level Agreements (SLAs) for 1-2 business-day callbacks in the user's language. Add "request help" buttons and post-handoff follow-ups to ensure the loop is closed.

## Design Requirements — From status-aware triage to interpreter-backed calls

To effectively serve Persona B1, the service discovery tool must incorporate the following features:

### Must-Haves
* **Status & Arrival Intake:** An eligibility engine that calculates the 4-month RCA/RMA window [3], the 240-day MG window [2], and the 180-day Asylum EAD clock [4].
* **WhatsApp Integration:** Conversational entry via WhatsApp, supported by shareable QR codes placed in CBOs [9] [10].
* **Multilingual & Low-Literacy UX:** Audio prompts, iconography, and plain-language text (below a 15-year schooling reading level) [12].
* **Interpreter-Backed Calling:** "Call me in my language" scheduling to bypass English-only IVR systems [13].
* **Document Navigator:** Visual checklists and sample images of required proofs (I-94, EAD codes) [2].
* **Caregiver Filters:** Provider filters for onsite childcare, transit access, and weekend/evening hours [14].

### Nice-to-Haves
* Community moderators for peer-to-peer tips.
* Progress trackers for mandatory integration tasks (ESL intake, SSN application, biometrics).

## Edge Cases and Failure Modes — Plan for clock stops and policy volatility

The system must proactively guard against predictable failure modes that derail integration:

* **The Stopped Clock:** If an asylum seeker misses a biometrics appointment or fails to pick up a decision, their 180-day EAD clock stops [4]. The tool must send SMS/WhatsApp deadline alerts.
* **Policy Volatility:** Funding windows change rapidly (e.g., the May 2025 reduction of RCA/RMA to four months) [3], and FQHC eligibility rules for undocumented immigrants are under legal tension [8]. The tool must maintain a live registry of state/local safety-nets (e.g., California's SB 75) to route non-qualified aliens when federal clinics restrict access [8].
* **Interpreter Scarcity:** Lesser-diffusion languages face long wait times on language lines [12]. The tool should provide ETA indicators for interpreter availability.

## Measurement Plan — Prove connection, not clicks

To ensure the tool is actually driving Thriving and Inclusive Communities, analytics must move beyond page views. 

**Key Performance Indicators (KPIs):**
* Assisted contact rate (percentage of users who request a warm handoff).
* Interpreter-assisted completion rate.
* 48-hour callback compliance.
* Successful enrollment/appointment rate (verified via follow-up prompts).
* Renewal save rate (tracking users who successfully renew Medicaid/benefits).

## Source Map and Evidence Gaps — Where to strengthen with local data

The national data provides a strong foundation, but local validation is required for deployment.

* **Strong Evidence:** ORR ASR data on language, labor, and benefits [14] [15]; ORR policy on RCA/RMA windows [2] [3]; USCIS EAD clock rules [4]; MACPAC data on LEP barriers [12]; Information grounds theory [7]; IRC WhatsApp models [9] [11].
* **Gaps to Fill Locally:** Local smartphone data plan constraints; WhatsApp penetration rates by specific origin communities in the target zip codes; local interpreter availability for lesser-diffusion languages; and the specific chilling effects of FQHC policy changes in the local region.
* **Next Steps:** Conduct rapid intercept interviews at local ESL classes and mosques, and survey local safety-net providers regarding their current language line capacities and childcare offerings.

## References

1. *Resettlement Timeline: First 90 Days*. http://worldrelief.org/wp-content/uploads/2021/12/RP-Timeline_0.pdf
2. *Benefits for Refugees | The Administration for Children and Families*. https://acf.gov/orr/fact-sheet/refugee-benefits
3. *Reduction of the Refugee Cash Assistance and Refugee Medical Assistance Eligibility Period | The Administration for Children and Families*. https://acf.gov/orr/policy/dear-colleague-letters/25-13
4. *Applicant-Caused-Delays-in-Adjudications-of-Asylum- ...*. https://www.uscis.gov/sites/default/files/document/notices/Applicant-Caused-Delays-in-Adjudications-of-Asylum-Applications-and-Impact-on-Employment-Authorization.pdf
5. *Asylum | USCIS*. https://www.uscis.gov/humanitarian/refugees-and-asylum/asylum
6. *Refugee Resettlement - Reception and Placement Program by USCRI*. https://refugees.org/refugee-resettlement/
7. *People and places: Bridging the information gaps in refugee integration - Oduntan - 2021 - Journal of the Association for Information Science and Technology - Wiley Online Library*. https://asistdl.onlinelibrary.wiley.com/doi/10.1002/asi.24366
8. *Emergency Alert! HHS Restricts Care for Immigrants—Health Centers Must Act Now | Hinshaw & Culbertson LLP*. https://www.hinshawlaw.com/en/insights/healthcare-alert/health-care-alert-hhs-restricts-care-for-immigrants
9. *IRC Launches “ALMA," A Free Virtual Assistant to Support Newcomers in the U.S. | The IRC*. https://www.rescue.org/press-release/alma
10. *Meet Alma: Your Virtual Assistant | Client Rescue*. https://welcome.rescue.org/us/en/services/alma
11. *How the IRC is using social media to fight the coronavirus | The IRC*. https://www.rescue.org/article/how-irc-using-social-media-fight-coronavirus
12. *Enrollment-and-Access-Barriers-for-People-with-Limited- ...*. https://www.macpac.gov/wp-content/uploads/2024/07/Enrollment-and-Access-Barriers-for-People-with-Limited-English-Proficiency.pdf
13. *
      Federal Register
       :: 
      Guidance to Federal Financial Assistance Recipients Regarding Title VI Prohibition Against National Origin Discrimination Affecting Limited English Proficient Persons
    *. https://www.federalregister.gov/documents/2003/08/08/03-20179/guidance-to-federal-financial-assistance-recipients-regarding-title-vi-prohibition-against-national
14. *2021 Annual Survey of Refugees Key Findings*. https://acf.gov/sites/default/files/documents/orr/2021-ASR-Snapshot-Brief.pdf
15. *Annual Survey of Refugees | The Administration for Children and Families*. https://acf.gov/orr/programs/refugees/annual-survey-refugees