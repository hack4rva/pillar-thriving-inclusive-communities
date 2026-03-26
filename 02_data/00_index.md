# Data Index - Thriving and Inclusive Communities

## Summary
This pillar faces significant data constraints. The most important data gap is the cross-agency referral pathway (D3=1). No cross-agency intake dataset exists. The service directory data that does exist (Help1RVA, FindHelp) is not publicly downloadable in a clean format.

**Key constraint**: Teams must build with public data only. No PII, no intake records, no immigration status data. This is both a legal requirement and an ethical baseline.

---

## Available Data Sources

### 1. Help1RVA Service Directory
- URL: https://help1rva.org (search example: https://help1rva.org/housing/help-find-housing--richmond-va?postal=23223)
- Description: Richmond's community resource directory connecting residents to nonprofit and City services; powered by the findhelp platform, stewarded locally by the YMCA of Greater Richmond
- Format: Web interface; no public API or bulk export — manual extraction recommended for hackathon use (see D1_data_help1rva.md for extraction guide)
- Access: Public browsing; no account required to search
- Key fields: Organization name, service type, address, phone, languages served, hours, eligibility, last reviewed date
- Limitations: No API; scraping likely violates TOS; manual extraction of 20–30 records is feasible in 2–3 hours
- Privacy note: Safe to use for building a service directory front-end
- Priority: High — this is the primary service data source for this pillar

### 2. FindHelp / Aunt Bertha
- URL: https://www.findhelp.org (or organization-specific subdomains)
- Description: National social care network used by many Richmond nonprofits; overlaps with Help1RVA
- Format: Web interface; API available but requires partnership/access
- Access: Public browsing for basic search; deeper API requires account
- Key fields: Program name, category, eligibility criteria, application instructions
- Limitations: Not interoperable with Help1RVA; some Richmond coverage gaps
- Privacy note: Safe for service directory browsing; API use may require terms review
- Priority: Medium — useful as supplementary service data

### 3. Virginia 211
- URL: https://search.211virginia.org/
- Description: Statewide helpline and online service directory; covers Richmond area; recommended by OIRE as a comparison platform alongside Help1RVA
- Format: Web search; some exportable data through the national 211 network
- Access: Public
- Key fields: Service categories, provider names, contact information, geographic coverage
- Limitations: Richmond-specific coverage may be thinner than Help1RVA
- Priority: Medium — good for cross-checking service coverage

### 4. US Census / American Community Survey (ACS) — Immigrant Population Data
- URL: https://data.census.gov
- Description: Population estimates including nativity, language spoken at home, citizenship status
- Format: CSV download, API available
- Key fields: Foreign-born population, language spoken at home, English proficiency, year of entry
- Geographic level: Available at census tract, zip code, city, metro area
- Limitations: 5-year estimates; not current; does not show individual-level data
- Privacy note: Aggregate data only — no individual identification possible
- Priority: High for contextualizing the population and language access problem

### 5. Virginia Refugee Resettlement Data
- Source: Virginia Department of Social Services / Office of New Americans
- URL: https://www.dss.virginia.gov/community/oan.cgi (Office of New Americans)
- Description: State-level data on refugee arrivals, resettlement locations, and program participation
- Format: Reports and PDFs; structured data export uncertain
- Limitations: State aggregate; Richmond-specific numbers may require direct request
- Priority: Medium — useful for scoping the population size

### 6. City of Richmond Open Data Portal
- URL: https://data.richmondgov.com (verify current URL)
- Description: City datasets including demographics, social services information, geographic data
- Format: CSV, GeoJSON
- Key fields: Varies by dataset
- Limitations: Social services / human services section may be limited or absent
- Priority: Medium — check for any relevant datasets on service locations or demographics

### 7. GRTC Transit Routes and Stops
- URL: https://ridegrtc.com or GTFS feed
- Description: Bus route data relevant to understanding transit access to service locations
- Format: GTFS (transit-standard format), web maps
- Key fields: Route lines, stop locations, frequency
- Privacy note: Public infrastructure data — no privacy concerns
- Priority: Low-medium — relevant if building a service access map with transit overlay

### 8. Trusted Community Organization Directory (OIRE-Verified)
- Source: Karla Almendarez-Ramos, Manager, Office of Immigrant and Refugee Engagement (OIRE), City of Richmond NCS — provided 2026-03-26
- Description: OIRE-verified list of 15 trusted intermediary organizations serving immigrant and refugee residents in Richmond, including refugee resettlement agencies, cultural associations, and community nonprofits. Also includes a multicultural church map and confirmed communication channel usage patterns.
- Format: See research/D2_data_community_org_directories.md for full list; multicultural church map available at https://www.google.com/maps/d/u/0/viewer?mid=1tjvSZB1TouFEa2gXxpd7f1Uv-N4
- Priority: High — use as the authoritative starting list for trusted messenger and community connector tools
- Note: This gap is now filled. Teams no longer need to compile this from scratch.

---

## Critical Missing Data

| Gap | Impact | Notes |
|-----|--------|-------|
| Cross-agency referral pathway map | Blocks Statement 2 entirely | No dataset exists; must conceptualize without data |
| Help1RVA structured export | Limits service directory tools | No API; manual extraction of 20–30 records feasible (see D1_data_help1rva.md) |
| Priority languages served by organization | Limits multilingual features | Spanish, Arabic, Dari, Pashto, Portuguese — confirmed by VDH/Bon Secours data |
| Communication channel usage patterns | ~~Gap closed~~ | **Confirmed by OIRE (2026-03-26):** Facebook (primary), WhatsApp, Instagram (younger), YouTube, in-person networks, local radio |
| Trusted community org list | ~~Gap closed~~ | **Filled by OIRE (2026-03-26):** 15 verified orgs in D2_data_community_org_directories.md |
| Anonymized intake data showing resident journeys | Blocks data-driven navigation tool | HIPAA wall; not available for hackathon |

---

## Data Access Guidance

For all data sources:
- Do not collect or store any personal information from tool users
- Do not attempt to access internal agency systems
- Use public-facing APIs and export tools only
- When data quality is uncertain, label outputs as "pending verification" rather than presenting as authoritative
- Prefer aggregated, directory-style data over case-level data
