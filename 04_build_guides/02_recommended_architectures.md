# Recommended Architectures - Thriving and Inclusive Communities

Architecture recommendations for each MVP shape. Optimized for weekend feasibility, privacy-by-design, and deployability by Sunday.

---

## Architecture A — Static Service Directory (Shapes A, B, D)

### When to use
Any team building a browsable service directory, whether resident-facing or staff-facing.

### Stack
```
Data layer:  JSON file (services.json) — manually curated or scraped
Frontend:    React (Vite) or plain HTML/CSS/JS
Deploy:      Netlify, Vercel, or GitHub Pages (free, fast)
No backend required for MVP
```

### Data model (services.json)
```json
{
  "services": [
    {
      "id": "001",
      "name": "Organization Name",
      "name_es": "Nombre de la Organización",
      "categories": ["housing", "food", "legal"],
      "description": "One sentence in plain English.",
      "description_es": "Una oración en español sencillo.",
      "phone": "804-555-0100",
      "address": "123 Main St, Richmond VA",
      "languages": ["en", "es", "ar"],
      "intake_notes": "No ID required. Walk-ins welcome Mon-Fri 9am-4pm.",
      "verified_date": "2026-03-20",
      "no_papers_required": true
    }
  ]
}
```

### Privacy implementation
- Host on a provider that does not log individual user queries
- No cookies beyond session (and session cookies should not persist)
- No analytics unless explicitly aggregate-only (Plausible, not Google Analytics)
- Privacy statement component rendered on every page

### Deploy checklist
- [ ] `netlify.toml` or `vercel.json` present
- [ ] No `.env` file with API keys committed
- [ ] Privacy statement visible on landing
- [ ] Mobile-responsive (many users will be on phones)
- [ ] Test on low-bandwidth connection

---

## Architecture B — WhatsApp/SMS Messenger (Shape C)

### When to use
Teams building the trusted community messenger distribution system.

### Stack
```
Messaging:   Twilio API (SMS) or Twilio WhatsApp Sandbox
Admin UI:    Google Form → Google Sheet → Python script (simplest)
             OR simple Express.js / FastAPI admin endpoint
Deploy:      Render, Railway, or Glitch (free tiers work for demo)
```

### Twilio sandbox setup (hackathon-friendly)
1. Create Twilio account
2. Use the WhatsApp Sandbox (no approval required for demo)
3. Ambassadors join sandbox by sending a code to a Twilio number
4. Script sends formatted service updates via the API

### Content update flow
```
Organizer updates content (Google Form or admin UI)
  → Triggers a script
  → Formats message in English + Spanish
  → Sends to all subscribed ambassador numbers via Twilio
```

### Privacy implementation
- Ambassador phone numbers stored only in Twilio (not in a custom database)
- Resident phone numbers never collected
- Message content contains no personal information about residents
- Unsubscribe instruction included in every message

### Scope limit
The hackathon demo shows one update being sent to one or two demo ambassadors. Do not attempt to build a full CMS or multi-organization workflow in a weekend.

---

## Architecture C — Interactive Visualization (Shape E)

### When to use
Teams building the cross-agency service pathway map.

### Stack (no-code / low-code)
```
Design:      Figma or Miro (presentable by Sunday with no deployment)
Interactive: Flourish.studio (free, shareable link, no code)
             OR React + vis-network or D3 force graph
```

### Recommended approach for hackathon
Use Figma or Miro for the visual. Export as a PDF or shareable link for demo. This is faster and more reliable than building a custom visualization in 48 hours.

If the team has data viz experience, a Flourish network diagram showing organizations as nodes and referral relationships as edges can be built in a few hours.

### Data prep
Build a simple spreadsheet:
```
Source org | Target org | Handoff type | Typical wait time | Notes
```
Convert to JSON or CSV for a code-based viz, or use the spreadsheet directly in Flourish.

### Privacy implementation
No resident data at any point. This is an organization-to-organization map, not a resident journey tracker.

---

## General Recommendations

### Deploy by Saturday evening
Whatever you're building, have a live URL by Saturday evening. Sunday morning should be for polish and rehearsal, not deployment troubleshooting.

### Mobile-first
The primary users of any resident-facing tool will be on a phone, often an older Android with limited data. Test on a real mobile device or use browser developer tools to simulate.

### Plan for demo failure
Have a static screenshot or video recording of the tool working. If the live demo breaks, show the recording.

### Keep data small
For a hackathon, a JSON file with 20–50 carefully curated organizations is more impressive than a poorly-synced database of hundreds. Quality over quantity.

### No real API keys in git
If you're using Twilio, OpenAI, or any other API, use environment variables and a `.env.example` file. Never commit real keys.
