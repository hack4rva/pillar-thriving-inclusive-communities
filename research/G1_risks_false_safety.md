> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# False Sense of Safety in AI Governance: Hidden Risks, Real-World Failures, and Action-Ready Mitigations

## Executive Summary

Organizations increasingly rely on AI governance frameworks, risk registers, and safety benchmarks to manage the deployment of artificial intelligence. However, these tools often create a dangerous "false sense of safety" where documentation outpaces actual security. Risk registers can lull organizations into false security simply because every column is filled and signed off by the board, making everyone feel protected despite underlying vulnerabilities [1]. Furthermore, AI safety tests and benchmarks are heavily flawed, often built on unclear definitions or weak analytical methods [2]. 

This document outlines the critical gaps in current AI risk management, highlighting real-world failures such as the Unitree G1 robot's undocumented data exfiltration [3] and high-severity vulnerabilities in Markdown handling [4]. By aligning with established frameworks like the NIST AI Risk Management Framework [5] and ISO/IEC 42001 [6], organizations can transition from performative compliance to verifiable AI safety.

## Defining "False Sense of Safety"

A false sense of safety in AI governance occurs when organizations mistake the presence of compliance artifacts—such as model cards, risk registers, and basic safety filters—for actual operational security. Current market conditions and AI regulations can threaten effective AI governance because they often incentivize the appearance of safety over rigorous, adversarial testing [7]. 

For example, developers frequently rely on AI model cards to report risks, but analyses of nearly 460,000 AI model cards reveal that risk reporting is often too thin, biased toward technical issues, and lacks candid structure [8]. Similarly, safety alignment for Large Language Models (LLMs) is frequently bypassed by jailbreaking attacks, which use adversarial prompts to bypass model alignment and trigger harmful outputs [9].

## Real-World Illustrations

### Failure Cases: Exfiltration, Vulnerabilities, and AI-Washing

Real-world incidents demonstrate how assumed safety measures fail in practice. These failures span hardware, software, and corporate governance.

| Failure Category | Incident / Vulnerability | Impact & Description |
| :--- | :--- | :--- |
| **Hardware / IoT** | Unitree G1 Robot Exfiltration | The Unitree G1 humanoid robot secretly and continuously sends sensor and system data to servers in China without the owner's knowledge [3]. |
| **Software / Supply Chain** | CVE-2026-20841 (Windows Notepad) | A high-severity Windows Notepad vulnerability tied to Markdown link handling allows malicious Markdown links to trigger unsafe protocol handlers [10] [4]. |
| **Corporate Governance** | AI-Washing | Businesses expose themselves to increased risk of enforcement actions by deliberately or inadvertently misleading customers, investors, and regulators about AI capabilities and safety [11]. |

These failures highlight that relying on default configurations or vendor assurances without independent verification leads to severe security blind spots.

### Success Cases: Iterative Red-Teaming and Standards Compliance

Conversely, organizations that actively probe their systems uncover and mitigate risks before they escalate. For instance, OpenAI's Codex system utilizes active monitoring that flags potentially high-risk cyber activity and routes users to fallback models (e.g., gpt-5.2 fallback) when necessary, demonstrating an active, rather than passive, approach to safety [12]. 

## Root Causes & Systemic Drivers

The root causes of false safety stem from a misalignment between governance documentation and technical reality. 

1. **Performative Risk Registers:** Risk registers lull stakeholders into false security because the mere existence of a filled-out binder creates an illusion of protection [1].
2. **Flawed Benchmarks:** AI safety tests are heavily flawed due to unclear definitions and weak analytical methods, making it difficult to accurately gauge true model safety [2].
3. **Inadequate Threat Models:** Traditional threat models often fail to reflect the safety risks of seemingly innocuous interactions, leading to unsafe information leakage in supposedly "safe" AI systems [13].

## Business & Regulatory Impact

The consequences of AI governance failures extend beyond technical glitches to severe business and legal repercussions. AI governance failures expose organizations to professional liability risks, and the insurance and risk management sectors currently face coverage gaps regarding these specific AI-driven liabilities [14]. Furthermore, AI-generated content can create false confidence in business decisions, highlighting the hidden risk of relying solely on AI-generated expertise without human oversight [15].

## Mitigation Blueprint

### Immediate Controls: Auditing Risk Registers and Parsers

Organizations must immediately audit their existing risk registers to ensure they reflect actual, tested vulnerabilities rather than theoretical compliance. Additionally, technical teams must patch known vulnerabilities in documentation tools, such as the high-severity Notepad flaw (CVE-2026-20841) that allows malicious Markdown links to execute unsafe protocols [10].

### Mid-Term Processes: Enhancing Model Cards and Verification

To combat the "model card mirage," organizations must mandate comprehensive risk reporting that goes beyond thin, technically biased descriptions [8]. This includes systematic evaluations of jailbreak attacks targeting LLM safety alignment to assess their true success rates against content safety filters [16].

### Long-Term Governance: Aligning with ISO 42001 and NIST AI RMF

Long-term mitigation requires adopting robust, internationally recognized frameworks. 

| Framework | Focus Area | Strategic Value |
| :--- | :--- | :--- |
| **NIST AI RMF** | Cross-sectoral risk management | Helps better manage risks to individuals, organizations, and society associated with AI, including specific profiles for Generative AI [5] [17]. |
| **ISO/IEC 42001:2023** | AI Lifecycle Governance | Enables effective AI governance and establishes comprehensive risk management requirements for the entire AI lifecycle [6]. |
| **EU AI Act** | Compliance & Risk Categorization | Divides AI systems into Unacceptable, High, and General Purpose AI (GPAI) risk categories for strict compliance purposes [18]. |

## Measurement & Continuous Monitoring

Effective AI governance requires continuous monitoring rather than point-in-time assessments. Organizations must track the success rates of jailbreaking attacks against their content safety filters [16] and monitor for unsafe information leakage [13]. 

## Policy Recommendations for Leaders

1. **Mandate Independent Verification:** Do not accept risk registers at face value. Require independent red-teaming to validate the controls listed in the register [1].
2. **Avoid AI-Washing:** Ensure all public claims regarding AI safety are strictly verified to avoid misleading stakeholders and incurring regulatory penalties [11].
3. **Implement Human-in-the-Loop:** Maintain human expertise for strategic decisions to counteract the false confidence generated by AI systems [15].

## Roadmap & Implementation Timeline

| Phase | Timeframe | Key Milestones |
| :--- | :--- | :--- |
| **Phase 1: Discovery** | Months 1-3 | Audit existing risk registers [1]; Patch Markdown vulnerabilities (CVE-2026-20841) [4]. |
| **Phase 2: Assessment** | Months 4-6 | Conduct systematic evaluations of jailbreak vulnerabilities [16]; Review model cards for structural candor [8]. |
| **Phase 3: Alignment** | Months 7-9 | Map internal controls to NIST AI RMF [5] and ISO/IEC 42001 [6]. |
| **Phase 4: Integration** | Months 10-12 | Deploy continuous monitoring for data exfiltration (e.g., IoT sensors) [3] and establish liability coverage strategies [14]. |

## Conclusion & Call to Action

The transition from performative compliance to verifiable AI safety is an urgent business imperative. By recognizing the flaws in current safety benchmarks [2] and the illusory protection of static risk registers [1], organizations can proactively defend against emerging threats like prompt injections [9] and covert data exfiltration [3]. Leaders must immediately initiate independent audits of their AI governance frameworks to ensure true operational resilience.

## Appendix A - Source Bibliography

* **[10] ** Mishcon. "Windows 11 Notepad update addresses Markdown link issue." Feb 23, 2026.
* **[3] ** LinkedIn. "Unitree G1 robot secretly sends data to China, security risk." 
* **[4] ** Penligent. "CVE-2026-20841 — When Markdown in Windows Notepad Becomes an Execution Path." Mar 12, 2026.
* **[12] ** GitHub. "False positive: Codex cyber-safety flag during normal UI/dev work." Feb 18, 2026.
* **[14] ** Risk and Insurance. "AI Governance Failures Expose Organizations to Professional Liability Risks." Oct 22, 2025.
* **[1] ** LinkedIn. "Risk Registers: A False Sense of Security." Feb 11, 2026.
* **[8] ** Medium. "The Model Card Mirage: The AI Model Risk Catalog paints an uncomfortable portrait." Oct 21, 2025.
* **[7] ** arXiv. "False Sense of Security in Explainable Artificial Intelligence (XAI)." May 6, 2024.
* **[13] ** arXiv. "A False Sense of Safety: Unsafe Information Leakage in 'Safe' AI." Jul 2, 2024.
* **[5] ** NIST. "AI Risk Management Framework."
* **[6] ** AWS Security Blog. "ISO/IEC 42001:2023 for AI governance." May 13, 2025.
* **[17] ** NIST. "Artificial Intelligence Risk Management Framework: Generative AI." Jul 25, 2024.
* **[11] ** RM Magazine. "Criminally Overhyped: The Risks of AI Washing." Jan 27, 2026.
* **[2] ** Yahoo. "AI safety tests are heavily flawed, new study finds." Nov 13, 2025.
* **[15] ** Marmalade Marketing. "False Confidence: The Hidden Risk of AI-Generated Expertise." Mar 4, 2026.
* **[18] ** Security Compass. "Understanding EU AI Act Risk Categories." Aug 7, 2024.
* **[16] ** arXiv. "Jailbreaking Attacks vs. Content Safety Filters." Dec 30, 2025.
* **[9] ** arXiv. "Jailbreaking Attacks vs. Content Safety Filters: How Far Are We in..." Dec 30, 2025.

## Appendix B - Glossary

* **AI-Washing:** Deliberately or inadvertently misleading customers, investors, and regulators about an organization's AI capabilities or safety measures.
* **Jailbreaking:** The use of adversarial prompts that bypass model alignment to trigger harmful or unintended outputs from an AI system.
* **Model Card:** Documentation accompanying an AI model that details its intended use, performance characteristics, and potential risks (often found to be lacking in structural candor).
* **Risk Register:** A document used as a risk management tool to identify potential risks in a project or organization, which can sometimes create a false sense of security if not actively tested.

## References

1. *Risk Registers: A False Sense of Security - LinkedIn*. https://www.linkedin.com/posts/aerodriguez_risk-registers-lull-you-into-false-security-activity-7427366880065060865-Txy2
2. *AI safety tests are heavily flawed, new study finds - Yahoo*. https://www.yahoo.com/news/articles/ai-safety-tests-heavily-flawed-122401936.html
3. *Unitree G1 robot secretly sends data to China, security risk*. https://www.linkedin.com/posts/z6115552_the-unitree-g1-humanoid-robot-secretly-and-activity-7377353473320792064-SrDG
4. *CVE-2026-20841 — When Markdown in Windows Notepad ...*. https://www.penligent.ai/hackinglabs/cve-2026-20841-when-markdown-in-windows-notepad-becomes-an-execution-path/
5. *AI Risk Management Framework | NIST*. https://www.nist.gov/itl/ai-risk-management-framework
6. *ISO/IEC 42001:2023 for AI governance | AWS Security Blog*. https://aws.amazon.com/blogs/security/ai-lifecycle-risk-management-iso-iec-420012023-for-ai-governance/
7. *False Sense of Security in Explainable Artificial Intelligence (XAI)*. https://arxiv.org/abs/2405.03820
8. *The Model Card Mirage: The AI Model Risk Catalog paints ... - Medium*. https://medium.com/socialdynamics/the-model-card-mirage-the-ai-model-risk-catalog-paints-an-uncomfortable-portrait-df57c8f20ac1
9. *Jailbreaking Attacks vs. Content Safety Filters: How Far Are We in ...*. https://arxiv.org/html/2512.24044v1
10. *Windows 11 Notepad update addresses Markdown link issue*. https://www.mishcon.com/news/windows-11-notepad-update-addresses-markdown-link-issue
11. *Criminally Overhyped: The Risks of AI Washing*. https://www.rmmagazine.com/articles/article/2026/01/27/criminally-overhyped--the-risks-of-ai-washing
12. *False positive: Codex cyber-safety flag during normal UI/dev work*. https://github.com/openai/codex/issues/12130
13. *A False Sense of Safety: Unsafe Information Leakage in 'Safe' AI ...*. https://arxiv.org/html/2407.02551v1
14. *AI Governance Failures Expose Organizations to Professional ...*. https://riskandinsurance.com/ai-governance-failures-expose-organizations-to-professional-liability-risks/
15. *False Confidence: The Hidden Risk of AI-Generated Expertise*. https://marmalademarketing.co.uk/blog/false-confidence-the-hidden-risk-of-ai-generated-expertise?hsLang=en
16. *[2512.24044] Jailbreaking Attacks vs. Content Safety Filters - arXiv*. https://arxiv.org/abs/2512.24044
17. *[PDF] Artificial Intelligence Risk Management Framework: Generative ...*. https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf
18. *Understanding EU AI Act Risk Categories - Security Compass*. https://www.securitycompass.com/blog/understanding-eu-ai-act-risk-categories/