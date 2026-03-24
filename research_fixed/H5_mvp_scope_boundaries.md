# Sunday-Ready MVP: Ruthless Scope Cuts with a Credible Demo

## Executive Summary

For teams facing time pressure ahead of a Sunday demo, success requires ruthless prioritization. The core objective is to deliver a single, stable, mobile-responsive user flow rather than a broad but broken feature set. By strictly adhering to five non-negotiable requirements—including a complete flow from landing to organization contact and exactly 10 verified entries—teams can guarantee a credible presentation. High-risk features like real-time API syncs, user accounts, and analytics must be cut immediately to protect the core build. Instead of building complex backend systems, teams should leverage UI mocks and scripted narrative to demonstrate future vision without jeopardizing the weekend's deliverables. Privacy and safety remain absolute hard stops; no feature compromising user data can be retained, mirroring the privacy-first and accessibility commitments of platforms like Help1RVA [1].

## Objective and Hard Constraints

The primary objective is to deliver a stable, credible demo by Sunday. Success is defined not by the volume of features, but by the flawless execution of a single core flow. 

To achieve this, teams must adhere to five hard constraints:
1. A visible privacy statement on the landing page.
2. At least one complete user flow from landing to organization contact.
3. A fully mobile-responsive layout.
4. Honest labeling of data quality and limitations.
5. Exactly 10 verified organization entries in the service directory.

Everything outside of these constraints must be evaluated for immediate cutting or mocking.

## Decision Framework Under Time Pressure

When evaluating whether to keep, mock, or cut a feature, apply this four-step decision framework. Privacy, safety, and core value are hard stops.

1. **Does cutting this feature affect the core user value proposition?** 
 * *If yes:* It may be non-negotiable. Keep it in scope.
2. **Does cutting this feature affect privacy or safety?** 
 * *If yes:* It is absolutely non-negotiable. Do not cut it.
3. **Can this feature be faked or mocked for the demo?** 
 * *If yes:* Mock the UI and build the actual functionality post-hackathon.
4. **Can this feature be described verbally rather than shown?** 
 * *If yes:* Cut it entirely from the build and add it to the demo script.

## Non-Negotiables as Acceptance Criteria

To ensure the MVP is ready for Sunday, convert the five non-negotiable features into strict pass/fail acceptance criteria.

| Non-Negotiable Feature | Acceptance Test | Owner | Due Date |
| :--- | :--- | :--- | :--- |
| Privacy statement on landing | Visible on first paint without scrolling | Product Lead | Friday 5pm |
| 1 complete user flow | Landing → Category → Org → Contact works flawlessly | UX Engineer | Saturday noon |
| Mobile-responsive layout | Passes testing on at least 3 different device sizes | Front-End Engineer | Saturday 3pm |
| Honest data labeling | "Verified on 2026-03-24" badge + limitations text on each org | Data Steward | Saturday 5pm |
| 10 verified orgs | Exactly 10 records are verified, consistent, and seeded | Content Manager | Friday noon |

*Takeaway: Assign clear ownership and deadlines to these criteria. If a feature does not pass its test by the deadline, the build is at risk.*

## MVP Shapes and Boundaries

Choose one of the following MVP shapes and strictly enforce its boundaries to prevent over-building.

### Directory-First MVP

This shape focuses entirely on a single browse-to-contact flow populated with 10 highly verified entries.

| Capability | Status | Rationale |
| :--- | :--- | :--- |
| Static category list & org cards | In-Scope | Core to the user value proposition. |
| Tel/mailto contact links | In-Scope | Completes the flow without requiring backend messaging. |
| API sync & User Accounts | Out-of-Scope | High risk of schedule blowup; cut immediately. |
| Advanced filters & Analytics | Out-of-Scope | Can be described verbally as future roadmap items. |
| Future language toggle | Mocked | Shows vision without the heavy translation burden. |

*Takeaway: This is the safest and most reliable shape for a weekend sprint. It guarantees a working demo.*

### Capacity-Aware Directory (Mocked Capacity)

This shape builds on the Directory-First model but adds a visual indicator for organizational capacity.

* **In-scope:** All features from the Directory-First MVP.
* **Mocked:** A "Current capacity" status badge on organization cards (labeled explicitly as "Org-reported; prototype only").
* **Out-of-scope:** Any real-time backend inputs or external API syncs to fetch actual capacity data.

### Bilingual Access Lite

This shape demonstrates accessibility without the burden of full translation.

* **In-scope:** English core content, with Spanish translations strictly limited to category labels and the privacy statement. A functional language toggle UI.
* **Mocked:** Additional languages in the toggle dropdown.
* **Out-of-scope:** Full multilingual translation of all organization details and descriptions.

## Priority Grid

Allocate engineering and design effort strictly according to this grid.

| Feature | Priority | Evidence from Scope Rules |
| :--- | :--- | :--- |
| Privacy statement & Mobile layout | Must-Have | Explicitly listed as non-negotiable; safety/privacy hard stop. |
| 10 verified orgs & 1 complete flow | Must-Have | Core user value proposition; non-negotiable. |
| Multilingual beyond Spanish | Demo-Fake | Can be mocked for the demo (show toggle UI). |
| Current capacity status | Demo-Fake | Can be mocked with a placeholder UI. |
| Referral confirmation | Demo-Fake | Can be mocked as a post-hackathon roadmap item. |
| Real-time API sync ([Help1RVA](https://help1rva.org)) | Cut Entirely | High risk; cut if behind. |
| User accounts & Admin interface | Cut Entirely | Can be described verbally; cut from build. |
| Audio/TTS & Analytics dashboard | Cut Entirely | Non-essential for core flow; cut from build. |

*Takeaway: If a feature is not a "Must-Have," zero backend engineering time should be spent on it before Sunday.*

## Build Plan to Sunday

To survive the time pressure, establish predefined kill switches and strict daily milestones.

* **Wednesday:** Finalize the static data model. Seed exactly 10 verified organizations. Ensure the base layout is mobile-responsive.
* **Thursday:** Complete the category browse and organization detail views. Wire up basic `tel:` and `mailto:` links for the contact flow.
* **Friday:** Implement the privacy banner and data quality labels. Add Spanish category labels. **Enforce a strict feature freeze at 5:00 PM.**
* **Saturday:** Conduct device testing. Build out the UI mocks (capacity, language toggle). Finalize the demo script and take backup screenshots. **Pass the demo-viability gate at noon.**
* **Sunday:** Buffer time for dry runs and presentation polish only. No code changes.

## Demo Script and Honest Labeling

Control the narrative during the presentation. Proactively explain mocked features to build trust with the judges.

| Feature | Demo Status | On-Screen Label | Script Line (20 seconds max) |
| :--- | :--- | :--- | :--- |
| Multilingual beyond Spanish | Mock | "Prototype toggle" | "We validated the UX for language switching; full content translation comes post-hackathon." |
| Current capacity | Mock | "Org-reported, prototype only" | "This requires partner participation. We’ve designed the interface to show how it will look once integrated." |
| Referral confirmation | Mock | "Future workflow" | "This UI mockup represents our next major roadmap item after gathering initial pilot feedback." |
| Accounts / Admin / Analytics | Cut | *None* | "We deliberately excluded admin dashboards to ship core value faster; these will follow the pilot phase." |

*Takeaway: Honesty about what is mocked demonstrates maturity and strong product management.*

## Risk Controls and Privacy/Safety Guardrails

Prevent last-minute compliance and technical failures by enforcing these guardrails:

* **No PII Storage:** Do not build forms that collect or store Personally Identifiable Information. Use standard `tel:` and `mailto:` links to hand off contact actions to the user's native device apps.
* **Visible Privacy:** The privacy statement must be visible immediately on the landing page without requiring the user to dig through menus.
* **Offline-First Data:** Rely on a static JSON or CSV file for the 10 organization entries. Do not rely on external network calls during the live demo.

## Success Metrics for Demo Readiness

Before Sunday morning, ensure the project passes these binary checks to greenlight the demo:

1. Does the single core flow work flawlessly on at least 3 different device sizes?
2. Are there exactly 10 verified organizations, complete with data limitation labels?
3. Is the privacy banner immediately visible?
4. Does the page load successfully without external API dependencies?
5. Are all mocked features clearly labeled as prototypes?
6. Is the demo script rehearsed and under 3 minutes?

## Appendix

**Decision Rules Reference:**
* If it affects privacy/safety → **KEEP**
* If it breaks the core flow → **KEEP**
* If it can be shown as a UI shell → **MOCK**
* If it can be explained in 10 seconds → **CUT & SPEAK**

**Sources:**
* Help1RVA Accessibility & Privacy Statement: https://help1rva.org/legal/accessibility [1]

## References

1. *Help1RVA Greater Richmond Resource Directory | Accessibility*. https://help1rva.org/legal/accessibility