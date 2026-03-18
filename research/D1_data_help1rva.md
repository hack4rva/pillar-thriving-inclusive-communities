---
title: "Help1RVA Data, Fast: A 2–3 Hour Path to a Reliable Immigrant/Refugee Services Dataset"
pillar: thriving-inclusive-communities
section: D
problem_statement: immigrant-service-access
tags:
  - Help1RVA data
  - no API
  - manual extraction
  - service categories
  - data sprint
  - findhelp TOS
summary: "Documents that Help1RVA has no public API or bulk data export and recommends a targeted manual extraction sprint as the legally safe path to a curated immigrant/refugee services dataset in 2–3 hours."
geography: Richmond, VA
source: perplexity-sonar-deep-research
status: raw
privacy_sensitivity: high
related_reports:
  - C1_services_help1rva
  - D2_data_community_org_directories
  - D5_data_quality_gaps
---

# Help1RVA Data, Fast: A 2–3 Hour Path to a Reliable Immigrant/Refugee Services Dataset

## Executive Summary
Help1RVA operates as a white-labeled instance of the findhelp platform, meaning it relies on findhelp's underlying infrastructure and data model [1] [2]. There is no publicly documented API or bulk data export available for Help1RVA or findhelp.org. However, the platform offers a rich, highly structured dataset for individual programs. For a hackathon team needing 20–30 curated immigrant and refugee services in Richmond, the most viable and legally safe path is a targeted, manual extraction sprint. By focusing on "Claimed" programs within specific categories (Citizenship & Immigration, Translation & Interpretation, ESL) and verifying details against official provider websites, a team can build a high-quality, verified JSON/CSV dataset in under three hours.

## Platform Reality and Access Limits
Help1RVA does not expose developer tools, public APIs, or bulk CSV/JSON export functions. 

**Facts:**
* Help1RVA is powered by findhelp, as evidenced by its accessibility and support links directing to findhelp.com and findhelp.org [1] [3].
* The site navigation only exposes user-facing tools like "Suggest Program," "Claim Programs," "Accessibility," "Terms," and "Privacy" [1] [4].
* The "Suggest Program" page explicitly directs users looking for help to findhelp.org [4].

**Inferences:**
* *Inference:* Because Help1RVA is a closed, proprietary directory managed by findhelp, automated scraping is likely restricted by their Terms of Service, and no hidden API endpoints are intended for public developer use. 
* *Inference:* A hackathon team must rely on manual data entry for their initial prototype to avoid IP blocks or legal friction.

## Data Landscape for Immigrant/Refugee Services
There is sufficient category depth on the platform to easily curate a 20–30 organization list focused on immigrant and refugee needs in the Richmond area.

**Facts:**
* A search for services in the Richmond 23223 ZIP code reveals 16 programs under "Citizenship & Immigration," 14 under "Translation & Interpretation," and 9 under "English As A Second Language (Esl)" [5].
* Key local providers are actively listed, including the International Rescue Committee (IRC) - Richmond and Commonwealth Catholic Charities (CCC) [5] [6] [7].

**Inferences:**
* *Inference:* The overlap between these categories means a team can quickly review about 40 total listings to select the 20–30 highest-quality, most relevant local programs.

## Structured Fields and Data Model
While there is no API, the findhelp program detail pages expose a highly structured data model that a hackathon team can easily map to a relational database or flat CSV.

**Facts:**
Program pages display the following explicit fields:
* **Provider Name & Program Name:** e.g., "Refugee Services by International Rescue Committee (IRC) - Richmond" [6].
* **Claim Status & Last Reviewed Date:** e.g., "Claimed Program" and "Reviewed on: 02/24/2026" [6].
* **Description & Services Offered:** Bulleted lists of specific services (e.g., English language classes, health care, housing placement) [6] [7].
* **Eligibility:** Specific intake requirements (e.g., "Must be a refugee") [6].
* **Languages:** e.g., "English, Spanish" [7].
* **Cost:** e.g., "Reduced Cost" [6].
* **Next Steps:** Contact methods (Phone, Email, Website links) [6].
* **Locations & Hours:** Specific addresses, distances, and daily operating hours [6] [7].
* **Coverage Area:** Specific cities or counties served [6] [7].

## Access Paths Compared
To determine the best approach for the hackathon, we must compare the available data acquisition methods.

| Data Source | Speed (Records/Hour) | Legal/TOS Risk | Field Depth | Data Freshness Signal |
| :--- | :--- | :--- | :--- | :--- |
| **Manual Capture (findhelp pages)** | 10–15 | Low (if volume is small) | High (12+ structured fields) | High ("Last Reviewed" timestamps) |
| **Automated Scraping** | 100+ | High (Likely violates TOS) | High | High |
| **Provider Official Websites** | 5–10 | None | Variable (often unstructured) | Unknown (rarely timestamped) |

**Key Takeaway:** Manual capture from findhelp pages offers the best balance of speed, data depth, and legal compliance for a 20–30 record dataset. Provider websites should be used strictly for secondary verification.

## Legal and Policy Considerations
Help1RVA and findhelp maintain strict control over their platform data. The site includes explicit "Terms" and "Privacy" links in its footer [1]. 

**Inferences:**
* *Inference:* Automated scraping of findhelp.org or help1rva.org carries a high risk of IP bans and violates standard directory terms of service. 
* *Action:* The hackathon team should limit their activity to manual extraction of the 20–30 required records. For future scaling, they should contact findhelp's compliance team (compliance@findhelp.com) to discuss authorized data sharing [1].

## Step-by-Step Data Acquisition Plan
To build the dataset within a 2–3 hour maximum timeframe, the hackathon team should execute the following sprint:

1. **Targeted Search (15 mins):** Navigate to findhelp.org, enter a central Richmond ZIP code (e.g., 23223 or 23227), and open the "Citizenship & Immigration," "Translation & Interpretation," and "ESL" categories [5].
2. **Triage and Selection (30 mins):** Filter for programs marked as "Claimed Program." Claimed programs, such as those by CCC and IRC, indicate that the organization actively maintains the listing [6] [7]. Prioritize listings with a "Last Reviewed" date within the last 6–12 months.
3. **Data Extraction (60 mins):** Divide the 30 target programs among team members. Manually copy the structured fields (Name, Description, Eligibility, Languages, Phone, Address, Hours, Coverage Area) into a shared Google Sheet.
4. **Verification (45 mins):** Click the "Program's Website" link provided in the findhelp listing [6]. Quickly verify that the phone number, address, and core services match the provider's official site.
5. **Export (15 mins):** Download the finalized Google Sheet as a CSV or JSON file for integration into the hackathon project.

## Data Quality Risks and How to Mitigate
While findhelp provides a strong baseline, directory data is inherently prone to decay. 

**Facts:**
* Some programs surface in local Richmond searches despite being located thousands of miles away, because they offer remote services (e.g., Tarjimly, which is 2452.26 miles away but "serves your state") [5].
* Programs may have multiple locations with different hours, such as CCC's Refugee Resettlement Program which lists offices in Richmond, Newport News, and Roanoke [7].

**Risks and Verification Steps:**
* **Geographic Noise:** *Risk:* Including national hotlines that lack local Richmond context. *Mitigation:* Explicitly filter for programs where the "Coverage Area" lists Richmond or surrounding counties, and prioritize those with physical local addresses [6].
* **Stale Contact Info:** *Risk:* Phone numbers and hours change frequently. *Mitigation:* Rely on the "Last Reviewed" date as a primary quality signal [6]. For any program reviewed more than a year ago, mandate a manual check against the provider's official website.
* **Language Capacity Accuracy:** *Risk:* Listed languages may reflect the platform's translation tools rather than on-staff interpreters. *Mitigation:* Check the provider's website for explicit mentions of bilingual staff or interpretation services.

## Output Format and Handoff
The team should structure their output as a flat JSON array or CSV to ensure easy consumption by their application. The schema should include: `id`, `provider_name`, `program_name`, `description`, `eligibility_notes`, `languages_array`, `phone`, `website`, `address`, `hours`, `coverage_area`, `claimed_status`, and `last_reviewed_date`.

## Beyond the Hackathon
If the project continues past the hackathon, manual extraction will not scale. The team should leverage the "Suggest Program" and "Claim Programs" features to contribute corrections back to the Help1RVA ecosystem [8] [4]. For programmatic access, they must establish a formal partnership with findhelp or local stakeholders like the YMCA of Greater Richmond, which actively utilizes the Help1RVA network [8].

## References

1. *
        Help1RVA Greater Richmond Resource Directory
            | Accessibility
    *. https://help1rva.org/legal/accessibility
2. *Claim Programs, Help1RVA Greater Richmond Resource Directory, findhelp*. https://help1rva.org/claims
3. *Help1RVA Greater Richmond Resource Directory*. https://help1rva.org/forms/help1rva-intake
4. *Suggest a Program*. https://help1rva.org/suggest-program
5. *translation & interpretation programs in Richmond, va | findhelp.org*. https://www.findhelp.org/legal/translation-%26-interpretation--richmond-va
6. *citizenship & immigration programs in Richmond, va | findhelp.org*. https://www.findhelp.org/legal/citizenship-&-immigration--richmond-va
7. *Refugee Resettlement Program - Commonwealth Catholic Charities (CCC) serving Richmond, VA | findhelp.org*. https://www.findhelp.org/commonwealth-catholic-charities-%28ccc%29--richmond-va-refugee-resettlement-program/4454021?postal=23227
8. *Social Needs Navigation - YMCA of Greater Richmond*. https://www.ymcarichmond.org/resources/help1rva/