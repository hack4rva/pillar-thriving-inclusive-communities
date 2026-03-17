# Benchmark Scan - National Comparables

Pillar: Thriving and Inclusive Communities
Purpose: Identify what has been built elsewhere that is relevant to Richmond's immigrant and refugee service access problem. Use this to avoid reinventing the wheel, identify patterns that work, and understand why some tools have failed.

Status: Unverified research placeholder. Teams should verify URLs and current status before citing.

---

## Tool 1: NYC Immigrant Services (NYC.gov/immigrants)

**What it is**: New York City's official immigrant services portal. Provides multilingual information on legal services, health care, education, and economic opportunity specifically for immigrant residents.

**What works**:
- Multilingual from the start (20+ languages)
- Organized around immigrant-specific concerns, not general service categories
- Explicit privacy statement and guidance on what information is and isn't required
- Integrated with NYC's broader benefits access infrastructure

**What's different from Richmond**:
- Scale: NYC has hundreds of staff and a dedicated Office of Immigrant Affairs
- Resources: Full-time multilingual content team
- Partner network: Hundreds of legal aid, health, and social service organizations

**Takeaways for Richmond**:
- Organizing by immigrant concern ("I'm looking for legal help") vs. by service category works better for this population
- Privacy statement on the landing page is essential
- Even with limited scope, a "this is safe to use" message should be prominent

---

## Tool 2: RefugeeConnect (Various States)

**What it is**: A category of platforms designed specifically for refugee resettlement — connecting newly arrived refugees to resettlement caseworkers and local resources. Various implementations exist across different resettlement agencies.

**What works**:
- Designed for the specific context of a new arrival who doesn't know the city at all
- Often mobile-first and SMS-compatible
- Caseworker-facing and resident-facing components
- Language support built in from day one

**What's different from Richmond**:
- Usually built and maintained by large national resettlement agencies (IRC, CWS, USCRI) with dedicated tech teams
- Requires formal resettlement program enrollment — not accessible to undocumented residents

**Takeaways for Richmond**:
- The caseworker-facing component (Concept 4 in this repo) is the most replicable element
- SMS/voice interfaces are critical for newly arrived residents
- The enrollment requirement is a design anti-pattern for privacy-sensitive populations outside formal resettlement

---

## Tool 3: Aunt Bertha / FindHelp (findhelp.org)

**What it is**: A national social care network that connects residents to local programs and services. Used by hospitals, community organizations, and government agencies across the country including in Richmond.

**What works**:
- Large coverage — thousands of programs nationwide
- API available for organizations to integrate service search into their own tools
- Used by social workers, care coordinators, and community health workers as a lookup tool
- Organization profiles include eligibility requirements and intake instructions

**What's different from Richmond**:
- Richmond coverage exists but is not comprehensive
- Not interoperable with Help1RVA — different data standards
- Language support is inconsistent
- Not designed with privacy-sensitive populations as the primary user

**Takeaways for Richmond**:
- The model of an embeddable service search API is worth exploring — could power a Richmond-specific front end
- Organization-level intake information (what you need to bring, what questions they ask) is valuable and missing from Help1RVA
- Interoperability with Help1RVA is a real gap worth surfacing in a demo

---

## Tool 4: 211.org (National and Virginia)

**What it is**: The national 2-1-1 helpline and online service directory. Virginia 211 (211virginia.org) provides Richmond-area coverage.

**What works**:
- Phone-first: accessible to residents without internet or digital literacy
- Human operators available during business hours
- Covers a wide range of basic needs
- No account required, no PII collected for general searches

**What's different from Richmond**:
- Coverage can be inconsistent; local quality depends on local 211 funding
- Phone-only model limits scale
- Not multilingual in all instances
- Not always current

**Takeaways for Richmond**:
- The no-account, no-PII model is exactly right for this population
- Phone as primary interface should be respected — any web tool should have "call 211" as a fallback
- Language line services (interpreter phone access) are a model for multilingual access without building a full multilingual UI

---

## Tool 5: UniteUs

**What it is**: A closed-loop referral platform used by social service organizations to track cross-agency referrals. Used in some Virginia markets.

**What works**:
- Closes the referral loop — organizations can see if a resident actually connected with the referred program
- Built for care coordinators and case managers
- Can reduce "did that referral happen?" phone tag

**What's different from Richmond**:
- Requires all participating organizations to be on the platform — interoperability requires buy-in
- Richmond/Virginia adoption is partial
- Not interoperable with Help1RVA or FindHelp
- Resident-facing component is limited
- Implementation costs are significant

**Takeaways for Richmond**:
- The closed-loop referral concept is what the rubric's "Cross-Agency Navigation" problem actually needs — but UniteUs requires organizational buy-in and data sharing agreements that don't exist
- A lightweight "referral receipt" concept — where a case manager can share a simple text or WhatsApp message confirming a referral was made — is a prototype-level version of this

---

## Tool 6: Integrated Benefits Initiative / One-Stop Navigation Portals

**What it is**: A category of government and nonprofit efforts to create single navigation portals for benefits and services — "no wrong door" systems.

**What works**:
- In theory: residents don't need to know which agency handles which program
- Some implementations have reduced duplicate intake by sharing consent records

**What doesn't work**:
- Requires significant backend integration — exactly what the D3=1 data constraint prevents
- HIPAA, state law, and organizational autonomy create barriers to data sharing
- Many implementations are aspirational rather than functional

**Takeaways for Richmond**:
- This is the long-term vision behind Statement 2 — but it is not weekend-buildable
- A team can demonstrate the problem (fragmentation) without claiming to solve the full integration challenge
- Framing as "here's what the service map currently looks like, and here's where the gaps are" is more credible than claiming to solve cross-agency coordination

---

## Patterns that Fail in this Space

Based on national experience with immigrant and refugee service tools:

1. **Tools that require account creation with email or phone number** — adoption collapses among undocumented residents who fear data retention
2. **Tools that ask for address or zip code to "personalize" results** — residents perceive this as location tracking
3. **Machine-translated content without human review** — inaccurate or culturally inappropriate translations erode trust and can cause harm
4. **Tools that imply eligibility determination** ("You qualify for X") — this is both legally risky and potentially misleading
5. **Tools that go dark after the hackathon** — communities that adopted a tool that then disappears feel abandoned; creates lasting distrust
6. **Tools that compete with trusted intermediaries** — if the tool is positioned as a replacement for a community navigator or case manager, adoption fails; position as support for those relationships instead
