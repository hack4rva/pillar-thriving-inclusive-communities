# Data Prep Guide - Thriving and Inclusive Communities

How to get usable data for your MVP in 2–3 hours without waiting for an API.

---

## The data reality for this pillar

There is no clean, downloadable dataset of Richmond immigrant and refugee services. You will need to build one manually. This is a feature, not a bug — your curated, human-verified dataset will be more accurate than any automated scrape.

A curated list of 20–30 organizations with accurate contact information, languages served, and intake notes is more valuable for a weekend demo than an untested scrape of Help1RVA.

---

## Step 1: Start with Help1RVA

Go to https://help1rva.com and search for the following categories:
- Housing assistance
- Food assistance
- Immigration legal services
- English language learning (ESL)
- Workforce development
- Mental health and counseling
- Healthcare and clinics
- Emergency assistance

For each result, note:
- Organization name
- Phone number
- Address
- Languages listed
- Service description

Do this manually for 10–15 organizations per category you're covering. This takes about 2 hours for one focused researcher.

---

## Step 2: Cross-check with Virginia 211

Go to https://www.211virginia.org and run the same searches. Note any organizations that appear in 211 but not Help1RVA (or vice versa). Fill in any gaps in contact information.

---

## Step 3: Add language capacity flags

Help1RVA often lists whether an organization serves Spanish speakers. For other languages (Arabic, Nepali, Burmese), you will need to check organization websites directly or call.

During the hackathon, if you cannot verify language capacity, mark the field as "unverified" in your data rather than leaving it blank or guessing.

---

## Step 4: Add the privacy flag

For each organization, note whether they explicitly state that they serve undocumented residents or do not require immigration documentation. This is a critical field for your privacy-first tool.

Organizations to look for: those that explicitly state "serving all regardless of immigration status" or similar language.

If an organization's policy is unclear, mark it as "contact to confirm."

---

## Step 5: Build your JSON or CSV

Use the data model from `04_build_guides/02_recommended_architectures.md`. A minimal viable record for a service directory looks like:

```json
{
  "id": "001",
  "name": "Example Housing Nonprofit",
  "categories": ["housing"],
  "description": "Provides emergency rental assistance to residents in need.",
  "phone": "804-555-0100",
  "languages": ["en", "es"],
  "no_papers_required": true,
  "intake_notes": "Walk-ins accepted. Bring proof of address if available.",
  "verified_date": "2026-03-27"
}
```

---

## Step 6: Verify at least 5 phone numbers

Before demo, call or confirm at least 5 phone numbers to make sure they're active. Nothing undermines a demo faster than a resident trying to call a number that's been disconnected.

---

## What NOT to do with data

- Do not scrape Help1RVA automatically without reviewing whether their terms of service permit it
- Do not store any information about tool users in your data layer
- Do not include organizations without at least verifying the name and phone number
- Do not present the dataset as comprehensive or authoritative — label it as a curated sample
