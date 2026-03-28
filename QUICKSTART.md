> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](docs/methodology.md) for details.

# Quickstart

## Fastest path for teams
1. Read `00_core/00_pillar_overview.md`
2. Read `01_problem_space/02_targeted_problem_statements.md`
3. Read `02_data/00_index.md`
4. Pick one user and one problem
5. Read `04_build_guides/01_mvp_shapes.md`
6. Create your project brief using `99_templates/project_one_pager_template.md`

## Questions to answer before building
- Who is the user (immigrant resident, refugee, case manager, community org staff)?
- What problem are they facing?
- What data or documents are you using?
- What can actually be built in a weekend?
- How will a judge understand the value in under 60–90 seconds?
- **What privacy risks does your idea introduce, and how are you mitigating them?**

## High-probability project types
- multilingual service finder (public data, no login required)
- privacy-first help connector (anonymous browsing, plain language, no PII)
- Help1RVA interface improvement (simpler navigation, voice-friendly, multilingual)
- trusted community messenger tool (WhatsApp/SMS pipeline for service info through ambassadors)
- case manager coordination helper (referral workflow for nonprofit staff)
- cross-agency service pathway map (visual explainer of who serves whom)

## The defining constraint for this pillar
**Privacy and trust are not secondary concerns — they are the product.**

Immigrant and refugee residents may avoid services entirely if they fear data exposure. Any tool that collects, stores, or transmits personal information must be designed with this in mind from the start — not bolted on afterward.

Privacy-first design principles:
- No login required for residents
- No collection of name, address, immigration status, or household information
- No retention of search or browsing history
- Prefer aggregated, anonymized views over individual profiles
- Be explicit about what the tool does and does not store

## What to avoid
- Tools requiring residents to create accounts with personal information
- Eligibility determination features
- Integration with internal agency databases (HIPAA and policy walls apply)
- Tools that could create false confidence about privacy or safety
- Replacing human case managers or community trust relationships
