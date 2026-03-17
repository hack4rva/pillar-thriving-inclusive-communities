# Privacy-First, Bilingual Service Discovery for Richmond's Newcomers

## Executive Summary
Building a service discovery tool for immigrant and refugee residents requires balancing comprehensive data with absolute privacy and low-friction access. The AIRS/211 Taxonomy provides a robust backend structure of over 9,900 terms across 10 major categories [1], but the frontend must translate this into plain language that matches resident mental models. Because collecting personal data creates a "deep chilling effect" for immigrant families [2], the minimum viable product (MVP) must operate with zero data collection—no logins, no tracking, and absolutely no immigration status questions [3]. 

To maximize value per build hour for a hackathon prototype, the recommended approach is a **Static JSON frontend** featuring category browsing and essential filters ("No ID required", "Languages available"), rather than a complex live API integration with the existing Help1RVA platform. This bypasses immediate licensing hurdles while delivering a highly accessible, Spanish-first interface that builds trust through transparency, local partner endorsements, and a strict "collect nothing" privacy policy.

## Why this tool matters now — trust, language, and speed determine usage

A privacy-first, Spanish-forward, low-friction finder closes the largest access gaps faster than deeper but riskier integrations. For vulnerable populations, the barrier to entry is rarely a lack of available services, but rather the fear of enforcement and the complexity of navigating agency jargon.

### Richmond context: Help1RVA exists; newcomers still face language/privacy barriers
Richmond already benefits from Help1RVA, a comprehensive social care network powered by the findhelp platform [4] [5]. Help1RVA is a robust tool with a commitment to Web Content Accessibility Guidelines (WCAG) AA standards [6]. However, findhelp's architecture is designed for broad social care coordination, meaning its API and platform are built around user accounts, referrals, and data exchanges that can intimidate undocumented or mixed-status families. Furthermore, findhelp's API is offered on a subscription basis and requires strict adherence to their terms [7]. Position this new prototype not as a replacement for Help1RVA, but as a specialized, high-trust, low-friction complement that meets Limited English Proficiency (LEP) and privacy needs immediately, routing users to Help1RVA only when they are ready.

## Resident-first Information Architecture — labels people use, structure systems need

Show plain-language, icon-backed categories on the frontend while indexing with the AIRS/211 Taxonomy on the backend for durability and future portability. The Taxonomy provides a "common language" for human services [8].

### Recommended top-level categories mapped to Taxonomy codes
The AIRS Taxonomy organizes services into 10 basic categories and up to six levels of granularity [1]. However, residents do not think in terms of "Income Support and Employment" or "Individual and Family Life" [1]. The MVP should map resident-friendly terms to underlying Taxonomy codes:

* **Food** (Taxonomy: BD - Food)
* **Housing** (Taxonomy: BH - Housing/Shelter)
* **Health** (Taxonomy: L - Health Care)
* **Work & Money** (Taxonomy: N - Income Support and Employment)
* **Legal & Papers** (Taxonomy: F - Criminal Justice and Legal Services)
* **Family & School** (Taxonomy: P - Individual and Family Life / H - Education)
* **Transport** (Taxonomy: BT - Transportation)
* **Safety** (Taxonomy: PH - Crisis Intervention)
* **Language & Learning** (Taxonomy: PL - 6400.4500 Language Instruction)
* **Seniors & Disability** (Taxonomy: Y - Target Populations)
* **Veterans** (Taxonomy: Y - Target Populations)
* **New to the U.S.** (Taxonomy: Y - Target Populations)

### Labeling and content style grounded in plain language
The AIRS Style Guide emphasizes using active verbs and clear language, advising against accepting agency narratives directly [9]. Furthermore, Texas HHS plain language guidelines demonstrate that simpler words increase comprehension: use "help" instead of "assist," "person" instead of "applicant," and "yearly" instead of "annually" [10]. Avoid acronyms on first mention (e.g., use "Food stamps (SNAP)" instead of just "SNAP").

## MVP Feature Set — ruthless prioritization for value per build hour

Curated content, a bilingual UI, and critical filters deliver 80% of the value. Heavy workflows like guided intake trees or user accounts should be deferred.

### Must-have vs nice-to-have features

| Feature | Why it matters (Evidence) | Build Effort | Phase |
| :--- | :--- | :--- | :--- |
| **12-16 Category Tiles with Icons** | Visual cues aid LEP users; avoids text-heavy cognitive load. | Small | MVP |
| **Spanish/English Toggle** | Immediate accessibility for the largest LEP demographic. | Small | MVP |
| **Keyword + Synonym Search** | AIRS supports keyword taxonomy searches with partial/full word matching [11]. | Medium | MVP |
| **Privacy-centric Filters** | "No ID/SSN required" and "Languages available" directly address immigrant fears. | Medium | MVP |
| **Click-to-call & Hours** | Reduces friction to actual service delivery. | Small | MVP |
| **"No Results" Fallbacks** | AIRS mandates problem-solving when services are unavailable [12]. | Small | MVP |
| **Geolocation / Map View** | Helpful, but requires location permissions which can trigger privacy fears. | Large | Phase 2 |
| **Guided Question Flow** | High value, but time-intensive to map logic trees accurately. | Large | Phase 2 |

### Filters that match immigrant privacy needs
Instead of filtering by "most trusted" (which is subjective and legally risky), filter by objective, structured flags: *Documents required (None, Photo ID, Proof of Address)*, *Proof of income required*, and *Interpreter availability*. This empowers the user to make their own safety assessments.

## Search UX — balancing browse, search, and guidance

Category browsing combined with assisted keyword search yields the fastest wins for a hackathon prototype, deferring complex guided flows.

### Approach comparison: Browse vs. Search vs. Guided

| Search Mode | Strengths | Risks | MVP Decision |
| :--- | :--- | :--- | :--- |
| **Category Browsing** | Zero cognitive load; highly visual; easy to translate. | Can bury niche services if categories are too broad. | **Primary UI**. Use 12-16 icon-backed tiles. |
| **Free-text Search** | Fast for users who know exactly what they want. | High risk of "false drops" (irrelevant results) if not mapped to a controlled vocabulary [12]. | **Secondary UI**. Backed by a hidden synonym list. |
| **Guided Question Flow** | Highly personalized; mimics a live navigator. | Massive build time; requires complex logic and constant updating. | **Defer to Phase 2**. |

## Data & Integration Strategy — Static JSON now, API/MOU later

Static curation avoids licensing and format risks, accelerating the launch while planning a pathway to live data.

### Static JSON vs findhelp live sync

| Option | Speed | Legal/Contract Risk | Data Freshness | Decision |
| :--- | :--- | :--- | :--- | :--- |
| **Static JSON + Frontend** | Very Fast (Days) | Low. No API terms to negotiate. | Requires manual monthly updates. | **Select for MVP**. |
| **Live Help1RVA (findhelp) API** | Slow (Weeks/Months) | High. API is subscription-based; format changes require findhelp consent [7]. | Automated and real-time. | **Defer**. Pursue MOU later if resourced. |

### Curation scope and QA loop
Limit the MVP scope to 50-100 highly vetted, high-demand programs. To mitigate the risk of static data drift, display a "Last verified [Date]" stamp on every listing. Assign community owners to specific categories for a monthly update cadence, and include a simple "Report an issue" mailto link.

## Privacy, Trust, and Safety — design choices that lower fear

Collect nothing by default. The strongest signal of trustworthiness to an undocumented resident is the physical inability of the tool to leak their data.

### Privacy-by-design controls
Guidance from the National Immigration Law Center (NILC) and the ACLU explicitly warns against collecting immigration status, noting it has a "deep chilling effect" [2]. Furthermore, there is no general legal obligation for health centers or nonprofits to collect immigration status [3]. The MVP must feature no PII collection, no accounts, and no analytics cookies. If a "share this" feature is built, it should use native device sharing (mailto: or sms:) rather than server-side processing.

### Trust signals beyond words
Trust is visual. Place logos of recognized local coalition partners (e.g., YMCA of Greater Richmond, which already navigates social needs [4]) above the fold. Use a `.org` domain. Display a WCAG AA accessibility badge. Most importantly, prominently feature a "No papers required" filter to signal that the tool understands the user's specific vulnerabilities.

### Privacy statement draft (Plain language, <200 words)
*Draft to be displayed prominently on a single screen, available in English and Spanish:*

**Our Privacy Promise to You**
We built this tool to help you find services safely. Your privacy and safety are our top priorities. 
* **We do not track you.** We do not ask for your name, phone number, address, or email.
* **We do not ask about immigration status.** You will never be asked for your citizenship or documentation status to use this website.
* **We do not share data with the government.** Because we do not collect your personal information, we have nothing to share with ICE, law enforcement, or any government agency. 
* **You are in control.** You can search for services that do not require an ID or Social Security Number by using our "No ID required" filter.

If you choose to call an agency listed here, they may have their own rules. We recommend asking them what information they require before giving your details.

## Accessibility & Multilingual — ship Spanish-first, add audio/icons

WCAG AA compliance, Spanish translation, and pictograms meaningfully expand reach with modest effort.

### Multilingual prototype options

| Option | Benefits | Risks | MVP Pick |
| :--- | :--- | :--- | :--- |
| **Spanish-first Static UI** | Perfect translation quality; culturally nuanced. | Hard to scale to Arabic, Dari, etc. | **Yes**. Toggle between EN/ES. |
| **Image-based Categories** | Universal comprehension regardless of literacy. | Icons can be ambiguous without text. | **Yes**. Pair icons with plain text. |
| **Audio Labels** | Helps users with low literacy. | Increases payload size; requires recording. | **No**. Defer to Phase 2. |
| **Auto-translate Widget** | Covers 100+ languages instantly. | High error rate for complex legal/medical terms. | **No**. Stick to high-quality manual ES/EN first. |

## Handling "No Results" and Sparse Coverage — from dead ends to options

A "no results" page must pivot to problem-solving, not a dead end. AIRS standards dictate that when services are unavailable, the service must engage in problem-solving to identify alternative strategies [12].

### Fallback design
When a category has limited Richmond coverage, the UI should automatically display:
1. **Nearby/Related Categories**: "We couldn't find [Specific Legal Help], but here are general [Legal Aid] services."
2. **Live Help Pathways**: A prominent button to "Call 2-1-1 for live assistance."
3. **Know Your Rights**: Links to trusted resources, such as the Protecting Immigrant Families (PIF) toolkits [13].
4. **Community Sourcing**: A "Suggest a program" button that opens a blank email template, ensuring no PII is captured in a web form.

## Implementation Plan — build, measure, learn in 2-4 weeks

A small, well-indexed catalog with strong UX can launch in weeks if the scope is strictly managed.

### Tech stack and delivery
Use a static site generator (Next.js or Vite) pulling from a local JSON file. Host on Vercel or Netlify for fast, secure (HTTPS default) delivery. Implement CI/CD checks for broken links and basic accessibility (a11y) compliance.

### QA, verification, and governance
Establish a verification log (Appendix E). Assign a content owner to review the 50-100 listings monthly. Ensure all Spanish translations are reviewed by a native speaker familiar with local Richmond dialects, avoiding literal machine translations that miss cultural context.

## Phase 2 Roadmap — integrations and guided assistance

After proving value with the static MVP, the tool can expand to solve deeper navigation challenges.

### Candidate expansions
Once trust is established, Phase 2 can introduce a guided question flow to help users determine eligibility without storing their data. Geolocation can be added as an opt-in feature. Finally, if engineering resources permit, negotiate a Memorandum of Understanding (MOU) with findhelp to utilize the Help1RVA API [7], ensuring data-sharing governance aligns with the strict privacy requirements of the immigrant community.

***

## Appendices

### A. Category-to-Taxonomy mapping
* **Food**: BD-1800 (Emergency Food), BD-5000 (Food Pantries)
* **Housing**: BH-1800 (Emergency Shelter), BH-8400 (Subsidized Housing)
* **Health**: L (Health Care), LF-4900 (Community Clinics)
* **Work & Money**: N (Income Support), ND (Employment)

### B. Content Style Guide
Follow the AIRS Style Guide: use active verbs, avoid agency jargon, and ensure descriptions are precise but meaningful [9]. Apply Texas HHS plain language rules: use "help" instead of "assist," "doctor" instead of "physician," and "tooth decay" instead of "cavities" [10].

### C. Privacy Statement
*(See full draft in the "Privacy, Trust, and Safety" section above. Total word count: 138 words).*

### D. Synonym List for Keyword Search
Map resident phrases to Taxonomy terms to prevent false drops [12]:
* *Resident types*: "Food stamps", "EBT" → *System searches*: SNAP, Food Pantries
* *Resident types*: "Light bill", "Power shutoff" → *System searches*: Utility Assistance
* *Resident types*: "Papers", "Green card" → *System searches*: Immigration Legal Services

### E. Verification Log Template
Maintain a simple spreadsheet for the static JSON data:
* **Agency Name**
* **Taxonomy Code**
* **Source URL**
* **Contact Person (for updates)**
* **Last Verified Date** (Displayed on frontend)
* **Requires ID?** (Boolean)

## References

1. *TAXONOMY DEVELOPMENT RULES*. https://211hsis.org/library/Taxonomy_Development_Rules.pdf
2. *Protecting Our Students: What You Need to Know About the Rights of Immigrants and the Threat of Deportation - NILC*. https://www.nilc.org/resources/know-your-rights-immigrant-students-and-schools/
3. *Immigration Enforcement— Guidance for Health Centers*. https://assets.aclu.org/live/uploads/2025/03/2025.03.06-Immigration-HealthCenters-2.pdf
4. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva
5. *Henrico Prevention Services  – Service Partner Detail*. https://prevention.henrico.gov/partner?org=sneadk
6. *
        Help1RVA Greater Richmond Resource Directory
            | Accessibility
    *. https://help1rva.org/legal/accessibility
7. *Terms for Organizations - Findhelp*. https://company.findhelp.com/cbo-terms/
8. *What is the 211HSIS Taxonomy and Why is it Important?*. https://211hsis.org/library/What_is_the_211HSIS_Taxonomy_and_Why_is_it_Important_.pdf
9. *AIRS Style Guide*. https://assets-002.noviams.com/novi-file-uploads/airs/pdfs-and-documents/AIRS_Style_Guide_2021_FINAL_7_15_2021-b4b2066c.pdf
10. *Plain Language Terms and Phrases | Texas Health and Human Services*. https://www.hhs.texas.gov/hhs-brand-guide/grammar/plain-language-terms-phrases
11. *AIRS STANDARDS AND QUALITY INDICATORS FOR ...*. https://www.211texas.org/wp-content/uploads/AIRS_Standards_9_0_Final-1.pdf
12. *AIRS STANDARDS AND QUALITY INDICATORS FOR ...*. https://www.advancingstates.org/sites/default/files/AIRS%20Standards%208th%20Edition.pdf
13. *Data Privacy and Public Programs Toolkit - Protecting Immigrant Families*. https://pifcoalition.org/toolkits/data-privacy-and-public-programs/