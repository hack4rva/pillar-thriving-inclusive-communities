# Weekend-to-Impact: Proven Hackathon Patterns for Immigrant Service Tools

## Executive Summary
Civic hackathons frequently produce prototypes that stall after demo day, but a subset of projects built for immigrant and refugee communities have achieved lasting national and local impact. The evidence reveals that successful weekend projects share a common DNA: they launch on platforms users already trust (like WhatsApp or Facebook Messenger), they structure their data using open standards like the Human Services Data Specification (HSDS), and most importantly, they secure a dedicated data steward before the coding even stops. 

For a team in Richmond looking to build an immigrant service navigation tool in 48 hours, the mandate is clear: do not build a custom database from scratch. Instead, fork existing open-source frontends (like Link-SF or Ohana Web Search), power them with a simple JSON file hosted on GitHub, and focus the weekend's energy on mapping local resources and integrating the tool into the existing workflows of local clinics and resettlement agencies. The single most important factor in whether a hackathon project survives is not the technology stack, but the presence of a named community organization that takes ownership of keeping the data accurate after the event.

## Why this matters for Richmond — Deliver value in 48 hours by borrowing what works
Weekend wins come from reusing open standards, riding existing channels, and securing a local data steward before the demo. By examining the history of civic tech projects, Richmond can bypass the common pitfalls of "app graveyard" prototypes.

### Richmond’s immediate opportunity: meet immigrants where they already are
Build for platforms with existing network effects and mobile-first constraints. Vulnerable populations often rely on smartphones and specific messaging apps. Launching a lightweight mobile web app or a messaging bot allows immediate access without the friction of app store downloads.

## Evidence scan: weekend-to-impact case studies with adoption patterns
Tools that align with standards and partners outlast weekend prototypes. The following case studies demonstrate the trajectory from hackathon pitch to sustained adoption.

### Tarjimly’s rapid scale via Messenger, then compliance-grade app
Tarjimly was "hacked together" by MIT and Stanford graduates in late January 2017 in direct response to the U.S. Muslim Ban and the Syrian refugee crisis [1] [2] [3]. By launching as a Facebook Messenger bot, they met refugees and aid workers on a platform they already used, gaining 4,000 sign-ups on day one [1] [3]. They quickly recruited over 2,200 volunteer translators and partnered with more than 15 organizations [1]. Eventually, to meet data security (HIPAA) and scalability needs, they evolved into a dedicated mobile app [3]. 

### Link-SF’s hack-day HSDS conversion and sustained city partnership
Link-SF is a mobile-first web app connecting people to services like food and shelter, built as a collaboration between Zendesk and the St. Anthony Foundation’s Tenderloin Technology Lab [4] [5]. During a social good hack day, a team of developers successfully "forward engineered" Link-SF's data to comply with the Open Referral Human Services Data Specification (HSDS) in just a few hours (2:30 PM to 8:30 PM) [6]. They converted the dataset to a single JSON file hosted on GitHub, decoupling the backend from the frontend and making the app easily deployable by other cities [6].

### ShelterTech’s SF Service Guide: volunteer roots to 10k+ MAU
ShelterTech is a volunteer-led non-profit that launched the SF Service Guide in 2019 [7]. It has grown to serve over 10,000 monthly users, maintaining a directory of over 1,800 services and 500 organizations [7]. Their success stems from working directly with government and non-profit partners to keep the guide accurate [7].

### Streetlives NYC: HSDS + co-design with lived experience
Streetlives NYC built a platform for homeless individuals to find and rate social services [8]. They ran extensive human-centered design sessions with over 50 people with lived experience of homelessness, discovering that their community's information needs mapped perfectly onto Open Referral’s HSDS data model [8]. 

### YMCA Oasis (Hack4Impact UIUC): multilingual pilot through existing programs
The New American Welcome Center at the University YMCA partnered with student group Hack4Impact to build "Oasis," a virtual resource hub for immigrants [9]. The tool features multi-language support (Spanish, Chinese, French) and was piloted directly through existing channels like "La Linea," YMCA legal clinics, and public office hours [9].

### Cautionary: Bureaucrazy’s hurdles despite press and prizes
A team of Syrian refugees in Berlin developed "Bureaucrazy" at a ReDI School hackathon to help newcomers navigate German bureaucracy [10] [11]. Despite winning first place at a hackathon and receiving massive international press coverage, the project faced significant hurdles [12] [11]. They struggled with data privacy concerns (storing auto-fill data in privacy-conscious Germany), translation accuracy (relying on Yandex for complex German compound nouns), and basic funding logistics (developers couldn't open bank accounts without risking their job center benefits) [10].

## Technical patterns that ship in a weekend for immigrant navigation
Choose low-devops, HSDS-aligned approaches; decouple content from UI.

| Pattern | Example(s) | Build time/complexity | Data source | Strengths | Risks/When to avoid |
|---|---|---|---|---|---|
| Messaging bot on existing platforms | Tarjimly on FB Messenger (2017) [1] | Hours to days | Minimal; match requests | Instant reach; no install; network effects | Platform limits; privacy; hard to localize complex content |
| JSON-backed React SPA | Link-SF + GitHub JSON (HSDS) [5] [6] | 1 day to fork/point | GitHub raw JSON (HSDS-aligned) | No server; quick search/filter UX; easy theming | Needs a data steward; offline search limited |
| Rails API + turnkey search UI | Ohana API + Ohana Web Search [13] [14] | 1–2 days with experienced devops | HSDS-like admin + API | Admin UI included; multi-channel (web, SMS) | Higher ops burden for a weekend |
| Static site (Jekyll) | Food Oasis LA [15] | Hours | CSV/JSON baked into build | Easiest hosting; no backend | Limited interactivity/admin |

The table above illustrates that static sites and JSON-backed single-page applications offer the best balance of speed and maintainability for a weekend hackathon.

## What’s specifically worked for service directories/navigation
HSDS + lightweight backends + mobile-first UIs are the repeatable recipe.

### Proven components to reuse
You can stand up a credible MVP in 48 hours by forking and configuring existing open-source projects. Code for America's Ohana API provides a robust Ruby on Rails backend and a separate web search interface [13] [14]. Alternatively, the Link-SF project offers a React.js frontend that can query a static JSON file hosted on GitHub, entirely removing the need for a traditional database backend [5] [6].

### Features that matter at launch
Keep it narrow but useful. Successful tools focus on critical details like hours of operation, phone numbers, and required documents [5] [9]. Filtering by category, cost, and languages spoken is essential, as demonstrated by the YMCA Oasis project [9].

## Post-hackathon adoption patterns and playbook
Adoption follows stewardship, workflows, and standards.

### Who tends to own it after the weekend
City agencies or nonprofits with daily client contact sustain directories. For example, the Ohana API was developed in partnership with San Mateo County's Human Services Agency [13]. Link-SF is an ongoing collaboration with the Tenderloin Technology Lab [5].

### How it gets used
Embedded in existing channels, not via app store discovery. Tools gain traction when they are used by case workers, integrated into hotline scripts (like YMCA Oasis), or utilized at clinic intake desks [9].

### Governance checklist (do this during the hackathon)
Governance beats gold-plating. The single most important factor in whether a hackathon project has lasting impact is establishing a durable data owner. Projects must name a data steward, establish an update cadence, and ensure no Personally Identifiable Information (PII) is collected in the MVP phase.

## Borrow vs. build for Richmond
Borrow the stack and schema; build the local data and relationships.

| Decision | Borrow (existing) | Build (local) | Rationale |
|---|---|---|---|
| Data model | HSDS (Open Referral) [16] | HSDS field selection matching Richmond use-cases | Interoperability + user alignment |
| Front-end | Fork Link-SF or Ohana Web Search [14] [5] | Branding, language pack, local taxonomy mapping | Ship fast; tailor UX to community |
| Backend | GitHub JSON or Ohana API [13] [6] | Lightweight ETL to generate HSDS JSON from partner spreadsheets | Weekend viability; scalable later |
| Channel | WhatsApp/SMS intake scripts; mobile web | Partner onboarding, QR posters, clinic tablet flows | Meet users where they are |
| Data stewardship | — | Assign anchor org + update budget | Most critical success factor |

Richmond teams should leverage the Open Referral HSDS standard to ensure their data can be shared and reused [16]. 

### 48-hour build plan
A credible MVP is feasible in 2 days with the right constraints.
* **Day 0:** Secure anchor org; pick top 50 services via partners.
* **Day 1:** Map to HSDS; publish JSON (GitHub raw); fork Link-SF.
* **Day 2:** Walkthrough with clinic staff; refine filters; demo with signed stewardship MOU.

## Risks, constraints, and mitigations
Avoid PII; constrain scope; set update cadence. Privacy and data risks can stall promising ideas if ignored. Tarjimly had to evolve from a simple bot to a HIPAA-compliant app to handle sensitive situations [3]. Bureaucrazy faced significant hurdles regarding data privacy and the storage of user information [10]. For Richmond, the MVP must avoid collecting PII entirely.

## Metrics and 30/60/90-day path to durable impact
Measure usage in partner workflows and commit to maintenance.
* **30 days:** Achieve usage via partner channels (e.g., 2 clinics adopting the tool).
* **60 days:** Expand the HSDS dataset and train partner organization editors.
* **90 days:** Formalize funding for ongoing data updates and stewardship.

## Appendices — reusable components and exemplar links
Everything here is open-source or publicly documented.
* **Tarjimly:** Facebook Messenger bot origins [1] [2].
* **Ohana API:** Code for America open-source directory [13] [14].
* **Link-SF:** React frontend and HSDS JSON backend [5] [6].
* **Food Oasis LA:** Hack for LA static site [15].
* **ShelterTech:** SF Service Guide [7].
* **Bureaucrazy:** ReDI school hackathon project [10] [11].

## References

1. *How Three Millennial Entrepreneurs Created A Messenger Bot To Help Refugees*. https://www.forbes.com/sites/toriutley/2017/06/20/how-three-millennial-entrepreneurs-created-a-messenger-bot-to-help-refugees/
2. *Hackathon Hackers | Some of my MIT friends and I hacked together this project in light of the #MuslimBan and refugee crisis - a Messenger bot that connects volunteer tran... | Facebook*. https://www.facebook.com/groups/hackathonhackers/posts/1490467647675382/
3. *About Tarjimly*. https://www.tarjimly.org/about/our-purpose
4. *Link-SF gets a much-needed update*. https://www.zendesk.com/blog/link-sf-gets-much-needed-update/
5. *GitHub - zendesk/linksf: A mobile website to connect those in need in to services that can help them · GitHub*. https://github.com/zendesk/linksf
6. *A Hack Day Event To Help The Link-SF App Speak Human Services Data Specification (HSDS)
    *. https://apievangelist.com/2017/08/11/a-hack-day-event-to-help-the-link-sf-app-speak-human-services-data-specification/
7. *Sheltertech | Find social services and free wifi in San Francisco*. https://www.sheltertech.org/
8. *Streetlives NYC: designing with our users – Open Referral*. https://openreferral.org/streetlives-nyc-designing-with-our-users/
9. *YMCA Oasis | Hack4Impact UIUC*. https://uiuc.hack4impact.org/projects/ymca-oasis
10. *Syrian refugees design app for navigating German bureaucracy | Germany | The Guardian*. https://www.theguardian.com/world/2016/aug/05/syrian-refugees-app-navigating-german-bureacracy-bureaucrazy
11. *Refugees solve German bureaucracy with new app*. https://www.dw.com/en/refugees-solve-german-bureaucracy-with-new-app/a-19463744
12. *A Reflection on Spacehack: The Refugee Journey | by Travis J. Todd | Silicon Allee | Medium*. https://medium.com/silicon-allee/a-reflection-on-spacehack-the-refugee-journey-89ae22e9db7b
13. *GitHub - codeforamerica/ohana-api: The open source API directory of community social services. · GitHub*. https://github.com/codeforamerica/ohana-api
14. *GitHub - codeforamerica/ohana-web-search: A mobile-friendly website for finding human and social services in your community · GitHub*. https://github.com/codeforamerica/ohana-web-search
15. *GitHub - hackforla/food-oasis-la: This is a website with a map of food sources in Los Angeles, and list of resources about food deserts and health, published with Jekyll and GitHub Pages. · GitHub*. https://github.com/hackforla/food-oasis-la
16. *Our History – Open Referral*. https://openreferral.org/about/history/