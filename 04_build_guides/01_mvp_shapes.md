# MVP Shapes - Thriving and Inclusive Communities

Five buildable shapes for this pillar. Each shape addresses specific friction points from the user journeys. Choose the one that best matches your team's skills and the problem you want to solve.

Privacy-by-design is a requirement for all shapes. See `03_artifacts/community_trust_framework.md` before starting.

---

## Shape A — Privacy-First Service Finder

### Best for
Teams with frontend and content skills. Strongest alignment with Statement 1.

### Core concept
An anonymous, no-login service directory that opens with a clear privacy statement and allows residents to browse services by plain-language category. No search history, no PII, no account required.

### Inputs
- Help1RVA service data (scraped or manually exported)
- Plain-language service descriptions (team-written or AI-assisted with human review)
- Privacy statement text (team-drafted, reviewed for clarity)

### Demo
User opens tool. Sees: "This tool does not ask for your name or papers." Selects "housing help" from a visual menu. Sees 4 organizations with name, phone, languages served, and a one-sentence description. Taps "call now."

### Tech stack options
- Static HTML/CSS/JS with a local JSON data file (easiest to deploy)
- React with a small JSON API
- No database required for MVP

### Scope boundaries
- IN: service browsing by category, organization detail cards, privacy statement
- OUT: personalization, account creation, eligibility filtering, live data sync

### Privacy checklist
- No login or account required
- No analytics that log individual searches
- No storage of IP addresses or session data
- Privacy statement visible on landing page

---

## Shape B — Multilingual Help Resource Tool

### Best for
Teams with multilingual capacity and frontend skills. Extension of Shape A.

### Core concept
Same service finder concept as Shape A, but with Spanish language support as the primary differentiator. Voice-friendly text rendering. Optional: image-based category navigation to reduce literacy burden.

### Inputs
- Same service data as Shape A
- Human-reviewed Spanish translations of category labels and top service descriptions
- (Optional) Icons or images for visual category navigation

### Demo
User selects "Español" on landing. All navigation and service descriptions appear in Spanish. User selects "vivienda" (housing). Sees organizations with Spanish-speaking staff highlighted.

### Tech stack options
- React with language toggle and JSON-keyed translations (i18n library)
- Static site with language-specific HTML pages

### Scope boundaries
- IN: language toggle (English + Spanish minimum), translated category labels, top 10–15 organizations with Spanish descriptions
- OUT: full translation of all content, Arabic/Burmese/Nepali in MVP (stretch goal), voice interface

### Privacy checklist
Same as Shape A.

---

## Shape C — Trusted Messenger Distribution System

### Best for
Teams with backend skills and an interest in outreach infrastructure. Novel approach.

### Core concept
A system that lets verified community ambassadors receive service updates and share them through WhatsApp or SMS to their community networks. Content originates from organizations; distribution happens through trusted people, not through the tool directly.

### Inputs
- Curated list of 10–15 key services and their current status/availability
- At least one community ambassador willing to participate in demo
- Twilio or WhatsApp Business API sandbox account

### Demo
Ambassador receives a WhatsApp message: "[Organization X] is accepting new clients for rental assistance through [date]. No papers required. Call [phone]." Ambassador forwards to their community group.

### Tech stack options
- Twilio API for SMS/WhatsApp (sandbox works for hackathon demo)
- Simple admin interface (Google Form or basic web form) for updating service content
- No resident-facing app required

### Scope boundaries
- IN: curated service update distribution, ambassador subscription, formatted messages in English + Spanish
- OUT: resident-facing browsing tool, full CMS, multi-organization admin, real-time data sync

### Privacy checklist
- Ambassadors subscribe voluntarily
- Resident phone numbers are not collected by the system
- Message content does not include personal information

---

## Shape D — Case Manager Coordination Helper

### Best for
Teams focused on staff-facing tools. Addresses Statement 2 without requiring cross-agency data.

### Core concept
A staff-facing reference tool (not resident-facing) that aggregates public information about local service providers — language capacity, intake requirements, current contact information, and referral notes templates. No resident data stored.

### Inputs
- Help1RVA service data plus manually researched intake requirements and language capacity fields
- Team-written templates for referral notes
- YMCA, ReEstablish Richmond, NCS public-facing program information

### Demo
Case manager searches "housing + Burmese speaker." Sees 3 organizations. Each shows: intake requirements, languages served, and a copyable referral note template. Case manager copies the note and pastes it into their own system.

### Tech stack options
- Static HTML/JSON (simplest)
- React with filter/search
- No backend required for MVP

### Scope boundaries
- IN: filtered service search by need type and language, intake requirement detail, referral note templates
- OUT: live data sync, resident-facing access, case management workflow, actual case tracking

### Privacy checklist
- Tool does not store any information about the client
- Staff use the tool for their own reference only
- No login required

---

## Shape E — Cross-Agency Service Map

### Best for
Teams with data visualization or design skills. Best as an advocacy and onboarding tool.

### Core concept
A visual map (static or lightly interactive) showing the service ecosystem for a specific resident scenario — for example, "recently arrived refugee seeking housing, workforce support, and English classes." Shows organizations, handoffs, typical timelines, and friction points. No resident data involved.

### Inputs
- Public service descriptions from organization websites and Help1RVA
- Team-constructed pathway based on working session context and publicly available program information
- Timeline estimates from public program descriptions

### Demo
Presenter walks through the visual: "A family arrives. They start at ReEstablish Richmond. ReEstablish Richmond connects them to the YMCA for workforce. But the YMCA intake requires an ID the family doesn't have yet. Here's where 2 weeks get lost." Shows the gap visually.

### Tech stack options
- Figma or Miro for static visualization (no code required)
- React + D3 or vis.js for interactive version
- Simple SVG with tooltips

### Scope boundaries
- IN: visual pathway, friction point annotations, organization cards with intake notes
- OUT: live data, resident interaction, case tracking, eligibility determination

### Privacy checklist
- No resident data involved at any point
- Pathway is illustrative and must be labeled as such if based on constructed scenarios
