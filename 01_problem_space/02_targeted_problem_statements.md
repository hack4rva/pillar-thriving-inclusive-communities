# Targeted Problem Statements - Thriving and Inclusive Communities

## 1) Help Residents Safely Discover and Connect to Trusted Support Services

Score: 24/32 — Strong

### Problem statement
While Richmond has a growing network of City programs, nonprofits, and community-based organizations that provide support to immigrant and refugee residents, many residents struggle to safely discover and connect to these services. Concerns about privacy, language barriers, and uncertainty about which organizations can be trusted often prevent residents from seeking help.

### Context
Support services for immigrant and refugee communities exist across many organizations and communication channels, but information about these services is fragmented and becomes outdated quickly. Residents may not know which services exist, how to access them, or whether engaging could expose personal information. Organizations providing support work in parallel without shared tools to coordinate communication or keep service information current.

Help1RVA (help1rva.com) currently connects Richmond residents to community services but requires manual data entry and navigation that creates friction. Service information across platforms (Help1RVA, FindHelp/Aunt Bertha, individual organization websites) is not synchronized. Information quality varies and updates lag.

### Constraints
- Must prioritize strong privacy protections and anonymity
- Must work with existing nonprofit and community-based support networks
- Cannot require a full replacement of current systems
- Should avoid collecting unnecessary personal data
- Must operate within limited staffing capacity and budgets
- Service information should be easily updated by trusted organizations
- Must not require residents to create accounts or provide identifying information

### Success would mean
- Residents can safely discover and connect to trusted support services
- Immigrant and refugee communities feel more comfortable seeking help
- Service information is accurate, multilingual, and easy to access
- Community organizations coordinate more effectively
- Fewer residents fall through gaps between support programs
- Tool can be updated without requiring significant technical expertise

### Gaps to close
- Help1RVA export or snapshot showing services relevant to immigrant and refugee residents (not currently public)
- List of trusted community organizations with languages served (partial — organizations known but not systematically documented)
- Documentation of which communication channels residents actually use (WhatsApp groups, SMS chains, Facebook, faith organization bulletins)
- Priority languages: Spanish, Arabic, Nepali, Burmese likely — but not formally specified in rubric materials
- Confirmation of which organizations are willing to serve as trusted information intermediaries

### Hackathon approach
This problem is the stronger starting point. The service discovery gap is well-documented, public service directory data exists (though export format is uncertain), and the user need is clear. A privacy-first service finder or multilingual resource tool is directly buildable.

---

## 2) Helping Residents Navigate the Right Support Services Without Repeating Their Story

Score: 22/32 — Needs work (D3=1 — critical data gap)

### Problem statement
Residents seeking housing stability, workforce support, or reentry services often need assistance from multiple City departments and partner organizations. However, information about programs is spread across different agencies, eligibility requirements are complex, and residents frequently have to repeat their story to multiple providers.

### Context
Residents navigating housing, workforce development, or reentry services interact with multiple organizations: Social Services, Housing, workforce programs, and nonprofit partners. These programs operate independently on different systems. Residents must determine eligibility on their own and contact multiple offices before finding the right support. Each touchpoint may require re-explaining the same circumstances — which is exhausting and can be retraumatizing for vulnerable individuals.

The current ecosystem includes:
- City of Richmond Department of Social Services
- City of Richmond Department of Housing and Community Development
- Workforce development programs (YMCA, community colleges, workforce boards)
- Nonprofit partners (ReEstablish Richmond, NCS, others)
- Help1RVA as the referral backbone — but with manual, siloed intake processes
- FindHelp/Aunt Bertha and UniteUs as supplementary tools used by some organizations — but not interoperable with each other or with Help1RVA

### Constraints
- Must respect privacy protections including HIPAA and PII rules
- Must work across departments operating on different systems
- Cannot require a full technology overhaul
- Should support — not replace — human case managers and volunteers
- Must function within existing staffing capacity
- Cross-agency data sharing is severely limited by policy and legal constraints

### Success would mean
- Residents can quickly identify relevant services and eligibility requirements
- Residents do not have to repeat their story across agencies
- More residents successfully connect to housing, workforce, or reentry support
- Staff spend less time redirecting residents between programs
- Organizations coordinate more effectively across service pathways

### Gaps to close (CRITICAL — D3=1)
- No mock or anonymized intake dataset showing cross-agency referral structure exists
- No service directory export from Help1RVA, FindHelp, or UniteUs is publicly available
- No process map showing how a resident moves between Social Services, Housing, workforce programs, and nonprofits
- Cross-agency referral pathway has not been mapped at all
- HIPAA and organizational data-sharing agreements are unknown

### Hackathon approach
This problem has the highest real-world impact but the most severe data constraints. D3=1 means no cross-agency dataset exists. Teams building toward this problem must:
1. Work with public information only (no intake data, no cross-agency records)
2. Focus on the staff-facing or map-facing layer — not a resident-data tool
3. Consider building a pathway visualization tool using publicly available service descriptions
4. Accept that the demo will be conceptual rather than data-driven for the cross-agency elements

See `04_build_guides/01_mvp_shapes.md` Shape D and E for relevant approaches.
