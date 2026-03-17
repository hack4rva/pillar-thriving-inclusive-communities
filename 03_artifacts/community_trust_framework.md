# Community Trust Framework - Thriving and Inclusive Communities

## Purpose
This framework guides teams building tools for immigrant and refugee communities in Richmond. Trust is not a feature to be added to a working prototype — it is the foundation that determines whether any tool will be used at all.

A tool that collects no personal data but fails to communicate its privacy approach will be avoided by the very residents it was designed to help. A tool that technically complies with privacy law but is organized in a way that feels institutional or government-like may trigger fear rather than assistance.

This framework is the defining constraint for Pillar 5. Every design decision should be filtered through it.

---

## Principle 1: Privacy by Default, Not by Configuration

**What this means**: The default state of the tool must be the most privacy-protective state. Users should not need to find a settings page or opt out of data collection.

**In practice**:
- No login required to access any service information
- No cookies that persist personal browsing history
- No collection of name, address, phone number, or email from residents
- No collection of immigration status, household composition, or income
- Search queries are not logged or tied to any identifier
- If any analytics are collected (e.g., aggregate page views), this must be disclosed

**Why this matters**: Undocumented residents and others with precarious status have well-founded reasons to fear digital surveillance. If a tool collects anything that could be subpoenaed or accessed by law enforcement, it represents a real risk. The standard is not "we wouldn't do that" — it is "the tool is designed so that it cannot do that."

---

## Principle 2: Transparent Disclosure at the Front Door

**What this means**: Before a resident interacts with the tool at all, they should clearly understand what information the tool does and does not collect.

**In practice**:
- Landing page includes a clear, plain-language privacy statement
- Statement is available in at least Spanish, the most common non-English language for Richmond's immigrant population
- Statement does not require reading fine print or navigating to a separate policy page
- Language example: "This tool does not ask for your name, address, or immigration papers. We do not store any information about who you are or what you searched."

**Why this matters**: The working session finding is explicit: trust is the primary barrier, not lack of information. Residents who are not sure if the tool is safe will default to not using it. The privacy statement is not a legal formality — it is a welcome mat.

---

## Principle 3: Work Through Trusted Intermediaries

**What this means**: For many immigrant and refugee residents, technology is not the first or most trusted channel. Information about services is obtained through people: neighbors, church members, teachers, community navigators, and case managers. Digital tools work best when they support these human relationships, not try to replace them.

**In practice**:
- Design tools so community ambassadors can share service information through WhatsApp, SMS, or social media without needing the resident to interact with the tool directly
- Allow case managers to use the tool on behalf of clients without exposing client data to the tool
- Build content that is shareable as a message or image, not just a link that requires a specific browser or device
- Test the tool with at least one community organization before demo, even informally

**Why this matters**: The rubric working session explicitly identified this: "Technology should support — not replace — human relationships." Tools that bypass trusted community relationships often fail to reach the residents with the highest need.

---

## Principle 4: Cultural and Language Adaptation, Not Translation

**What this means**: Translating English text into Spanish (or Arabic, or Nepali) using machine translation is not sufficient and can be actively harmful. Language access requires understanding cultural context, not just converting words.

**In practice**:
- Use human translators or community reviewers for any translated content in the final tool
- Label machine-translated content clearly as "machine translation — not reviewed" if human review is not possible by demo
- Avoid idiomatic expressions, legal language, and agency acronyms in any language
- Images and icons can reduce language burden — use them for category navigation
- Voice/audio playback of text helps residents with limited literacy in any language

**What to avoid**:
- Running service descriptions through Google Translate without review
- Assuming that Spanish translation covers all immigrant populations (Arabic, Nepali, Burmese are also significant in Richmond)
- Using language that assumes familiarity with US systems (e.g., "SNAP", "HUD", "TANF" without explanation)

---

## Principle 5: Never Imply Eligibility Determination

**What this means**: The tool should never tell a resident that they qualify for a program or that they do not qualify. Eligibility decisions involve complex, changing rules and are the responsibility of trained case workers, not a weekend prototype.

**In practice**:
- Use language like "this organization helps people who need [X]" rather than "you qualify for this program"
- Always direct residents to contact the organization directly for eligibility questions
- Never collect household income, family size, immigration status, or other eligibility variables — these are not needed for a service directory
- Add a clear disclaimer to any tool that surfaces service information: "Always contact the organization directly to confirm eligibility and availability."

**Why this matters**: An incorrect eligibility implication — even if unintentional — can send a vulnerable resident to the wrong organization, cause them to miss a deadline, or create a false sense of security. The harm from incorrect guidance is asymmetric: it falls most heavily on the people with the fewest alternatives.

---

## Principle 6: Fail Gracefully, Fail Honestly

**What this means**: A service tool that returns no results, shows outdated phone numbers, or leads to a dead end is not a neutral failure — it is a harm. It depletes the resident's limited trust and energy.

**In practice**:
- "No results" should never be a dead end — always provide a fallback (e.g., "Call 211" or "Contact a community navigator")
- Phone numbers and addresses in the directory must be verified before demo
- If data is outdated or unverified, label it clearly
- The tool should always provide a way to reach a human, not just a website

**Why this matters**: For a resident in crisis, a failed tool interaction may mean giving up on seeking help entirely. The cost of failure is not just a bad user experience — it is a missed connection to a potentially life-changing resource.

---

## Applying the Framework in Your Build

Before finalizing your MVP scope, answer these questions:

1. **What data does the tool collect from users?** List every field, cookie, and log entry.
2. **Is there a clear privacy statement on the landing page, in plain language?**
3. **Can a resident browse the tool without providing any identifying information?**
4. **Does the tool translate or adapt for non-English speakers, or is it English-only?**
5. **Does the tool imply eligibility determination anywhere?**
6. **Does the tool support the work of trusted intermediaries, or try to replace them?**
7. **What happens if the tool fails or shows no results?**
8. **Has any community member, case manager, or community organization reviewed the tool or its content?**

If you cannot answer all of these affirmatively before demo, flag the gaps explicitly. Judges will respect transparency about limitations more than overclaiming.
