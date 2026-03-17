# Safer Civic Tech: Steering Innovation Away from High-Risk Pitfalls

## Executive Summary

Civic technology projects often begin with the noble goal of helping vulnerable populations access critical services. However, without a deep understanding of legal, regulatory, and ethical constraints, well-intentioned tools can inadvertently expose residents to severe risks. This report outlines four critical "Do Not Build" categories for civic tech initiatives: collecting Personally Identifiable Information (PII) and immigration status, building automated eligibility determinators, attempting unauthorized agency system integrations, and deploying automated decision-making for vulnerable users. 

By examining recent regulatory actions—such as the Federal Trade Commission's crackdown on deceptive AI legal tools [1] —and federal privacy standards like the General Services Administration's (GSA) Digital Analytics Program [2], this report provides a roadmap for what to build instead. The focus must shift toward anonymous access, plain-language guidance, open data utilization, and human-in-the-loop systems that empower rather than endanger residents.

## 1. Why Good Intentions Go Bad—Hidden Compliance Traps in Civic Tech

Most harm in civic tech stems from mismatched ambition and legal reality, not from the technology itself. Developers often assume that collecting more data leads to better, more personalized services. In reality, digital systems encode policy choices and introduce potential for bias, risk for mistakes, and the overprioritization of computer assessments over human judgment [3]. When dealing with vulnerable populations, the consequences of a data breach, a subpoena, or an algorithmic error are not just bugs—they are life-altering events. 

## 2. Category 1 — PII & Immigration Status: Designing for Zero Subpoena Exposure

**The Risk:** Tools that require residents to enter their name, address, phone, email, immigration status, or income to "personalize" results create a massive liability. This data could be subpoenaed. Even if the developer intends to protect it, legal processes, data breaches, or organizational changes could expose it, causing severe harm to vulnerable residents.

**The Rationale:** Government and civic tech best practices mandate strict data minimization. For example, the GSA's Digital Analytics Program (DAP) explicitly forbids agencies from passing any PII into the account and ensures that IP-address masking (anonymization) takes place immediately in memory before any storage occurs [2]. The program successfully tracks web traffic across approximately 7,000 federal hostnames without tracking individuals [4]. Similarly, the UK's GOV.UK privacy policy ensures users cannot be directly identified from analytics data by not storing IP addresses [5].

**What to Build Instead:** 
* **Anonymous, Session-Based Tools:** Build applications that do not require user accounts or logins. 
* **Localized Resource Maps:** Create tools that allow users to browse services by neighborhood or zip code without saving their specific location data.
* **Privacy-First Analytics:** Implement cookie-less, anonymized tracking methods that measure aggregate usage without logging individual search queries.

## 3. Category 2 — Eligibility Determination: Complexity Humans Still Handle Better

**The Risk:** Tools that tell residents whether they qualify for a specific program, filter services based on user-entered eligibility criteria, or use rules engines to match residents to benefits.

**The Rationale:** Eligibility rules are highly complex, change frequently, and require trained caseworkers to apply correctly. An incorrect eligibility determination from a software tool could cause a resident to miss a critical benefit or be wrongly turned away. Automation in these systems introduces potential for bias and risk for mistakes [3]. 

**What to Build Instead:**
* **Pre-Screening with Strict Disclaimers:** Build screeners that recommend programs to *consider*, but explicitly state they do not determine eligibility. For example, ACCESS NYC's screener states it "cannot guarantee eligibility" and that the administering agency determines final eligibility [6]. Kentucky's kynect tool similarly warns that "Results do not guarantee eligibility. Application is required" [7].
* **Plain-Language Guides:** Translate complex bureaucratic requirements into clear, accessible language. Plain language helps claimants better understand the complexities of systems and more easily access benefits [8] [9].
* **Document Preparation Checklists:** Build tools that help users gather the standard documents (ID, proof of address, income statements) they will need *before* they apply.

## 4. Category 3 — Agency System Integration: When "Single View of Resident" Becomes a Breach

**The Risk:** Tools that claim to integrate with City DSS, Housing, or workforce program databases, attempt to read or write to internal agency case management systems, or propose to share resident data between agencies without existing data sharing agreements.

**The Rationale:** HIPAA, state laws, and strict organizational policies create necessary walls around resident data. Any "integration" built rapidly without formal Memorandums of Understanding (MOUs) and security audits is either non-functional or represents a massive compliance and security risk. 

**What to Build Instead:**
* **Open Data Directory Consumers:** Build tools that pull from public, open-source data feeds (like the Open Referral Human Services Data Specification) to display service locations and hours.
* **One-Way Information Portals:** Design systems that provide users with the exact links, phone numbers, and physical addresses of the official agency portals where they can securely log in.
* **Referral Generators:** Create tools that generate a standardized PDF or email template that the *resident* can choose to send to a provider, keeping the data control entirely in the user's hands.

## 5. Category 4 — Automated Decision-Making: Avoid the Next DoNotPay Headlines

**The Risk:** Tools that make referral decisions without human review, chatbots that give specific legal, immigration, or benefits advice, or AI systems that route residents to services without disclosing the AI's limitations.

**The Rationale:** The consequences of an incorrect automated decision are serious; residents in crisis need reliable guidance, not a high-confidence wrong answer. The legal landscape is actively punishing unauthorized AI advice. 

### The Legal Fallout of AI Advice

| Company/Tool | Legal Action | Core Allegation | Outcome/Status |
| :--- | :--- | :--- | :--- |
| **DoNotPay** | FTC Final Order (Feb 2025) | Deceptive claims about "AI lawyer" abilities; failure to test quality [1]. | Prohibited from deceptive claims; monetary relief imposed [1]. |
| **DoNotPay** | Class Action (Edelson P.C.) | Unauthorized practice of law; program is not barred in any jurisdiction [10]. | Sued for unlawful business practices [10] [11]. |
| **ChatGPT (OpenAI)** | Seventh Circuit Lawsuit | Unlicensed practice of law by providing legal analysis and drafting filings [12]. | Seeking injunction against providing legal assistance in Illinois [12]. |
| **AI Chatbots** | New York SB 7263 | Providing substantive professional advice via AI [13]. | Proposed bill to create liability for chatbot proprietors [13]. |

The White House Office of Science and Technology Policy (OSTP) Blueprint for an AI Bill of Rights explicitly calls for "Human Alternatives, Consideration, and Fallback," stating users should be able to opt out of automated systems in favor of a human alternative [14]. 

**What to Build Instead:**
* **Human-in-the-Loop (HITL) Triage:** Use AI to scan documents or extract information to assist caseworkers, but ensure a human makes the final determination [15].
* **Scripted FAQ Bots:** Deploy chatbots that only serve pre-approved, static answers to common questions, with clear boundaries and no generative advice capabilities.
* **Warm Handoff Systems:** Build routing tools that quickly connect a user to a live human navigator or legal aid hotline, rather than trying to solve the complex issue algorithmically.

## 6. Safer Innovation Playbook—What to Build Instead

To ensure hackathons and civic tech projects deliver value without causing harm, teams should pivot their energy toward the following safe, high-impact alternatives.

### Safe Civic Tech Alternatives

| High-Risk Concept (Do Not Build) | Safe Alternative (Build This) | Why It Works |
| :--- | :--- | :--- |
| PII-based personalized dashboards | Anonymous, zip-code based resource locators | Eliminates subpoena risk while still narrowing down relevant local services. |
| Algorithmic eligibility determinators | Plain-language requirement checklists with disclaimers | Empowers the user with knowledge without making legally binding or erroneous promises [6]. |
| Direct API integration with case management | Open-data service directory aggregators | Uses public data safely without violating HIPAA or requiring complex MOUs. |
| Generative AI legal/benefits advisors | Guided pathways to official legal aid hotlines | Avoids unauthorized practice of law lawsuits [10] and ensures users get certified help. |

## 7. Implementation Roadmap—From Concept to Launch Without Legal Surprises

To build safely in the civic tech space, teams must adopt a stage-gated approach that prioritizes privacy and human oversight from day one.

### Phase 1: Privacy by Design
Assume all data collected will eventually be public or subpoenaed. Implement IP anonymization immediately, mirroring federal standards [2]. Do not create database schemas for names, addresses, or immigration status.

### Phase 2: Content Over Code
Before writing complex matching algorithms, invest in content design. Rewrite bureaucratic program descriptions into plain language [8]. Clear communication often solves the user's problem better than a complex predictive model.

### Phase 3: Human-Centric Fallbacks
Align with the NIST AI Risk Management Framework [16] and the OSTP AI Bill of Rights [14] by ensuring every digital tool has a clear, accessible escalation path to a human caseworker. Technology should accelerate the connection between a resident in need and a trained professional, not replace the professional entirely.

## References

1. *FTC Finalizes Order with DoNotPay That Prohibits Deceptive 'AI Lawyer' Claims, Imposes Monetary Relief, and Requires Notice to Past Subscribers | Federal Trade Commission*. https://www.ftc.gov/news-events/news/press-releases/2025/02/ftc-finalizes-order-donotpay-prohibits-deceptive-ai-lawyer-claims-imposes-monetary-relief-requires
2. *Terms of service | Digital.gov*. https://digital.gov/guides/dap/gsa-dap-terms-of-service
3. *Implementing Benefits Eligibility + Enrollment Systems: Key Context - Digital Government Hub*. https://digitalgovernmenthub.org/publications/implementing-benefits-eligibility-enrollment-systems-key-context/
4. *analytics.usa.gov | The US government's web traffic.*. https://analytics.usa.gov/about
5. *Privacy notice - GOV.UK*. https://www.gov.uk/help/privacy-notice
6. *Step 1 of 10 - Eligibility Screener*. https://access.nyc.gov/eligibility/
7. *Benefit Eligibility Screening Tool | kynect Benefits*. https://www.kynect.ky.gov/benefits/s/prescreening?language=es
8. *Plain Language | U.S. Department of Labor*. https://www.dol.gov/agencies/eta/ui-modernization/use-plain-language
9. *An introduction to plain language - Digital.gov*. https://digital.gov/resources/an-introduction-to-plain-language
10. *Lawyer Bot Short-Circuited by Class Action Alleging ...*. https://www.wilsonelser.com/publications/lawyer-bot-short-circuited-by-class-action-alleging-unauthorized-practice-of-law
11. *DoNotPay Cases Underscore Hurdles For AI-Fueled Legal Help*. https://technologylaw.fkks.com/post/102j901/donotpay-cases-underscore-hurdles-for-ai-fueled-legal-help
12. *Seventh Circuit Lawsuit Seeks to Expand Cognizable Claims Scope A*. https://natlawreview.com/article/lawsuit-alleges-ai-chatbot-engages-unauthorized-practice-law
13. *New York Bill Would Create Liability for Chatbot Proprietors Offering Professional Advice | Insights | Holland & Knight*. https://www.hklaw.com/en/insights/publications/2026/03/new-york-bill-would-create-liability-for-chatbot-proprietors
14. *Blueprint for an AI Bill of Rights | OSTP | The White House*. https://data.aclum.org/storage/2025/01/OSTP_www_whitehouse_gov_ostp_ai-bill-of-rights.pdf
15. *Human-in-the-Loop AI for the Public Sector: Step-by-Step Guide*. https://naviant.com/blog/human-in-the-loop-ai-government/
16. *AI Risk Management Framework | NIST*. https://www.nist.gov/itl/ai-risk-management-framework