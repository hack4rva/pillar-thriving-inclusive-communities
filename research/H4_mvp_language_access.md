# 48-Hour Multilingual MVP: Ship Spanish You Can Trust

## Executive Summary

Building a multilingual service discovery prototype in a 48-hour hackathon requires ruthless prioritization. Attempting to translate everything using unreviewed machine translation (MT) introduces severe risks for vulnerable populations, particularly regarding legal, medical, or eligibility information. Conversely, waiting for 100% professional human translation will break your time and budget constraints. 

The most viable strategic path is a **hybrid, Spanish-only MVP**. By focusing exclusively on Spanish, you can afford to professionally translate or human-review the highest-risk content (privacy notices, eligibility, emergency contacts) while safely using AI-driven machine translation for low-risk UI elements and general descriptions. 

Key strategic actions for the 48-hour window include:
* **Limit scope to navigation + 10 priority organizations**: Translate 8–10 top-level categories and 10 exemplar organization cards featuring concise, 1-2 sentence descriptions.
* **Adopt a hybrid translation model**: Use AI translation (DeepL/GPT-4) for bulk strings, but mandate bilingual human review for the four "red-line" categories: privacy, eligibility, emergency info, and legal/immigration services.
* **Implement discoverable, compliant UX**: Default to the user's browser language, place the language toggle in the top right (desktop) or main menu (mobile), and ensure WCAG 3.1.1 compliance using HTML `lang` attributes.
* **Deploy honest disclaimers**: Protect users by explicitly stating that automated translations are for convenience and the English version remains the official text.

## Scope Decision: Language Coverage You Can Stand Behind in 48 Hours

**Key takeaway:** Commit to Spanish-only for the hackathon. Queue a second language only if you have guaranteed bilingual reviewers and extra budget.

When operating within a 48-hour envelope, depth and accuracy in one language vastly outperform thin, error-prone coverage across multiple languages. Professional translation services typically require 24 to 48 hours for turnaround and charge per word, with rates ranging from $0.087 to $0.144 per word depending on the required expertise [1] [2]. 

Because high-risk content—such as privacy statements, eligibility requirements, and legal aid descriptions—demands human review to prevent real-world harm, spreading your limited review capacity across multiple languages will create bottlenecks. 

**Decision Rule:**
* **If no pre-booked professional service or community reviewer is available:** Stick strictly to Spanish-only, utilizing a bilingual team member for targeted reviews.
* **If a second bilingual reviewer is secured for 2–3 hours:** You may consider adding a second language, but restrict it strictly to UI-only strings and navigation, omitting complex service descriptions.

## Minimum Content Coverage: What to Translate for a Credible Demo

**Key takeaway:** Translate core navigation, a short privacy notice, and 10 exemplar organization listings with critical fields. Skip the long-tail content.

To demonstrate credible multilingual functionality without overextending your team, focus on the structural elements of the directory and a representative sample of service cards. Social service taxonomies typically cluster into 8 to 10 top-level categories. For example, the AIRS Taxonomy is organized into 10 major categories (such as Basic Needs, Consumer Services, Criminal Justice, and Education) [3], while Findhelp utilizes 8 primary categories (Food, Housing, Goods, Transit, Health, Money, Care, Education) [4]. 

For the organization cards, adhere to the AIRS Style Guide, which recommends brief site descriptions of no more than 1-2 sentences [5]. Service descriptions should be precise, meaningful, and omit minor details that clients can discover by contacting the program directly [5].

### MVP Content and Review Level

| Item | Est. Words | Review Level |
| :--- | :--- | :--- |
| Category + nav labels (8-10 items) | 80–150 | MT + spot-check |
| Buttons/UX microcopy | 40–120 | MT + spot-check |
| Privacy short notice | 100–150 | Human review (professional or bilingual) |
| 10 org descriptions (1-2 sentences) | 250–400 | MT + bilingual spot-check |
| Eligibility (10 items) | 120–200 | Human review |
| Documents required (10 items) | 50–100 | Human review |
| Application/intake (10 items) | 70–120 | Bilingual review |
| Fees (10 items) | 40–80 | Bilingual review |
| Emergency contacts (if present) | 10–30 | Human review |
| Immigration/legal services (if present) | 50–150 | Human review |

*Takeaway: By capping the demo at 10 organizations and adhering to strict brevity guidelines, the total translation payload remains under 1,500 words, making it highly manageable for a weekend build.*

## Translation Approach: Speed-Quality-Risk Tradeoffs for a Hackathon

**Key takeaway:** Use AI machine translation (MT) plus bilingual review as your default. Send privacy/legal text to a professional service if possible, and never ship unreviewed Google MT for this population.

Relying solely on unreviewed machine translation for social services is a critical failure point. Government agencies explicitly warn against this; for instance, the Washington State Department of Licensing notes that their third-party translation tool is "offered for information and convenience only" and that discrepancies "aren't legally binding" [6]. Similarly, the North Carolina DHHS states that automated translations "should not be considered exact and used only as an approximation" [7]. 

### Translation Options Comparison

| Option | Turnaround | Cost (per word) | Quality/Risk | Hackathon Fit |
| :--- | :--- | :--- | :--- | :--- |
| **A. Professional LSP** (e.g., BLEND) | 24–48h | ~$0.096–$0.144 | Highest; consistent | Yes, for small critical set (privacy/legal) |
| **B. Bilingual team review of MT** | Hours | Reviewer time | High if reviewer is strong | Yes (Core pattern for MVP) |
| **C. Community org review** | Days–weeks | In-kind | Highest contextual fit | No (Too slow for 48h) |
| **D. AI MT (DeepL/GPT-4) + spot-check** | Minutes–hours | Low | Good for UI/general | Yes (Default for low-risk text) |
| **E. Google MT no review** | Minutes | Free | Not reliable; highly risky | **No** (Never for vulnerable populations) |

*Takeaway: Option B combined with Option D provides the optimal balance of speed and safety for a hackathon, reserving Option A for post-hackathon hardening or highly sensitive legal text.*

## Interface & Accessibility: Make Language Easy and Compliant

**Key takeaway:** Default to the browser's language, always show a visible toggle, and set HTML `lang` attributes to meet WCAG standards.

Discoverability is the most common failure point for multilingual interfaces. Research by the Nielsen Norman Group (NN/g) shows that users consistently look to the **upper right corner** on desktop sites to change language settings [8]. On mobile devices, the language switcher should be placed above the fold or inside the main navigation menu, as placing it in the footer makes it highly undiscoverable [8]. 

Furthermore, NN/g recommends displaying the name of the available language in that language (e.g., *Español* instead of *Spanish*) and warns against using only a national flag to represent the language switch, as the target is small and flags can be misinterpreted [8]. 

To meet WCAG 3.1.1 (Language of Page) Level A compliance, the default human language of each web page must be programmatically determined [9]. This requires using the `lang` attribute on the HTML element (e.g., `<html lang="es">`) [10].

### Detection vs. Toggle Choices

| Option | Pros | Cons | Recommendation |
| :--- | :--- | :--- | :--- |
| **Auto-detect only** | Frictionless | Wrong guesses, no recourse for user | Do not use alone |
| **Toggle only** | Simple to build | Extra step, lower conversion | Weak alone |
| **Both (Hybrid)** | Best UX | Slightly more build time | **Use for MVP** |

*Takeaway: Automatically detect the user's browser settings to save them time, but always provide a manual fallback toggle in the top right corner or mobile menu.*

## Honest Labeling: Disclaimers that Build Trust

**Key takeaway:** Place short, clear disclaimers near the toggle and in the footer. State that English is the authoritative text and offer a human contact for help.

Because you are utilizing machine translation for parts of the prototype, you must protect both the user and the organization. Government websites provide excellent templates for this. The Commonwealth of Virginia notes that "automated translation software... has been used" and they do not "guarantee the accuracy, relevance, timeliness, completeness, or translation of outside information" [11]. Washington DC simply states: "No automated translation is perfect" [12].

**Sample UI Copy for the Prototype:**
* **Near the toggle (Tooltip/Banner):** "Some content is translated automatically. We strive for accuracy, but the English version is the official text. Need help? Call [phone] for assistance in your language."
* **Footer on Spanish pages:** "Este contenido puede incluir traducciones automáticas. La versión en inglés es la oficial. Si tiene preguntas o necesita ayuda en su idioma, contáctenos: [tel/email]."

## Cost & Word Budget: Right-size Scope and Spend

**Key takeaway:** Expect 700–1,200 words total for the MVP. Professional translation for the critical 200–300 words will cost roughly $19–$39.

If you choose to utilize a professional localization service like BLEND for your high-risk content, general business content starts at $0.096 per word, while industry-specific content (legal, medical) starts at $0.13 per word [1]. 

### Cost Range Assumptions

| Component | Words (Assumed) | Pro Rate Low ($0.096) | Pro Rate High ($0.13) |
| :--- | :--- | :--- | :--- |
| Privacy short notice | 120 | $11.52 | $15.60 |
| High-risk fields (eligibility/docs/fees; 10 orgs) | 300–500 | $28.80–$48.00 | $39.00–$65.00 |
| UI/nav strings | 120–200 | $11.52–$19.20 | $15.60–$26.00 |
| Org descriptions (10) | 250–400 | $24.00–$38.40 | $32.50–$52.00 |
| **Total (MVP Range)** | **790–1,220** | **$75.84–$117.12** | **$102.70–$158.60** |

*Takeaway: By relying on AI MT and bilingual team review for UI strings and general descriptions, you can reduce your actual hackathon spend to under $50, reserving professional translation strictly for the privacy notice and legal/eligibility fields.*

## 48-Hour Build Plan: Parallelize to De-risk Turnaround

**Key takeaway:** Front-load your string freeze and professional translation submissions. Parallelize MT and human review, locking integration by hour 36.

* **T+0–6h (Scoping & Extraction):** Inventory all UI strings. Select the 10 MVP organizations. Draft a concise 120-word privacy notice. Freeze all high-risk text.
* **T+6–8h (Translation Kickoff):** Submit the privacy notice and any legal/immigration copy to the professional LSP. Run the full remaining dataset through AI MT (DeepL/GPT-4). Mark high-risk items for the internal reviewer.
* **T+8–20h (Human Review):** Bilingual team member conducts a review pass on high-risk fields (eligibility, documents, emergency). Spot-check UI strings for truncation and tone.
* **T+20–30h (Integration):** Integrate Spanish strings into the codebase. Implement the language toggle and browser detection. Set HTML `lang` attributes. Add disclaimers to the footer.
* **T+30–40h (QA & Testing):** QA the interface with Spanish speakers. Test toggle placement on mobile and desktop. Fix layout breaks caused by text expansion.
* **T+40–48h (Final Polish):** Finalize the demo script. Ensure analytics tagging captures language toggle usage. 

## Quality & Review Checklist: What Must Be Human-Reviewed vs. MT Acceptable

**Key takeaway:** Four "red lines" require human eyes. Everything else can be machine-translated with basic spot checks.

| Content Category | Review Requirement | Notes |
| :--- | :--- | :--- |
| **Privacy/data handling** | **Human review** | High legal risk; use professional LSP for authoritative phrasing. |
| **Eligibility/required documents** | **Human review** | Phrases like "no papers required" must be exact to prevent harm. |
| **Emergency contact info** | **Human review** | Safety-critical accuracy is non-negotiable. |
| **Legal aid/immigration** | **Human review** | Terminology precision is required. |
| Org names | MT acceptable | Proper nouns; verify uncommon names don't auto-translate weirdly. |
| Category labels/navigation | MT acceptable | Spot-check for cultural fit. |
| Button labels/UX text | MT acceptable | Watch for UI truncation and tone. |
| General org descriptions | MT + spot-check | Ensure clarity; avoid social service jargon [5]. |
| Fees/application process | Bilingual review | Short phrases; easy to validate quickly. |

## Post-Hackathon Hardening: From Demo to Production

**Key takeaway:** Replace critical MT with professional translations, expand languages based on community data, and formalize language access.

Once the hackathon concludes, the prototype must be hardened before public release. 
1. **Commission full professional translation:** Send all high-risk and high-traffic pages to an LSP. Build a glossary/termbase to ensure consistency.
2. **Engage community organizations:** Option C (Community organization review) is ideal but requires advance coordination. Use the post-hackathon period to have local partners validate the contextual fit of your translations.
3. **Expand i18n infrastructure:** Implement string externalization and pseudo-localization tests. Only add a second language when reviewer capacity and QA processes are fully established.

## Appendix: Concrete Implementation Snippets

**HTML Accessibility (WCAG 3.1.1):**
Ensure the root HTML element declares the language [10].
```html
<!-- On Spanish pages -->
<html lang="es">

<!-- Wrap mixed-language parts -->
<p>Llame al <span lang="en">211</span> para asistencia.</p>
```

**Toggle Placement & Defaulting:**
* **Desktop:** Place in the header utility bar, top right [8].
* **Mobile:** Place as the top item in the hamburger menu [8].
* **Logic:** Read `navigator.language`. If it starts with 'es', show the Spanish version with a dismissible "Switch to English?" banner. Persist the user's explicit choice in `localStorage`.

## References

1. *Best Translation Quote For Your Localization Projects | BLEND*. https://www.getblend.com/translation-price/
2. *One Hour Translation Reviews - Read Customer Reviews of Onehourtranslation.com*. https://one-hour-translation.tenereteam.com/
3. *Major Categories in the AIRS Taxonomy Used On the ...*. https://www.scph.org/sites/default/files/docs/Major%20Categories%20in%20the%20AIRS%20Taxonomy%20Used%20On%20the%20Summit%20County%20Community%20Asset%20Map.pdf
4. *findhelp.org by Findhelp - Search and Connect to Social Care*. https://www.findhelp.org/
5. *AIRS Style Guide*. https://assets-002.noviams.com/novi-file-uploads/airs/pdfs-and-documents/AIRS_Style_Guide_2021_FINAL_7_15_2021-b4b2066c.pdf
6. *Google™ Translate disclaimer | Washington State Department of Licensing*. https://dol.wa.gov/google-translate-disclaimer
7. *NCDHHS Translation Disclaimer | NCDHHS*. https://www.ncdhhs.gov/ncdhhs-translation-disclaimer
8. *6 Tips for Improving Language Switchers on Ecommerce Sites - NN/G*. https://www.nngroup.com/articles/language-switching-ecommerce/
9. *Understanding WCAG SC 3.1.1 Language of Page • DigitalA11Y*. https://www.digitala11y.com/understanding-sc-3-1-1-language-of-page/
10. *Understanding Success Criterion 3.1.1: Language of Page | WAI | W3C*. https://www.w3.org/WAI/WCAG22/Understanding/language-of-page
11. *Translation Disclaimer*. https://www.virginia.gov/translation-disclaimer/
12. *Google Translate Disclaimer - Washington, DC*. https://dc.gov/page/google-translate-disclaimer