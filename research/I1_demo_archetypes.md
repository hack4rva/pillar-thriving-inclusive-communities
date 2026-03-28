> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

```markdown
---
title: "I1 Demo Archetype"
date: 2024-04-24
description: "Demonstration archetype for the I1 project, illustrating content structure and front-matter conventions."
author: "I1 Documentation Team"
---

# I1 Demo Archetype

## Purpose
The **I1 demo archetype** serves as a starter template for new content within the I1 documentation system. It showcases the required front-matter fields, standard Markdown conventions, and example sections that authors can copy-paste when creating new pages.

## Front-Matter Specification
| Field | Type | Required | Description |
|-------------|---------------------|----------|------------------------------------------------------------------------|
| `title` | string | Yes | Human-readable title of the page. |
| `date` | date (`YYYY-MM-DD`) | Yes | Publication date; defaults to the file's creation date. |
| `author` | string | No | Name of the contributor. |
| `description`| string | No | Brief summary for search engines and index listings. |
| `tags` | array of strings | No | Keywords that aid navigation and filtering. |
| `draft` | boolean | No | Set to `true` to exclude the file from production builds. |

> **Note:** All dates follow ISO 8601 (`YYYY-MM-DD`). If only the year is known, use `YYYY-01-01` as a placeholder or omit month/day.

## Content Sections

### Overview
This archetype documents the core concepts behind the I1 demo, including its intended audience, primary use-cases, and integration points with the broader documentation suite.

### Detailed Description
The I1 demo combines **Markdown** with **YAML front-matter** to enable static-site generators (e.g., Hugo) to produce consistent pages [1]. It demonstrates how to embed code blocks, tables, and call-out notes while maintaining accessibility standards. Nearly all Markdown applications support the basic syntax outlined in the original Markdown design document, utilizing number signs for headings and standard punctuation for formatting [2].

### Implementation Example
Below is a concrete example of how the archetype might be used in practice:

```markdown
---
title: "Getting Started with I1"
date: 2025-06-01
author: "Jane Doe"
tags: ["getting-started", "i1", "tutorial"]
draft: false
---

# Getting Started

Welcome to the I1 tutorial. This guide walks you through the initial setup, explains core concepts, and provides sample commands you can run right away.
```

### Limitations & Known Issues
- **Internationalisation:** Only English localisation is provided as of 2024. *(Data not available for other languages.)* 
- **Automated validation:** No CI hook validates front-matter schema automatically; manual checks are required. 
- **Metadata completeness:** Some legacy pages lack `tags`; consider retrofitting them during the next documentation sprint. 

### References

1. *Archetypes*. https://gohugo.io/content-management/archetypes/
2. *Basic Syntax*. https://www.markdownguide.org/basic-syntax/
3. *archetypes/default.md · dev · TeDomum / Website · GitLab*. https://git.tedomum.net/tedomum/www/-/blob/dev/archetypes/default.md