> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Richmond Immigrant Data: Minimizing PII Exposure under HIPAA, Part 2, and ICE Access

## Executive Summary
Building a service navigation tool for immigrant and refugee communities in Richmond requires treating technical metadata as highly sensitive Personally Identifiable Information (PII). Immigration and Customs Enforcement (ICE) routinely uses administrative subpoenas to compel tech platforms to hand over IP addresses, connection records, and location data. Furthermore, the Department of Homeland Security (DHS) rescinded its 2021 "Protected Areas" memo in January 2025, meaning physical locations like clinics and schools are no longer reliable safe zones from enforcement. 

To protect undocumented residents, civic tech tools must adopt a "No Account, No Tracking" architecture. This means zero retention of search histories, IP anonymization, and the complete removal of third-party ad-tech trackers (like Google Analytics or Meta Pixel). Additionally, any tool interacting with Substance Use Disorder (SUD) treatment providers must navigate the strict 42 CFR Part 2 regulations, which carry severe civil penalties for unauthorized re-disclosure.

## Context: Why PII Minimization Is Existential Here

Service-use logs can elevate real enforcement risk for undocumented Richmond residents. The legal and policy landscape surrounding immigration enforcement directly targets the digital footprints left by individuals seeking essential services.

### 2025 Policy Shift Weakens Location Safe Zones
Historically, DHS policies discouraged enforcement actions near "protected areas" such as schools, medical facilities, and places of worship [1] [2]. However, on January 20, 2025, DHS superseded and rescinded the October 2021 "Guidelines for Enforcement Actions in or Near Protected Areas" [3]. Current Customs and Border Protection (CBP) guidance notes that while generally avoided, enforcement actions "may occur in or near protected areas in limited circumstances" [4]. Consequently, service locations can no longer be relied upon as de facto privacy shields.

### Community Harm Mechanism: Fear and Chilling Effects
When service-seeking behavior is logged, the risk of exposure deters vulnerable populations from accessing critical care. The Department of Health and Human Services (HHS) explicitly notes that "fear of discrimination or legal trouble can deter people from seeking SUD treatment" [5]. Logging visits to health clinics, food banks, or legal aid centers creates a chilling effect that undermines the core mission of a civic tech directory.

## What Counts as PII Here—Beyond the Obvious

In the context of immigration enforcement, PII extends far beyond names, addresses, and phone numbers. Technical metadata is actively weaponized to locate individuals.

### Evidence of High-Risk "Technical Identifiers"
ICE frequently issues administrative subpoenas to tech companies seeking expansive personal information. These requests specifically target connection records (including assigned IP addresses), session times and durations, and the physical location of accounts [6]. Therefore, IP addresses, device fingerprints, and precise geolocation must be treated as high-risk PII.

### Non-Obvious Linkages That Re-Identify Users
Even if a user does not create an account, combining an IP address, a timestamp, and the specific service page visited (e.g., an undocumented worker legal clinic) can infer immigration status. If this data is handed over to law enforcement, it can be cross-referenced with other databases to identify and locate the user.

## Legal Access Pathways to Your Data

Government agencies have multiple legal avenues to demand data from civic tech platforms. Understanding these pathways is critical for designing data retention policies.

### Comparison Table — Government Demands You May Receive

| Demand Type | Statutory Authority | Issuing Entity | Standard Required | Data Reach | Your Options |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **ICE Administrative Subpoena** | 8 U.S.C. § 1225(d)(4) [7] | ICE Officer | None pre-court | Broad records (IPs, logs) [6] | Can refuse absent a federal court order [8] [6] |
| **SCA Warrant** | 18 U.S.C. § 2703 [9] | Court | Probable Cause | Content <= 180 days [9] | Must comply, but can challenge scope |
| **SCA Subpoena / 2703(d) Order** | 18 U.S.C. § 2703 [9] | Court / Agency | Relevance / Specific facts | Older content, non-content metadata [9] | Seek narrowing; require warrant for recent content |
| **Preservation Letter** | 18 U.S.C. § 2703(f) [10] | Law Enforcement | Low bar | Freeze existing data [10] | Preserve existing data; does not require new collection |

*Takeaway:* Administrative subpoenas are common but not self-enforcing, while SCA warrants require probable cause for recent communications content.

### SCA Mechanics That Matter for Design
The Stored Communications Act (SCA) generally requires a warrant for new electronic communications content held for 180 days or less, but offers less robust protection for older content and non-content information [9]. To minimize exposure, platforms should avoid storing user content entirely and set aggressive deletion schedules (e.g., 7 days) for non-content metadata.

### Administrative Subpoenas: Scope, Enforcement, and Resistance
ICE administrative subpoenas, often issued under 8 U.S.C. § 1225(d)(4), are signed by an ICE officer, not a judge [8]. They do not require compliance without a judicial order from a federal court [6]. Recipients can lawfully resist these subpoenas, and any gag orders contained within them generally have no legal effect [8].

## Health Privacy Layers: HIPAA vs Part 2 vs Everything Else

While civic tech directories may not always fall under HIPAA, interacting with specific health data triggers severe federal regulations.

### 42 CFR Part 2 Is Binding on "Lawful Holders," Not Just Providers
Records related to Substance Use Disorder (SUD) treatment are protected by 42 CFR Part 2. In 2024, HHS published a final rule aligning Part 2 with HIPAA, with compliance required by February 16, 2026 [5]. These rules apply not only to programs but also to "lawful holders" of the data [11]. The Office for Civil Rights (OCR) enforces Part 2 and can impose civil money penalties for violations [5].

### Table — Health-Adjacent Sensitive Data (and What You Must Not Log)

| Data Category | Legal Regime | Example Signals to Avoid Logging | If Storage is Unavoidable |
| :--- | :--- | :--- | :--- |
| **SUD Treatment** | 42 CFR Part 2 [5] | Clicks on rehab clinics, SUD search terms | Segregate access; require specific, revocable consent [12] |
| **Behavioral Health** | HIPAA / State Law | Mental health counselor referrals | Execute Business Associate Agreements (BAAs) |
| **Reproductive Health** | HIPAA / State Law | Abortion clinic map routing | Zero retention; edge-anonymization |

*Takeaway:* SUD data is heavily regulated and carries civil penalties if mishandled. Categorically avoid storing user interactions that reveal SUD diagnosis or referrals.

### HIPAA Applicability Boundaries for Civic Tools
Most standalone civic tech directories are not HIPAA Covered Entities. However, if the tool integrates directly with health providers to transmit patient data, it may become a Business Associate. Furthermore, if participating providers use tracking technologies on their own sites, IP addresses and page visits may be considered Protected Health Information (PHI) under recent HHS guidance.

## PII Exposure Risk Assessment (Richmond Civic Tool)

The greatest risks stem from third-party tracking and detailed server logs that tie individuals to protected services.

### Table — Top 10 Data Elements by Risk and Recommended Handling

| Data Element | Risk Rationale | Default Action | Max Retention |
| :--- | :--- | :--- | :--- |
| **IP Address** | Subpoenaed by ICE to locate users [6] | Anonymize/Drop at edge | None (or 7 days hashed) |
| **Precise Location** | Reveals visits to sensitive sites | Truncate/Round to zip code | None |
| **Device Fingerprint** | Re-identifies anonymous users | Disable collection | None |
| **Search Terms** | Reveals health/immigration needs | Aggregate only | 14 days |
| **Referral Clicks** | Maps users to specific providers | Aggregate only | 14 days |

*Takeaway:* Technical metadata must be aggressively minimized. If you do not collect it, you cannot be compelled to produce it.

### Failure Cases and How to Avoid Them
A common failure case occurs when a platform uses Google Analytics, and ICE subpoenas Google for the platform's visitor data. Because the platform does not control Google's response, the data is surrendered. To avoid this, platforms must self-host analytics and ban third-party tracking scripts.

## Minimum Privacy-by-Design Requirements

A responsible tool for this population must be built on an anonymous-by-default architecture.

### Architecture Musts
The platform must operate on a "No Account, No Tracking" model. Users should not be required to log in to access the directory. IP addresses must be anonymized at the network edge, and all data at rest must be encrypted.

### Hosting/Infrastructure Choices That Reduce Risk
Use US-based hosting regions to avoid cross-border data transfer complications. Implement a Web Application Firewall (WAF) but configure it to minimize the retention of raw access logs. Avoid cloud providers that aggressively monetize tenant data.

### Analytics: Acceptable vs Unacceptable (for this use case)

| Analytics Tool | Status | Rationale |
| :--- | :--- | :--- |
| **Matomo / Plausible** | Acceptable | Self-hosted, allows strict IP anonymization and data minimization. |
| **Google Analytics / Meta Pixel** | Unacceptable | Third-party data sharing; vulnerable to direct ICE subpoenas [6]. |
| **Session Replay (Hotjar)** | Unacceptable | Captures keystrokes and sensitive search behavior. |

*Takeaway:* Only self-hosted, privacy-preserving analytics tools are acceptable for this threat model.

## Specific Technology Recommendations

### Hosting and Network
Deploy infrastructure within a private network (VPC) with strict ingress/egress rules. Configure Content Delivery Networks (CDNs) to drop the last octet of IP addresses before logging, or disable access logs entirely if operational requirements permit.

### Data Layer and Logging
Implement event-level aggregation rather than user-level tracking. Ensure k-anonymity thresholds are met before displaying any public metrics. Set strict Time-To-Live (TTL) policies on all application logs (e.g., 7 to 14 days).

### Client-Side Protections
Implement a strict Content Security Policy (CSP) to prevent the accidental inclusion of third-party scripts. Do not use cookies for tracking; rely only on essential session tokens if absolutely necessary, and clear them immediately upon session end.

## Government Request Response Plan

Organizations must have a pre-defined playbook for handling government data demands.

### Table — Request Type -> First 72-Hour Checklist

| Request Type | Verify Authority | Preservation Scope | Production Stance |
| :--- | :--- | :--- | :--- |
| **ICE Admin Subpoena** | Check 8 U.S.C. § 1225(d)(4) [7] | None required automatically | Refuse absent federal court order [8] [6] |
| **2703(f) Preservation** | Verify law enforcement origin | Freeze existing data [10] | Do not produce; await warrant |
| **SCA Warrant** | Verify judge signature | Freeze requested scope | Produce only explicitly scoped data |

*Takeaway:* Never voluntarily produce data to ICE without a federal court order, and always route requests through legal counsel immediately.

## What Needs Lawyer Review Before Launch

Before deploying the tool to real users, legal counsel must review several critical components:
* **Part 2 Exposure Analysis:** Verify whether the directory's interaction with SUD providers makes the platform a "lawful holder" subject to 42 CFR Part 2 penalties [5] [11].
* **Subpoena SOPs:** Draft and approve standard operating procedures for resisting administrative subpoenas under 8 U.S.C. § 1225(d)(4) [7].
* **Vendor DPAs:** Review Data Processing Agreements with hosting providers to ensure they will notify the organization of any government data requests and will not voluntarily disclose data.

## Implementation Roadmap (90 Days)

* **Sprint 1 (Weeks 1-3):** Conduct a data inventory. Strip all third-party tracking scripts (Google Analytics, Meta) from the codebase. Deploy self-hosted analytics (e.g., Plausible).
* **Sprint 2 (Weeks 4-6):** Configure network-level IP anonymization. Implement automated log deletion scripts (14-day TTL). Draft the Government Data Request Playbook.
* **Sprint 3 (Weeks 7-9):** Finalize legal review of Part 2 compliance and vendor contracts. Implement strict Content Security Policies (CSP).
* **Sprint 4 (Weeks 10-12):** Conduct a tabletop exercise simulating an ICE administrative subpoena. Finalize multilingual privacy UX communicating the "No Tracking" policy to users.

## References

1. *The Department of Homeland Security's “Protected Areas” ...*. https://www.nilc.org/wp-content/uploads/2021/11/Protected-Areas-Factsheet-2021-11-12.pdf
2. *Secretary Mayorkas Issues New Guidance for Enforcement Action at Protected Areas | Homeland Security*. https://www.dhs.gov/archive/news/2021/10/27/secretary-mayorkas-issues-new-guidance-enforcement-action-protected-areas
3. *Enforcement Actions in or Near Protected Areas*. https://www.dhs.gov/publication/enforcement-actions-or-near-protected-areas
4. *DHS Protected Areas FAQs - Border Security*. https://www.cbp.gov/border-security/dhs-protected-areas-faqs
5. *Understanding Confidentiality of Substance Use Disorder (SUD) Patient Records or “Part 2” | HHS.gov*. https://www.hhs.gov/hipaa/part-2/index.html
6. *ICE Administrative Subpoenas to Tech Companies for ...*. https://iptp-production.s3.amazonaws.com/media/documents/2022.08_Just_Futures_Law_-_ICE_Administrative_Subpoenas_to_Tech_Companies.pdf
7. *8 USC 1225: Inspection by immigration officers; expedited ...*. https://uscode.house.gov/view.xhtml?req=(title:8%20section:1225%20edition:prelim)
8. *Know Your Rights: Immigration Administrative Subpoenas*. https://assets.aclu.org/live/uploads/2025/04/ACLU-KYR-on-ICE-administrative-subpoenas-4.17.25.pdf
9. *Overview of Governmental Action Under the Stored Communications Act (SCA) | Congress.gov | Library of Congress*. https://www.congress.gov/crs-product/LSB10801
10. *COMPLIANCE GUIDE FOR LAW ENFORCEMENT*. https://www.eff.org/files/filenode/social_network/yahoo_sn_leg-doj.pdf
11. *
      Federal Register
       :: 
      Confidentiality of Substance Use Disorder (SUD) Patient Records
    *. https://www.federalregister.gov/documents/2024/02/16/2024-02544/confidentiality-of-substance-use-disorder-sud-patient-records
12. *Fact Sheet 42 CFR Part 2 Final Rule | HHS.gov*. https://www.hhs.gov/hipaa/for-professionals/regulatory-initiatives/fact-sheet-42-cfr-part-2-final-rule/index.html