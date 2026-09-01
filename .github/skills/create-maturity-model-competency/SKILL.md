---
name: create-maturity-model-competency
description: "Use when asked to create a new Microsoft 365 Maturity Model competency document."
argument-hint: "Provide the competency name and, optionally, its scope"
user-invocable: true
disable-model-invocation: false
---

# Create Maturity Model Competency

Create a new Microsoft 365 Maturity Model competency document in `docs/competencies/` that matches the structure and conventions of the existing primary competencies.

## Scope

- Create one primary competency document per invocation.
- Model the structure on existing primary competency documents in `docs/competencies/`, such as `microsoft365-maturity-model--collaboration.md`.
- Do not create how-to guides, principles documents, or practical scenarios in this skill.
- Do not modify existing competency documents beyond registering the new one in the index and table of contents.

## Step 1: Agree the Competency Name

Do not create any file until the name is settled. The name is the primary identifier for the competency across the document title, front matter, file name, index, and table of contents, so it must be simple.

A simple competency name:

- Uses two to four words, for example `Search`, `Collaboration`, `Staff and Training`, `Management of Content`.
- Describes an organizational capability, not a Microsoft product, feature, or service. Reject names such as `Teams`, `Copilot Adoption Portal`, or `SharePoint Governance Tooling`.
- Uses plain business language a non-specialist would recognize without a glossary.
- Avoids acronyms, ampersands, slashes, parentheses, punctuation, version numbers, and vendor branding.
- Is singular in concept, even when plural in wording. If the name needs "and" more than once, the competency is doing too much and should be split.
- Does not duplicate or substantially overlap an existing competency. Check the existing set first and confirm the boundary with the user if the new name is close to one already published.

If the user's proposed name fails any of these tests, propose two or three simpler alternatives, explain the reason briefly, and ask the user to choose or confirm before continuing.

Once the name is agreed, derive:

- **Title**: `Maturity Model for Microsoft 365 - <Competency Name> Competency`
- **File name**: `microsoft365-maturity-model--<kebab-case-name>.md` in `docs/competencies/`
- **TOC entry name**: `<Competency Name> Competency`

Confirm the derived file name with the user if a file with that name already exists.

## Step 2: Confirm the Competency Definition

Before drafting, establish and confirm with the user:

- The one or two sentence definition of the competency and what it deliberately excludes.
- The category lenses used within each level, for example People and Culture, Process, Technology, Governance, Risk, Compliance and Security, or Information Architecture. Choose lenses that suit this competency; do not copy another competency's lenses by default.
- The author or authors to credit.

Use the same category lenses at every level so a reader can trace one dimension from Level 100 to Level 500. If a lens has no meaningful state at Level 100, describe the ad-hoc or absent state rather than omitting the lens.

## Step 3: Create the Document

Write the file with this structure.

### Front matter

```yaml
---
title: Maturity Model for Microsoft 365 – <Competency Name> Competency
ms.date: <MM/DD/YYYY>
author: <GitHub handle of principal author>
ms.reviewer: pamgreen
manager: pamgreen
ms.topic: overview
ms.author: pamgreen
ms.service: microsoft-365
ms.localizationpriority: Low
description: Maturity Model for Microsoft 365 - <Competency Name> Competency
ms.collection: M365Community
---
```

Use the current date in `MM/DD/YYYY` form with zero padding.

### Body

1. `# Maturity Model for Microsoft 365 - <Competency Name> Competency`
2. `[!INCLUDE [content-disclaimer](../includes/content-disclaimer.md)]`
3. `![Maturity Model for Microsoft 365](../media/M365MM.png)`
4. `## Overview of the Concepts [tl;dr]` — why this competency matters, in plain language.
5. `## Definition of this competency` — the agreed definition and boundary.
6. `## Evolution of this competency` — how the competency progresses, including:
   - `See the [Maturity Model for Microsoft 365 - Introduction](../index.md) for definitions of the Maturity Model levels.`
   - A note on the sparkle marker if the document uses one: `Note: Some characteristics should, perhaps, be addressed a little more urgently than others; these have been marked with the 'Sparkles' emoji: ✨`
7. The five levels, each as an `###` heading, in order:
   - `### Level 100 - Initial`
   - `### Level 200 - Managed`
   - `### Level 300 - Defined`
   - `### Level 400 - Predictable`
   - `### Level 500 - Optimizing`
8. `## Common Microsoft 365 tool sets` — the apps and services relevant to the competency, framed as supporting the competency rather than as a checklist that creates maturity.
9. `## Resources` containing `[!INCLUDE [mm4m365-practitioners](../includes/mm4m365-practitioners.md)]`
10. A `**Principal authors**:` list of linked author names, separated by `---` rules.
11. `[!INCLUDE [mm4m365-core-team](../includes/mm4m365-core-team.md)]`

Optionally add `## Cost & Benefit`, `## Conclusion`, or a `## Related documents` section where the competency warrants it. Include `## Related documents` linking the introduction and any how-to guide once one exists.

### Level structure

Each level uses this shape:

```markdown
### Level 200 - Managed

<A short narrative paragraph describing the organizational state at this level.>

**[Managed level](../overview/microsoft365-maturity-model--intro.md#level-200---managed)** characteristics include:

#### <Category lens>

- <Characteristic written as a recognizable statement of current state.>

#### <Category lens>

- <Characteristic.>

#### Impacts

<What this level means for the organization and its people.>
```

Anchor values for the level links are `#level-100---initial`, `#level-200---managed`, `#level-300---defined`, `#level-400---predictable`, and `#level-500---optimizing`. Verify the opening parenthesis is present in every level link; a missing parenthesis is a known defect in existing documents.

## Content Requirements

- Each level describes an organizational state, not a list of Microsoft 365 features.
- Levels are meaningfully distinct and progress from reactive or ad-hoc, through managed and standardized, to measured and continuously improved.
- Level 500 shows feedback-driven optimization, automation in service of outcomes, and sustained value — not simply more tooling.
- Characteristics at a level can plausibly coexist in a real organization at that stage.
- Every level has an `#### Impacts` section whose claims follow from that level's characteristics.
- Impacts describe concrete business consequences such as productivity, risk, compliance, cost, quality, experience, resilience, or decision-making.
- Do not repeat a characteristic across two category lenses within the same level.
- Guidance stays applicable across organization sizes, sectors, and adoption paths, and avoids unsupported absolutes.

## Style Conventions

- All category headings within a level are `####`. Never use `###` for a category.
- Use US spelling consistently.
- Use `#### Impacts` as the heading, without the level number.
- Use sparkles (`✨`) only for genuinely urgent or foundational characteristics, and sparingly. They are optional.
- Keep bullet punctuation consistent within the document.
- Use repository-relative links with meaningful link text.
- Do not duplicate entries in the toolset list, and use current product names.

## Step 4: Register the Competency

After creating the document:

1. Add a link to `docs/competencies/microsoft365-maturity-model--competencies.md` in the existing alphabetical list, using the format `- [<Competency Name>](microsoft365-maturity-model--<kebab-case-name>.md)`.
2. Add an entry to `docs/competencies/toc.yml` in alphabetical position:

   ```yaml
   - name: <Competency Name> Competency
     href: microsoft365-maturity-model--<kebab-case-name>.md
   ```

   Use the nested `items:` form only when a matching how-to guide also exists.

## Step 5: Report

Summarize:

- The agreed competency name and why it qualifies as simple.
- The file created and the files updated.
- The category lenses used across the levels.
- Any sections left as placeholders that need subject matter input before publication.

Then suggest reviewing the new document with the `review-maturity-model-competency` skill.
