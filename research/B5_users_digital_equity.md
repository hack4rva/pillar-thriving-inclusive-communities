> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Designing for Richmond's Newcomers: Mobile-first, WhatsApp-led services that reduce literacy and affordability barriers

## Executive Summary
For civic tech teams building services for recently arrived immigrant and refugee populations in Richmond, Virginia, the digital landscape is defined by smartphone dependence, affordability barriers, and varying digital literacy levels. With the end of the Affordable Connectivity Program (ACP) [1], low-income households face renewed connectivity instability. In Richmond, while broadband infrastructure is widely available, adoption lags significantly in lower-income and immigrant-heavy neighborhoods like Southwood [2] [3]. 

To succeed, digital services must bypass traditional web-based forms that heavily tax low-literacy users. Instead, teams should prioritize mobile-first, data-light, and messaging-led platforms—specifically WhatsApp, which is already dominant in many users' countries of origin [4]. Simplifying language to a 6th-grade reading level and using linear, one-step-at-a-time interactions can nearly double task success rates [5].

## Why this report now — Price shocks and phone-only use are reshaping access
The sunsetting of the FCC's Affordable Connectivity Program (ACP) has removed a critical stabilizer for low-income households [1]. Over two-thirds of ACP households reported inconsistent or zero connectivity prior to their enrollment [1]. In Virginia, while over 1 million households were eligible, only about 40% had enrolled by late 2023 [6]. This indicates that in 2026, civic tech teams must design for users who may experience intermittent data access, relying heavily on public Wi-Fi or limited mobile data caps.

### Richmond and Virginia context — Coverage exists; adoption lags
In Richmond, the primary barrier to digital equity is not infrastructure, but adoption and affordability. 

* **Fact:** Approximately 9.7% of Richmond residents do not have an internet subscription [2].
* **Fact:** Comcast asserts that there is 100% access to broadband services throughout the city, pointing to a lack of adoption and awareness of discount programs as the core issue [2].
* **Inference:** Interventions in Richmond should not focus on building new networks, but rather on creating highly accessible, low-bandwidth touchpoints that work on mobile devices, paired with on-the-ground digital navigator support to help families enroll in remaining discount programs like Lifeline [2].

## Devices and connectivity reality — Assume Android-heavy, phone-primary, variable data
Device ownership among low-income and immigrant populations skews heavily toward smartphones as the primary or sole internet connection. 

* **Fact:** Only 54% of U.S. adults in households making under $30,000 a year subscribe to home broadband, compared to 94% of those in the highest-income households [7].
* **Fact:** About a third of adults in households earning less than $30,000 annually are "smartphone dependent" (owning a smartphone but lacking home broadband), compared to just 4% of high-income adults [7]. Hispanic adults and young adults are also more likely to rely solely on smartphones [7].
* **Inference:** Civic tech solutions must be designed assuming the user is on a mobile device, likely an Android (given global market share trends in middle-income countries), without the benefit of a desktop computer or stable home Wi-Fi.

### Prepaid vs postpaid nuance — Don't design for one plan archetype
There is a common industry narrative that immigrants exclusively use prepaid phone plans. However, recent data complicates this.

* **Fact:** From 2018 to 2024, immigration was the largest driver of wireless phone net additions in the U.S., accounting for nearly 44% of total additions (approx. 22.3 million) [8].
* **Fact:** During this same period, total prepaid phone connections declined by nearly 5 million, while postpaid net additions exceeded 56 million, indicating that a massive influx of immigrants was largely absorbed by the postpaid market [8].
* **Fact:** Conversely, T-Mobile, which has the highest share of prepaid customers (25.2 million at the end of 2024), is still considered highly exposed to immigration policy shifts because prepaid service remains more affordable and accessible (no credit check) for many lower-income immigrants [9].
* **Inference:** Teams should build onboarding flows that accommodate both prepaid and postpaid realities. This means avoiding strict identity verification tied to credit checks (SSNs) and supporting easy account recovery if a user's prepaid phone number changes.

### Affordability landscape post-ACP — Expect churn, pauses, and hotspot reliance
With the ACP ending, users will likely face data caps and service interruptions. 
* **Inference:** Applications must be data-light. Avoid auto-playing videos, heavy image payloads, and complex client-side rendering that drains limited data plans.

## Channels that work — WhatsApp first, SMS second, web as lightweight fallback
For recent arrivals, the choice of delivery channel dictates whether a service will be used. Messaging apps, particularly WhatsApp, offer a familiar, low-friction environment compared to traditional web browsers.

### Channel comparison for immigrant/refugee users
The following table evaluates delivery channels based on the specific needs of low-literacy, data-constrained populations.

| Channel | Literacy Load | Data Usage | Trust & Security | Setup Friction | Best Uses |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **WhatsApp** | Low (supports voice notes, buttons, images) | Low to Medium (media can be compressed) | High (End-to-end encrypted) | Very Low (if already installed) | Guided onboarding, document submission, multilingual support, notifications. |
| **SMS** | Medium (text-heavy, requires reading/typing) | Very Low | Low (Unencrypted, prone to spam/scams) | Zero (native to all phones) | Urgent alerts, simple reminders, fallback links. |
| **Web Browser** | High (requires typing URLs, navigating menus, scrolling) | High (loads full page assets) | Medium (HTTPS, but phishing fears exist) | High (requires leaving the messaging context) | Deep informational reading, complex multi-step applications (if unavoidable). |

**Takeaway:** WhatsApp provides the best balance of low literacy requirements (via audio and visual aids) and high trust, making it the optimal primary channel.

### WhatsApp availability signal from origin countries
* **Fact:** In eight middle-income countries surveyed in 2023, WhatsApp and Facebook dominated the social media landscape [4].
* **Inference:** Because many immigrants and refugees arrive from middle-income nations where WhatsApp is the default communication infrastructure, they already possess the "muscle memory" to use it. Leveraging WhatsApp eliminates the need to teach users a new interface.

## Digital literacy in practice — Where users get stuck and what works
Lower-literacy users interact with digital interfaces fundamentally differently than higher-literacy users. They do not scan text; they "plow" through it word-by-word, resulting in a narrow field of view that causes them to miss navigation menus and sidebars [5].

### Typical failure points and design antidotes
The Nielsen Norman Group (NN/g) has identified specific friction points for lower-literacy users [5] [10].

| Failure Point | Why it Fails (NN/g Findings) | Design Antidote |
| :--- | :--- | :--- |
| **Dense Text & Jargon** | Users read word-for-word; complex words cause them to skip or abandon tasks. | Write at a 6th-8th grade reading level; use plain language (e.g., "Reason for visit" instead of "Chief complaint") [5] [10]. |
| **Complex Navigation** | Users cannot quickly scan lists of options; they miss items outside the main text flow. | Use a single-column layout; provide linear, step-by-step choices rather than fly-out menus [5]. |
| **Scrolling** | Scrolling breaks visual concentration; users lose their place because they cannot scan to find where they left off. | Place the most important information above the fold; minimize scrolling by breaking tasks into distinct screens/messages [5]. |
| **Search Functions** | Users struggle with spelling query terms and processing out-of-context search snippets. | Make search tolerant of misspellings; ideally, guide users via buttons rather than open-ended search [5]. |
| **Moving UI Elements** | Animations distract and confuse users who are focusing intensely on reading. | Avoid text that moves or changes; keep interfaces static [5]. |

**Takeaway:** Simplifying text and streamlining navigation are not just aesthetic choices; they are functional requirements for this population.

### Proven improvements and targets
* **Fact:** In a usability study by NN/g, rewriting website content to target a broader consumer audience (6th-8th grade reading level) increased the success rate for lower-literacy users from 46% to 82% [5].
* **Fact:** Lower-literacy users also increased their performance speed by 135% on the revised site [5].
* **Inference:** Investing in plain language and linear design yields massive, measurable improvements in task completion for vulnerable populations.

### Voice/audio/image aids — promise and proof gap
* **Inference:** While direct U.S. civic-tech randomized controlled trials on voice interfaces for this specific demographic are sparse in the provided literature, the NN/g principles strongly suggest that bypassing text via audio (e.g., WhatsApp voice notes) or image-based navigation (pictograms) will reduce cognitive load. Teams should pilot short (20-30 second) audio instructions alongside text.

## Richmond neighborhood focus — Where to activate first
To deploy a solution effectively in Richmond, teams must target the neighborhoods where immigrant populations are concentrated.

* **Fact:** The Southwood neighborhood in Richmond's Southside has a population that is 84.2% Hispanic [3].
* **Fact:** The Virginia Digital Opportunity Plan highlights that Hispanic and Latino individuals are highly concentrated in the Southside region, and emphasizes the need for a "multigenerational approach to digital skills training" to reach language-learning communities [6].
* **Inference:** Field testing, outreach, and digital navigator deployments should be heavily concentrated in the Southside, specifically around Southwood. Partnering with local community-based organizations (CBOs) in this area is critical for building trust.

## 48-hour design blueprint — Ship fast, de-risk later
For a team building a solution in 48 hours, the focus must be on immediate utility, low friction, and mobile optimization.

### Must-haves in 48 hours (Design Recommendations)
1. **WhatsApp Chatbot/Flow:** Stand up a simple WhatsApp business account. Use WhatsApp's native interactive buttons for menus (avoiding typed responses).
2. **One-Question-at-a-Time Intake:** Instead of a long web form, ask for information sequentially in the chat.
3. **Multilingual Support:** Launch with English and Spanish immediately, given the Southside demographics [3].
4. **No Passwords:** Use phone-number authentication (OTP via SMS or WhatsApp) instead of requiring email-based account creation and password management.

### Content and copy
* Write all interface copy at a 6th-grade reading level [5].
* Use clear, descriptive labels (e.g., "Do you have a phone?" instead of "Indicate telecommunications status") [10].

### Staff operations
* Ensure the automated WhatsApp flow has a clear "Talk to a human" escape hatch.
* Equip backend staff with scripts to refer users to the Lifeline program or local digital navigators if they report connectivity issues [6] [2].

## Platform recommendations
1. **Prioritize WhatsApp:** It is the most reliable, familiar, and feature-rich platform for this demographic [4]. It supports voice notes for low-literacy users and end-to-end encryption for privacy.
2. **SMS as Fallback:** Use SMS for users who do not have smartphones or data plans, but limit it to simple alerts and reminders due to the higher literacy load of text-only communication.
3. **Web as Last Resort:** Only use web pages for static, highly simplified informational content. If a web form is absolutely necessary, it must be a single column, require no scrolling, and use massive tap targets [5].

## What to avoid
To prevent alienating this population, teams must strictly avoid:
* **Account Creation & Passwords:** These are massive barriers for low-literacy users.
* **Multi-column Layouts & Fly-out Menus:** These require scanning abilities that lower-literacy users do not utilize [5].
* **Jargon & Multi-syllabic Words:** These cause users to abandon tasks [5] [10].
* **Heavy Media:** Uncompressed images or auto-playing videos will drain limited data plans.
* **Strict ID/Credit Requirements:** Avoid requiring SSNs upfront, as this excludes undocumented immigrants and those relying on prepaid plans [9].

## Implementation enablers — Partners, privacy, and policy
* **Partnerships:** Collaborate with trusted local entities. The Virginia Digital Opportunity Plan emphasizes working with Community Action Agencies (like SERCAP) and local offices [6].
* **Privacy:** Immigrant populations may be highly sensitive to data collection due to enforcement fears (e.g., ICE activities reported in Southwood [11]). Practice strict data minimization—only collect what is absolutely necessary to provide the service.

## Metrics, risks, and mitigations
* **Metrics to Track:** Task completion rates, drop-off points in the WhatsApp flow, and the percentage of users escalating to human support.
* **Risks:** Phone number churn (users changing prepaid SIMs) could lead to lost accounts.
* **Mitigations:** Allow users to easily update their phone numbers or re-verify their identity using a simple PIN or a trusted community navigator.

## References

1. *Affordable Connectivity Program | Federal Communications Commission*. https://www.fcc.gov/acp
2. *Richmond City Council wants to increase internet speeds, close ‘digital divide’ • Virginia Mercury*. https://virginiamercury.com/2024/09/17/richmond-city-council-wants-to-increase-internet-speeds-close-digital-divide/
3. *Race, Diversity, and Ethnicity in Southwood, Richmond, VA | BestNeighborhood.org*. https://bestneighborhood.org/race-in-southwood-richmond-va/
4. *WhatsApp, Facebook are the most used social media sites ...*. https://www.pewresearch.org/short-reads/2024/03/22/whatsapp-and-facebook-dominate-the-social-media-landscape-in-middle-income-nations/
5. *Lower-Literacy Users: Writing for a Broad Consumer Audience - NN/G*. https://www.nngroup.com/articles/writing-for-lower-literacy-users/
6. *Virginia Digital Opportunity Plan*. https://www.dhcd.virginia.gov/sites/default/files/DocX/vati/dop-appendix-files/virginia-digital-opportunity-plan.pdf
7. *Internet use, smartphone ownership, digital divides in the US: What we know | Pew Research Center*. https://www.pewresearch.org/short-reads/2026/01/08/internet-use-smartphone-ownership-digital-divides-in-u-s/
8. *Immigration Policy Changes Portend a Growth Shock for the U.S. Wireless Industry*. https://tbri.com/special-reports/immigration-policy-changes-portend-a-growth-shock-for-the-u-s-wireless-industry/
9. *Big 3 wireless carriers so far unfazed by immigration crackdown*. https://www.fierce-network.com/wireless/big-3-wireless-carriers-so-far-unfazed-immigration-crackdown
10. *Few Guesses, More Success: 4 Principles to Reduce Cognitive Load in Forms - NN/G*. https://www.nngroup.com/articles/4-principles-reduce-cognitive-load/
11. *VPM | People living in the Southwood Apartments on ...*. https://www.instagram.com/reel/DM0l-s2Ag7O/