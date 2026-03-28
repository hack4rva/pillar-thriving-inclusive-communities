> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Pillar Overview - Thriving and Inclusive Communities

## Purpose
This repository is a markdown knowledge base for teams working on the Thriving and Inclusive Communities pillar in the Richmond Civic Hackathon. It helps teams understand the problem space, review problem statements, explore public data, and shape realistic weekend MVPs.

## Pillar framing
Thriving and Inclusive Communities focuses on helping immigrant and refugee residents in Richmond safely access the services and support they need, including:
- safe discovery of and connection to trusted support services
- multilingual and accessible information delivery
- cross-agency navigation without repeating one's story
- trust-based outreach through community ambassadors and organizations
- reducing friction between residents and the Help1RVA / FindHelp ecosystem
- supporting case managers and nonprofits with coordination tools

## Why this matters
Access to services depends on trust, language, and navigation:
- Immigrant and refugee residents face language barriers, digital literacy gaps, and deep fear of sharing personal information
- Services exist — the gap is not supply but safe, accessible, navigable delivery
- Fragmentation between Help1RVA, FindHelp/Aunt Bertha, and UniteUs means even case managers struggle to connect residents to the right help
- When residents fall through the gaps, consequences are serious: lost housing, missed health care, no workforce pathway

## Useful prototype directions
Prototypes that often help in this pillar:
- make service information easier to find without requiring personal information
- present resources in multiple languages with simple, clear navigation
- help case managers coordinate referrals across organizations
- distribute service information through trusted community channels (WhatsApp, SMS, faith organizations)
- reveal where the service gaps and navigation friction points actually are

## Less useful directions
Prototypes that tend to struggle in a weekend:
- require integration with HIPAA-protected agency systems
- require collection of immigration status, PII, or health information
- claim to make eligibility determinations
- depend on cross-agency data that does not exist or is not shareable
- try to replace the human trust relationships that vulnerable residents depend on

## The trust constraint
For this pillar, trust is not a feature — it is the foundation. Immigrant and refugee residents will not use a service discovery tool if they fear it exposes them. Every design decision must ask: "Does this protect the person using it?"

Privacy-by-design principles for this pillar:
- No login required to browse services
- No collection of name, address, immigration status, or household composition
- No retention of search history tied to individuals
- Transparent disclosure of what the tool does and does not store
- Prefer aggregated service directory views over personalized profiles
