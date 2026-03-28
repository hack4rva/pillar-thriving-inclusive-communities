> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Title: From 3 Hours to 30 Minutes — A Credible Cross-Agency Demo with D3=1

## Executive Summary
This document provides a complete 4-minute pitch script and judge Q&A preparation for the Demo Strategy I3 (Cross-Agency Navigation). The core strategy relies on the "honest gap" framing: acknowledging that a unified cross-agency dataset does not exist (Data Readiness Level D3=1) due to taxonomy fragmentation and varying technological capabilities among Community Based Organizations (CBOs) [1] [2]. Instead of faking a closed-loop system, the pitch demonstrates a pragmatic tool built on public information and Open Referral HSDS standards [3] [4]. It anchors its success criteria (D7) on reducing case manager referral preparation time from an average of 3 hours per client down to 30 minutes for 5 calls [5].

## 4-Minute Demo Script: Cross-Agency Navigation

**Speaker:** Lead Presenter / Product Manager
**Stage Directions:** *[Bracketed and italicized]*

### 1. The Case Manager Journey (0:00 - 0:30)
*[Screen shows a split screen: a frustrated case manager surrounded by sticky notes on the left, and a ticking clock on the right.]*

**Speaker:** "Meet Sarah, a local case manager. Research shows case managers like Sarah spend approximately 22% of their time just on care coordination [6]. When a resident faces an eviction risk, Sarah spends an average of 3 hours of indirect time per client, making up to 8 phone calls that average 28 minutes each just to find the right help [5]. This is the 3-hour coordination story. It leads to lost staff capacity, delayed help for residents, and severe burnout."

### 2. Naming the Data Wall (0:30 - 1:00)
*[Screen transitions to a bold slide: "D3 = 1: The Data Wall". It shows disconnected silos representing different agencies.]*

**Speaker:** "We wanted to build a fully automated, closed-loop referral system. But we have to be honest: the data doesn't exist. This is the D3=1 problem. There is a lack of a comprehensive, non-proprietary human services taxonomy [1]. Furthermore, local CBOs have massive technological disparities—some use advanced APIs, while others rely on paper [2]. Pretending we can build a live, cross-agency feed today is theater. We built with what actually exists."

### 3. What We Built with Public Information (1:00 - 2:30)
*[Screen shows the live demo of the tool: A clean dashboard showing a 'Pathway Map' for Eviction Risk, an 'Intake Guide', and a 'Service Taxonomy'.]*

**Speaker:** "Here is what we built using publicly available information. *[Clicks into Eviction Risk Pathway]* We created a pathway map that aggregates public directory data—like 211 listings—into a single, actionable 'prep pack'. 

*[Highlights the data structure on screen]* 
Under the hood, we aren't using a proprietary database. We structured this public data using the Open Referral Human Services Data Specification (HSDS), an open-source data exchange standard endorsed by Inform USA [3] [4]. 

*[Clicks into an Intake Guide]* 
Because we can't see live capacity, we focused on what we *can* control: readiness. This intake guide provides Sarah with pre-filled eligibility checklists, required documentation lists, and warm-transfer call scripts. We crosswalked the top 50 local needs to HSDS categories so Sarah doesn't have to guess which agency handles what."

### 4. What the Tool Does Today (2:30 - 3:30)
*[Screen shows a side-by-side comparison: The old 3-hour process vs. the new 30-minute workflow. A timer graphic emphasizes the speed.]*

**Speaker:** "What does this do for Sarah today? It changes our D7 Success Criteria from a vague 'better coordination' to a hard metric: Sarah can use this tool to prepare for 5 referral calls in 30 minutes, instead of 3 hours. 

By providing verified hours, eligibility rules, and 'verify-before-transfer' prompts, we eliminate the dead-ends that consume her day. Studies show that effective care coordination and obtaining needed referrals can reduce the odds of time burdens by up to 32% [7]. We are giving Sarah the scaffolding to achieve that time savings immediately, without waiting for a magical cross-agency database."

### 5. The Honest Gap (3:30 - 4:00)
*[Screen shows a transparent "Missing Data" ledger: Real-time capacity, Closed-loop status, Unified taxonomy.]*

**Speaker:** "But here is the honest gap. We still lack real-time capacity slots, and we cannot do automated closed-loop tracking. The healthcare delivery system is still evolving in its ability to formally represent and manage social needs [2]. To fill this gap, we don't need a new app; we need Data Readiness. We need MoUs with local agencies to publish their data in HSDS format so it reaches Band C1—accessible and machine-readable [8]."

### 6. The Continuation Path (4:00 - 4:30)
*[Screen shows a 3-phase roadmap: 1. Prove Time Savings, 2. Data Accessibility (C1), 3. Targeted Pilots.]*

**Speaker:** "Our path forward is federated, not centralized. Phase 1 is proving the 30-minute time savings with this public-data tool. Phase 2 is securing MoUs with 211 and two key agencies to provide weekly HSDS exports. Phase 3 is a targeted, closed-loop pilot in just one vertical—like housing—where technological readiness actually exists. We aren't boiling the ocean; we are building a credible, standards-based bridge from D3=1 to real interoperability. Thank you."

---

## Judge Q&A Preparation

| Anticipated Question | Strategic Answer | Evidence Base |
| :--- | :--- | :--- |
| **Why didn't you build a unified cross-agency dataset?** | "Because a universal, non-proprietary taxonomy doesn't exist yet, and CBO tech readiness varies wildly from APIs to paper. Attempting a unified dataset now would result in stale data and alert fatigue." | HL7 FHIR HSD IG notes the lack of comprehensive open taxonomies [1]. EHRA notes massive tech disparities among CBOs [2]. |
| **How do you measure success (D7) if the data isn't integrated?** | "We measure success by case manager time saved. Our metric is reducing referral prep time from 3 hours per client down to 30 minutes for 5 calls, using structured 'prep packs'." | Care coordination pilots show a mean of 3 hours of indirect time per client [5]. |
| **How do you handle the proprietary nature of existing taxonomies like 211HSIS?** | "We use a minimal viable crosswalk. We map the top 50 local needs to the open-source Open Referral HSDS schema, which is endorsed by Inform USA for interoperability." | HSDS is an open exchange standard [3]. Inform USA recommends 211HSIS but requires any taxonomy to be machine-readable and mappable [4]. |
| **What is your plan to improve Data Readiness (D3)?** | "We are moving data from 'hearsay' (Band C4) to 'accessible' (Band C1) by pursuing MoUs for static HSDS exports from key agencies, rather than demanding expensive API integrations immediately." | Data Readiness Levels framework defines Band C1 as data ready to be loaded into analysis software [8]. |

## References

1. *Home - FHIR Human Services Directory v1.0.0*. https://build.fhir.org/ig/HL7/FHIR-IG-Human-Services-Directory/
2. *Closed-Loop Referrals for Health-Related Social Needs*. https://www.ehra.org/sites/ehra.org/files/Closed-Loop%20Referrals%20for%20Health-Related%20Social%20Needs%20Barriers%20and%20Recommendations%20September%202024.pdf
3. *Human Services Data Specification (HSDS) — Open Referral Data Specifications 3.0.1 documentation*. https://docs.openreferral.org/en/latest/hsds/overview.html
4. *Standards - Inform USA (formerly AIRS, the Alliance of Information and Referral Systems)*. https://www.informusa.org/standards
5. *
            Focusing on burden and capacity to support self-management of chronic health conditions: A pilot trial of care coordination in rural Australia - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC12953959/
6. *
            How do case managers spend time on their functions and activities? - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC4818942/
7. *
            Which Components of Medical Homes Reduce the Time Burden on Families of Children with Special Health Care Needs? - PMC
        *. https://pmc.ncbi.nlm.nih.gov/articles/PMC4369217/
8. *Data Readiness Levels: Turning Data from Palid to Vivid*. https://inverseprobability.com/2017/01/12/data-readiness-levels