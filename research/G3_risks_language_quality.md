# Preventable Harm: Managing Mistranslation Risks in Multilingual Service Tools

## Executive Summary
Deploying multilingual civic and social service tools using unsupervised machine translation (MT) introduces severe risks for immigrant and refugee communities. While tools like Google Translate and DeepL have improved, small sentence-level errors compound into critical page-level risks that can misrepresent eligibility, misdirect users, and erode trust. Studies on emergency discharge instructions reveal that while Google Translate achieves 96% sentence accuracy for Spanish, 24% of translated instruction sets still contained at least one inaccuracy, with up to 6% posing potential harm [1]. For Chinese, 8% of translated sentences carried a potential for significant harm [2]. 

Furthermore, government bodies like the NYC Mayor's Office of Immigrant Affairs (MOIA) explicitly warn that unsupervised MT creates "serious risks," particularly for technical, legal, or culturally nuanced content, and strictly prohibit its use for vital information [3]. To build responsible tools during hackathons and beyond, teams must adopt a "Machine Translation + Human Review" minimum viable approach, strictly gate high-risk content, and implement clear UI disclaimers.

## Why This Matters Now: The Stakes of Mistranslation

### The Use Case and Stakes
Service navigation tools guide vulnerable populations through complex eligibility requirements, legal rights, and emergency contacts. When these tools rely on raw machine translation, the consequences extend beyond mere confusion. A mistranslated eligibility requirement can cause a resident to waste hours contacting the wrong organization or missing a critical deadline. Culturally inappropriate phrasing or incorrect regional dialects (e.g., Castilian vs. Latin American Spanish) can make the content feel foreign, immediately eroding trust in the tool and the organization providing it.

### Evidence Snapshot Across Domains
The medical and civic sectors provide clear evidence of MT limitations. In clinical settings, while GPT and Google Translate achieved ≥90% sentence-level accuracy for Spanish and Chinese, accuracy dropped significantly for Russian (80% for Google Translate) [1]. Government guidelines reflect these risks: NYC's Local Law 13 guidance mandates that agencies restrict machine translation to "basic, non-critical information" and warns against inputting sensitive personal information into free MT tools due to data security risks [4]. Similarly, the UK Home Office advises teams to "use online translators for guidance purposes only" and warns against inputting sensitive information [5].

## Risk Register for Translation Failures

| Risk Scenario | Failure Mode Example | Impact Severity | Primary Controls |
| :--- | :--- | :--- | :--- |
| **Misstated Eligibility** | "You qualify" instead of "You may qualify" | High | Plain language source; professional translator; second-eye review. |
| **Misformatted Contact Info** | Phone numbers or addresses lose digits or locale formatting | High | Use locale validators; treat numbers as non-translatable tokens. |
| **Inaccurate Legal/Procedural Terms** | Incorrect translation of rights, deadlines, or appeals | Very High | Prohibit MT-only; require certified translation and legal review [4]. |
| **Privacy Breaches** | PII entered into free public MT tools | High | Ban free MT for sensitive data; use secure, enterprise MT [4] [5]. |
| **Dialect Mismatch** | Using Castilian Spanish for a Latin American user base | Medium | Establish language style guides; conduct community QA. |
| **Offensive/Literal Phrasing** | Idioms translated literally, causing confusion or offense | Medium | Avoid idioms in source text [5]; community review. |

*Takeaway:* The most severe risks are concentrated in legal, procedural, and eligibility content. Formatting failures (like broken phone numbers) and privacy breaches are highly preventable with basic technical controls and strict data policies.

## Accuracy Landscape by Language and Tool

| Language / Tool | Evidence Summary & Accuracy | Common Error Types | Strategic Implication |
| :--- | :--- | :--- | :--- |
| **Spanish** | Google Translate: 96% sentence accuracy; 24% of sets inaccurate; ≤6% harm [1]. | Nuance, medical/legal terminology, tone. | MT post-editing (MTPE) is viable with professional review. |
| **Chinese** | Google Translate: 90% sentence accuracy; 8% of sentences had potential for significant harm [1] [2]. | Word order, complex grammar, idioms. | MTPE requires rigorous second-eye review. |
| **Russian** | Google Translate: 80% sentence accuracy; 66% of sets contained inaccuracies [1]. | Contextual meaning, grammar. | High risk; lean heavily on human translation. |
| **Low-Resource (e.g., Wolof, Fulani)** | MT systems have far less training data, resulting in significantly lower accuracy [3]. | Complete loss of meaning, hallucination. | Human interpretation/translation is mandatory [4]. |
| **DeepL (Tool)** | Excels in accuracy and natural fluency for European languages [6] [7]. | Limited language support (31 languages) [7]. | Preferred for Spanish/French; use for supported languages. |
| **Google Translate (Tool)** | Covers ~133 languages; good for basic understanding [7]. | Struggles with intricate linguistic nuances and specialized terminology [7]. | Use for broader coverage, but mandate human review. |

*Takeaway:* Engine choice should be strategic. DeepL is generally preferred for European language pairs due to better contextual understanding, while Google Translate offers broader coverage but requires heavier human oversight for non-European and low-resource languages [6] [7].

## Content Categories Ranked by Translation Risk Level

| Risk Level | Content Types | Required Translation Approach |
| :--- | :--- | :--- |
| **High Risk (Never MT-Only)** | Eligibility requirements, legal rights, consent forms, emergency contacts, notices of service denial/reduction [8]. | Professional human translation ONLY. Must include a bilingual second-eye review. |
| **Medium Risk** | General service descriptions, lists of required documents, appointment instructions. | Machine Translation + Professional Post-Editing (MTPE) + Second-eye review. |
| **Low Risk** | General announcements, greetings, basic UI navigation elements. | Machine Translation + Bilingual staff spot-check. |

*Takeaway:* Treat "vital documents" as high-risk. NYC guidance explicitly states that for "legal, medical, financial, or other vital information, always use professional interpretation services" [4].

## Minimum Viable Responsible Approach (MVRA) for Hackathons

For hackathon teams building multilingual tools, the minimum responsible approach is **"MT + Human Review."** 

1. **Scope Narrowly:** Limit the MVP to 1-2 high-need languages (e.g., Spanish) and only publish low-to-medium risk content.
2. **Plain Language Source:** Write the English source text simply. Avoid idioms, phrasal verbs, and complex tenses, as these break machine translators [5].
3. **Protected MT:** Use API-based MT (like DeepL Pro) rather than pasting text into free web portals to avoid data security risks [4].
4. **Human Post-Editing:** Have a bilingual team member or community partner review and edit the MT output before it goes live. The UK Government Digital Service (GDS) mandates that translated text must be submitted for "2nd eyes" review before publishing [9].
5. **Technical Safeguards:** Tokenize phone numbers, addresses, and dates so they are not altered by the translation engine.

## Required vs. Nice-to-Have Human Review Steps

| Review Step | High-Risk Content | Medium-Risk Content | Low-Risk Content |
| :--- | :--- | :--- | :--- |
| **Plain-language source rewrite** | Required | Required | Recommended |
| **Professional translator post-edit** | Required | Required | Optional |
| **Second-eye (bilingual) review** | Required | Required | Recommended |
| **Legal/Policy accuracy review** | Required | Optional | N/A |
| **Community review (cultural fit)** | Required | Recommended | Optional |
| **Usability testing in target language** | Recommended | Recommended | Optional |

*Takeaway:* Match your Quality Assurance (QA) rigor to the content's risk level. A second-eye review is non-negotiable for anything related to accessing services.

## UI Labeling and Disclaimers

Machine-translated content must be clearly labeled to set user expectations and reduce liability. Clinical studies recommend including automated warnings regarding the use of machine translation to minimize potential harm [2].

**Recommended Disclaimer Strategy:**
* **Disclaimer Text:** *"This page was translated by a computer to help you find information quickly. It may contain errors. For official information or free help in your language, please call [Phone Number]."*
* **Placement:** Place the disclaimer in a persistent banner at the top of the page and near primary Calls to Action (CTAs).
* **Translation:** The disclaimer itself *must* be human-translated into the target languages prior to launch.

## Who Reviews What: Roles and Responsibilities

| Role | Responsibilities | Minimum Qualifications |
| :--- | :--- | :--- |
| **Qualified Translator** | Primary translation or MT post-editing; ensures terminology consistency. | Professional translation experience in the specific domain (e.g., civic, legal). |
| **Bilingual Second-Eye** | Checks for context, formatting errors (links/numbers), and overall readability [9]. | Fluent bilingual staff member or contractor. |
| **Community Reviewer** | Validates cultural fit, dialect appropriateness, and usability. | Member of the target demographic/community-based organization. |
| **Language Access Owner** | Manages vendor relationships, tracks translation incidents, ensures policy compliance [10]. | Project Manager or Product Owner. |

*Takeaway:* Effective language access requires a mix of professional linguistic precision and on-the-ground community validation. Relying solely on unsupervised MT without designated reviewers is a critical governance failure [3].

## References

1. *
            Evaluation of the accuracy and safety of machine translation of patient-specific discharge instructions: a comparative analysis - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC12252260/
2. *
            Assessing the Use of Google Translate for Spanish and Chinese Translations of Emergency Department Discharge Instructions - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC6450297/
3. *Local Law 30 Report*. https://www.nyc.gov/assets/immigrants/downloads/pdf/FY25-Language-Access-Annual-Report.pdf
4. *Guidance on Temporary Languages New York City ...*. https://www.nyc.gov/assets/immigrants/downloads/pdf/LL13_guidance_FY25_Q4.pdf
5. *Limited English - Home Office User-Centred Design Manual*. https://design.homeoffice.gov.uk/design-and-content/content/designing-for-limited-english
6. *Exploring Translation Tools: Google Translate and DeepL |  University of Wisconsin Law School*. https://law.wisc.edu/newsletter/Law_Library/_2025-01-29
7. *DeepL vs Google Translate*. https://www.machinetranslation.com/blog/deepl-vs-google-translate
8. *Local Law 30 Report*. https://www.nyc.gov/assets/immigrants/downloads/pdf/CY2020-local-law-30-report.pdf
9. *  How to publish on GOV.UK - Translations - Guidance - GOV.UK
*. https://www.gov.uk/guidance/how-to-publish-on-gov-uk/translations
10. *Mayor's Office of Immigrant Affairs*. https://www.nyc.gov/assets/immigrants/downloads/pdf/FY2023-local-law-30-reports.pdf