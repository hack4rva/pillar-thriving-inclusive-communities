> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Risk Review Checklist - Thriving and Inclusive Communities

Run this checklist before demo. Every "No" is a blocker that needs to be addressed or explicitly acknowledged.

---

## Privacy and Safety

- [ ] The tool does not collect name, address, phone, email, or any identifying information from residents
- [ ] The tool does not collect or infer immigration status
- [ ] No user session data or search history is stored
- [ ] A privacy statement is visible on the landing page (before any interaction)
- [ ] The privacy statement is in at least English and Spanish
- [ ] No analytics tool that logs individual users is active (e.g., no Google Analytics with user IDs)
- [ ] The tool does not require login or account creation
- [ ] No API keys, credentials, or sensitive configuration are committed to the repository

## Data Quality

- [ ] At least 5 phone numbers in the service directory have been verified as active
- [ ] All organization names reflect current names (organizations change names)
- [ ] Service descriptions are accurate as of the hackathon date
- [ ] Language capacity flags (which organizations serve which languages) are based on verification, not assumption
- [ ] Any unverified information is labeled as such in the UI

## Legal and Eligibility

- [ ] The tool does not tell residents they are eligible or ineligible for any program
- [ ] The tool does not make legal claims about immigration or benefits status
- [ ] Any reference to "no papers required" or similar language has been verified with the organization
- [ ] The tool includes a disclaimer: "Contact the organization directly to confirm eligibility and availability"

## Accessibility and Language

- [ ] The tool is usable on a mobile phone
- [ ] The tool works on a slow connection (test by throttling to 3G in browser dev tools)
- [ ] Any translated content has been reviewed by a human speaker, not just machine-translated
- [ ] Machine-translated content is labeled as such if human review was not possible
- [ ] The tool does not use agency acronyms (SNAP, HUD, TANF, DSNAP) without explanation

## Scope and Claims

- [ ] The tool does not claim to be comprehensive or authoritative
- [ ] The tool does not claim to replace case managers or human navigators
- [ ] The tool does not claim to be City-endorsed or City-operated (unless it is)
- [ ] Demo script acknowledges known limitations and data gaps
- [ ] The tool does not make claims about outcomes ("this will connect you to housing")

## Demo Readiness

- [ ] The tool is deployed to a live URL accessible without VPN
- [ ] The tool has been tested on a real mobile device
- [ ] A static screenshot or video backup exists in case the live demo fails
- [ ] Service data file (JSON/CSV) is included in the repository
- [ ] README explains how to run or deploy the tool locally

---

## If you find a blocker

For any "No" that you cannot fix before demo:
1. Document it explicitly in the demo script
2. Explain what you would do to address it with more time
3. Do not hide it — judges respect transparency about known gaps

The worst outcome is to present a tool as ready when it has an unaddressed privacy or safety risk.
