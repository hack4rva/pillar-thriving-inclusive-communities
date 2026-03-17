# Demo Archetypes That Win Trust and Impact for RVA I1

## Executive Summary

To win the "Thriving and Inclusive Communities" (I1) pillar in Richmond, your demo must prove that you understand the city's specific demographic realities, compliance mandates, and the lived friction of navigating social services. 

* **Language access is table stakes for credibility:** In Richmond, 12.8% of residents speak a language other than English at home, and Spanish speakers make up 71.57% of the Limited English Proficient (LEP) population [1]. Leading your demo with a Spanish-first or bilingual flow demonstrates immediate alignment with the city's needs.
* **Accessibility is a compliance mandate:** The 2024 ADA rule requires state and local government web content to meet WCAG 2.1 Level AA standards [2]. Explicitly showing screen-reader labels and keyboard navigation will secure points on the D8 (accessibility) scoring rubric.
* **Trust by design beats features by volume:** Users avoid platforms that demand unnecessary personal data. Findhelp (the engine behind Help1RVA) explicitly allows users to search the website without providing any personal information [3]. Demonstrating a zero-PII (Personally Identifiable Information) pathway builds immense trust.
* **The problem is fragmentation, not just discovery:** Patients and caregivers face significant barriers including restrictive eligibility criteria, waitlists, and poor coordination between primary care and social service agencies [4]. Your demo must show how you resolve these dead ends, not just how you list phone numbers.

## Why These Archetypes Win in RVA’s I1 Pillar

Judges reward lived-impact, access, and trust. In Richmond, language access and ADA-grade accessibility are mandated norms, and trust (zero PII, clear handoffs) is the differentiator. Demos that dramatize fragmentation and then resolve it for a real person will consistently outperform generic service-finders.

### What the City Promises Residents Today

The City of Richmond's Language Access Plan guarantees free interpretation and translation services to residents [5]. The Office of Immigrant and Refugee Engagement (OIRE) provides 24/7 telephonic interpretation in over 240 languages, Video Remote Interpretation (VRI), and translates vital documents into Spanish [1]. Your demo must align with these existing promises, showing how your tool acts as a seamless extension of the city's language access commitments rather than a siloed tech experiment.

### The Real Navigation Pain

The core friction in social care is not a lack of directories—Help1RVA already catalogs over 1,800 local programs [6]. The real pain lies in fragmentation. Individuals navigating complex health and social services are frequently left to locate and access siloed services alone, facing restrictive eligibility criteria, financial constraints, and communication challenges [4]. Directory freshness is a persistent risk, meaning your product must show verification mechanisms and safe fallbacks when data is missing.

## Archetype 1: The Empathy Opener

**Focus:** Make D5 (population and impact) tangible with a specific user journey.

Start with a Spanish-speaking resident’s moment of need. Quantify how your tool reduces steps, time, and uncertainty without requiring PII. Grounding the demo in a specific, real-feeling person's experience makes the impact tangible for the judges.

* **Demo Sequence:**
 * *Cold open:* Introduce a resident's problem in Spanish (e.g., seeking childcare after a job shift change, relying only on a mobile phone).
 * *Friction montage:* Show a Google search in Spanish leading to mismatched results and unanswered calls.
 * *Switch to solution:* Open your tool. Enter a ZIP code and select "Cuidado infantil" in Spanish. Emphasize that no login is required.
 * *Outcome:* Display the top 1–2 vetted programs with clear eligibility hints and a one-tap button to call with an interpreter.
* **What should be on screen:** Real Spanish copy (no browser auto-translate artifacts), keyboard and screen-reader focus states, eligibility callouts (age, hours, required documents), and a "verified" timestamp.
* **Single most compelling moment:** The one-tap "Call with interpreter" button that connects the user to help within 15 seconds, with absolutely zero personal information entered.
* **Likely judge question & answer:**
 * *Question:* "How do you ensure this works for LEP residents beyond Spanish?"
 * *Answer:* "We align directly with OIRE’s existing language services, which offer telephonic and VRI interpretation in over 240 languages [1]. While our UI content is curated for Spanish today, our core flow is 'interpreter-first' for all languages, requiring no PII or login to access."

## Archetype 2: The Side-by-Side Contrast

**Focus:** Show fragmentation versus your clarity.

Juxtapose today’s dead ends with your verified, language-accessible pathway to prove immediate value. This communicates the problem and solution simultaneously without requiring the judge to imagine the problem on their own.

* **Demo Sequence:**
 * *Left panel:* Show the current state—a Google-in-Spanish search, an outdated PDF flyer, and a dead phone number.
 * *Right panel:* Show your prototype displaying a verified program with accurate hours and eligibility criteria.
 * *Resolution:* Show a "wrong door" warning in your tool that provides a safe redirect path to the correct agency.
* **What should be on screen:** "Verified on: MM/DD" badges, a last-answered call log (non-PII), and accurate Spanish copy.
* **Single most compelling moment:** Your right panel surfaces a navigator callback window in Spanish within 2 minutes, while the left panel is still buffering a voicemail system.
* **Likely judge question & answer:**
 * *Question:* "How will you keep this directory data fresh?"
 * *Answer:* "We leverage community co-maintenance. Agencies can use the 'Claim Program' feature on Help1RVA to update their hours and eligibility [6]. We run a monthly verification script to flag stale items and will pilot a data-quality loop with YMCA navigators and OIRE."

## Archetype 3: The Trust Demonstration

**Focus:** Lead with privacy and ADA conformance to score high on D8.

For this pillar specifically, trust is the defining constraint. Open with a plain-language privacy commitment and prove a complete zero-PII flow that is screen-reader friendly.

* **Demo Sequence:**
 * *First slide:* State clearly: "No account, no personal data required to search or call," aligning with Findhelp's policy that users are free to search without providing information [3].
 * *Accessibility proof:* Tab through the primary flow using only a keyboard, exposing `aria-labels` and alt text to prove WCAG 2.1 AA conformance [2].
 * *Consent moment:* If your tool uses SMS, show an explicit PHI (Protected Health Information) risk notice and opt-in, as text messaging is unencrypted and carries interception risks [3].
* **What should be on screen:** Granular cookie controls, a prominent "Skip sign-in" button, and a Spanish privacy summary.
* **Single most compelling moment:** Completing the entire journey—from search, to eligibility glance, to calling with an interpreter—without entering a single personal field.
* **Likely judge question & answer:**
 * *Question:* "Will you ever need to collect PII?"
 * *Answer:* "Only if the user explicitly chooses to save a favorites list or apply for benefits directly, which requires an email and password [3]. All browsing, triage, and calling remains entirely accountless."

## Archetype 4: The Pathway Walk

**Focus:** Be honest about data gaps and safe fallbacks to demonstrate D3=1 sophistication.

For cross-agency navigation tools, walk through the pathway map step by step. Name the missing eligibility fields and show how the tool handles uncertainty safely. Judges respect teams that name hard problems honestly.

* **Demo Sequence:**
 * *Pathway graph:* Show a cross-agency route (e.g., childcare subsidy → employment support → transportation).
 * *Highlight gaps:* Point out nodes with "unknown eligibility."
 * *Fallback:* Show the fallback mechanism (e.g., a warm handoff to a human navigator).
* **What should be on screen:** Clear data confidence badges ("Known," "Assumed," "Unknown"), timestamps, and Spanish tooltips.
* **Single most compelling moment:** A deliberate pause where you state, "Here is the data we don’t have," followed immediately by showing a safe, interpreter-enabled handoff that still resolves the user’s immediate need.
* **Likely judge question & answer:**
 * *Question:* "How will you fill these data gaps over time?"
 * *Answer:* "Through agency co-maintenance via 'Claim Program' and monthly verifications. We log 'unknowns' to prioritize our outreach efforts, and we hope to partner with department liaisons to close these specific gaps."

## Which Archetype Fits Which MVP

Match your storytelling to your product's actual capabilities. Avoid overextending a thin MVP by choosing the wrong narrative frame.

| MVP Shape | Primary Archetype | Secondary Archetype | Key Proof Moment | Red Flag to Avoid |
| :--- | :--- | :--- | :--- | :--- |
| **Multilingual triage assistant** | Trust Demonstration | Empathy Opener | Zero-PII one-tap interpreter call | Asking for an email to proceed |
| **Directory optimizer** | Side-by-Side Contrast | Trust Demonstration | "Verified on" + agency-claimed update | Claiming 100% coverage |
| **Cross-agency pathway mapper** | Pathway Walk | Side-by-Side Contrast | "Known vs. Unknown" with safe fallback | Inventing/fabricating eligibility logic |
| **Navigator co-pilot** | Empathy Opener | Trust Demonstration | Spanish-first co-browse; call transfer | Forcing the navigator to create an account |
| **Kiosk/offline access** | Empathy Opener | Trust Demonstration | Keyboard-only, large-type, interpreter call | Requiring Wi-Fi or an audio-only flow |

*Takeaway:* If your tool is a triage assistant, lean heavily into the Trust Demonstration to prove you aren't harvesting data. If you are building a pathway mapper, the Pathway Walk is essential to prove you understand the complexity of cross-agency eligibility.

## Combine Archetypes Into a Tight 5-Minute Demo

Sequence trust, empathy, contrast, and pathway so judges feel the problem and see a safe, inclusive resolution.

* **0:00–0:30 | Trust Demonstration:** Open strong. "We collect nothing. You can search and call with an interpreter—no login required."
* **0:30–1:45 | Empathy Opener:** Switch to a Spanish UI. Show a resident seeking childcare after a shift change. Show the pain of the current system, then reveal your first helpful screen.
* **1:45–2:45 | Side-by-Side Contrast:** Left screen shows a Google-in-Spanish search hitting a dead number. Right screen shows your verified program with eligibility hints and a queued one-tap interpreter call.
* **2:45–3:45 | Pathway Walk:** Transition to the broader journey. "Here’s what we know, assume, and don’t know across childcare and transport." Show the fallback navigator handoff for unknown data.
* **3:45–4:30 | Accessibility Receipt:** Perform a live keyboard tabbing pass. Check alt text. Show the Spanish privacy summary and cookie controls to prove WCAG 2.1 AA compliance [2].
* **4:30–5:00 | Close and Ask:** "We are ready to pilot with OIRE and YMCA navigators for a monthly data verification loop and a Spanish-first launch."

## Anticipate Judge Questions

Prepare crisp, evidence-backed answers on data freshness, language coverage, ADA conformance, and privacy.

| Archetype | Likely Question | 15-Second Answer | Evidence to Show |
| :--- | :--- | :--- | :--- |
| **Empathy Opener** | Is this replicable? | "We’ll track step/time reductions and LEP usage across pilot sites." | KPI mock with step/time metrics |
| **Side-by-Side** | How do you keep data fresh? | "Agency Claim/Verify + monthly checks; timestamps on every record." | Claim screen; "Verified on" badges |
| **Trust Demo** | When do you collect PII? | "Never to browse/call; only to save/apply with minimum fields + consent." | Privacy panel; accountless flow |
| **Pathway Walk** | What about missing eligibility fields? | "We mark unknowns, offer interpreter fallbacks, and target data outreach." | Pathway labels: Known/Assumed/Unknown |

*Takeaway:* Never answer a question with just a promise. Always point to a specific UI element, badge, or policy screen that proves your answer is already built into the product.

## Risks, Failure Cases, and Mitigations

Don’t lose points on avoidable pitfalls. Acknowledge common failure modes and show your countermeasures.

* **Machine-translate glitches:** Relying solely on browser auto-translate can lead to dangerous inaccuracies. *Mitigation:* Use curated Spanish content and an interpreter-first routing system.
* **Phantom coverage claims:** Claiming you have "all the data" will trigger skepticism. *Mitigation:* Show "Verified on" dates and avoid boasting about percentage coverage.
* **Hidden PII capture:** Forcing a login to view basic information violates trust. *Mitigation:* Ensure a strict zero-PII flow for browsing. If SMS is used, show visible consent and opt-out mechanisms due to PHI risks [3].
* **Inaccessible UI:** Failing to accommodate users with disabilities violates ADA rules [2]. *Mitigation:* Do a live keyboard-only pass during the demo and ensure alt text labels are visible.

## What to Measure to Prove D5/D8

Track only what you can measure accountlessly and report reliably.

| Metric | Collection Method (No PII) | Pilot Target | Cadence |
| :--- | :--- | :--- | :--- |
| **LEP session rate** | Language toggle + locale detection | ≥30% in Spanish | Weekly |
| **Step/time to successful contact** | UI event timestamps | ≤3 steps / ≤6 mins | Weekly |
| **Navigator callback latency** | Event stamps (enqueue to connect) | ≤2 minutes | Weekly |
| **Keyboard navigation pass rate** | Automated + manual audits | ≥95% | Biweekly |
| **Alt text coverage** | Lint + manual spot-check | 100% on demo scope | Biweekly |
| **PII fields per session** | Audit event with field counters | 0 | Weekly |

*Takeaway:* By tracking these metrics, you prove to the judges that you can measure D5 (impact) and D8 (accessibility) without compromising the privacy promises made in your Trust Demonstration.

## References

1. *Fetched web page*. https://rva.gov/sites/default/files/2026-01/City%20of%20Richmond%20Language%20Access%20Plan%202025.pdf
2. *Fact Sheet: New Rule on the Accessibility of Web Content and Mobile Apps Provided by State and Local Governments | ADA.gov*. https://www.ada.gov/resources/2024-03-08-web-rule/
3. *
        Aunt Bertha | Privacy Policy
    *. https://www.findhelp.org/legal/privacy
4. *
            Effectiveness of system navigation programs linking primary care with community-based health and social services: a systematic review - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC10165767/
5. *Language Access | Richmond*. https://www.rva.gov/immigrant-engagement/language-access
6. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/