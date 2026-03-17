# Data Index - Thriving and Inclusive Communities

## Summary
This pillar faces significant data constraints. The most important data gap is the cross-agency referral pathway (D3=1). No cross-agency intake dataset exists. The service directory data that does exist (Help1RVA, FindHelp) is not publicly downloadable in a clean format.

**Key constraint**: Teams must build with public data only. No PII, no intake records, no immigration status data. This is both a legal requirement and an ethical baseline.

---

## Available Data Sources

### 1. Help1RVA Service Directory
- URL: https://help1rva.com
- Description: Richmond's community resource directory connecting residents to nonprofit and City services
- Format: Web interface; API or export availability unclear — needs verification
- Access: Public browsing; no account required to search
- Key fields: Organization name, service type, address, phone, languages served, hours
- Limitations: Manual data entry; information quality varies; not always current
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
- URL: https://www.211virginia.org
- Description: Statewide helpline and online service directory; covers Richmond area
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

### 8. Community Organization Directories (Manual Compilation Needed)
- Sources: Individual organization websites, United Way Richmond partner directory, Richmond Community Foundation grantee list
- Description: No single authoritative directory of trusted community organizations serving immigrant and refugee residents exists — this must be manually compiled
- Format: Would require team-created spreadsheet or YAML
- Priority: High for any trusted messenger or community connector tool
- Note: This is a known gap identified in the rubric materials

---

## Critical Missing Data

| Gap | Impact | Notes |
|-----|--------|-------|
| Cross-agency referral pathway map | Blocks Statement 2 entirely | No dataset exists; must conceptualize without data |
| Help1RVA structured export | Limits service directory tools | May require manual scraping or API negotiation |
| Priority languages served by organization | Limits multilingual features | Anecdotally: Spanish, Arabic, Nepali, Burmese |
| Communication channel usage patterns | Limits messenger tool design | WhatsApp likely dominant but unverified |
| Anonymized intake data showing resident journeys | Blocks data-driven navigation tool | HIPAA wall; not available for hackathon |

---

## Data Access Guidance

For all data sources:
- Do not collect or store any personal information from tool users
- Do not attempt to access internal agency systems
- Use public-facing APIs and export tools only
- When data quality is uncertain, label outputs as "pending verification" rather than presenting as authoritative
- Prefer aggregated, directory-style data over case-level data
