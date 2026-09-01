---
name: review-maturity-model-practical-scenario
description: "Use to review a Microsoft 365 Maturity Model practical scenario."
argument-hint: "Provide the practical scenario document path to review"
user-invocable: true
disable-model-invocation: false
---

# Review Maturity Model Practical Scenario

Review one Microsoft 365 Maturity Model practical scenario. Assess whether it applies the Maturity Model to a specific business need, is complete and internally consistent, helps an organization recognize its current state, and gives actionable direction for progressing.

## Scope

- Review a practical scenario document in `docs/practical-scenarios/`.
- Use other practical scenarios as examples of established conventions, not as a rigid template.
- Practical scenarios deliberately vary in shape. Do not review them against the primary competency documents in `docs/competencies/` as if they were competencies; competencies define a broad capability, practical scenarios apply the model to a focused topic and normally span several competencies.
- Do not review `maturity-model-microsoft365-practical-scenarios.md` (the landing page) as a scenario. Treat it as context describing the intent of the series.
- Do not edit the document unless the user asks for changes after the review.

## Established Document Shape

A practical scenario normally contains:

1. YAML front matter with title, `ms.date`, author, `ms.reviewer`, `manager`, `ms.topic`, `ms.author`, `ms.service`, `ms.localizationpriority`, description, and `ms.collection: M365Community`.
2. An `# Practical Scenarios - <topic>` style H1 followed by the content disclaimer include: `[!INCLUDE [content-disclaimer](../includes/content-disclaimer.md)]`.
3. An `## Overview` or `## Introduction to <topic>` section that states the scenario applies Maturity Model concepts and characteristics to a specific business need, and normally links to the Maturity Model.
4. Topic framing before the levels, such as principles, challenges, sub-categories, or a process diagram, that establishes the lens used through the levels.
5. An `## Applying the Maturity Model to <topic>` section containing all five levels in order: Level 100 Initial, Level 200 Managed, Level 300 Defined, Level 400 (Predictable / Quantitatively Managed / Managed (Capable)), and Level 500 Optimizing.
6. Per level, some combination of a narrative or illustrative scenario, characteristics, impacts, key metrics, and development actions to reach the next level.
7. Optional closing material: success metrics, common challenges, conclusion, related documents, external resources.
8. A `**Principal author**` or `**Principal authors**` credit block at the end, normally separated by `---` rules.

Level heading style (`### Level 100: Initial` versus `## Level 100 - Initial`), level naming for 400, and category naming are all topic-specific and vary across existing scenarios. Do not flag that variation on its own; flag only inconsistency *within* the document under review.

## Reference Examples

Read these only as needed to resolve a convention question:

- `maturity-model-microsoft365-ps-knowledge-management.md` — the richest structure: sub-categories carried consistently through every level, per-level key success metrics, and explicit `Development actions & activities (L100 → L200)` transitions.
- `maturity-model-microsoft365-ps-enhancing-brand-management.md` — strong pattern of an illustrative `**Scenario:**` narrative opening each level, followed by characteristics and per-level development actions.
- `maturity-model-microsoft365-practical-scenarios-copilot-implementation.md` — characteristics / impacts / next steps per level, explicit naming of the competencies the scenario spans, and a "what not to measure" metrics section.
- `maturity-model-microsoft365-servicing-microsoft365-service-health-management.md` — a deliberately concise scenario; proof that brevity is acceptable when each level still differentiates.

## Review Procedure

1. Read the target document in full. Read a reference scenario or the Maturity Model introduction only when needed to resolve an ambiguity.
2. Verify the publishing structure:
   - Front matter is present, valid, and consistent with the H1 and description.
   - The content disclaimer include is present and its relative path resolves.
   - Headings form a logical hierarchy with no skipped levels, and level headings are styled consistently with each other within the document.
   - Links, images, and includes use valid repository-relative paths, have meaningful link text, and images have descriptive alt text.
   - The document is listed in `docs/practical-scenarios/toc.yml`.
   - All five maturity levels are present and in order.
   - Markdown lists, terminology, capitalization, and punctuation are consistent within the document.
3. Assess the scenario framing:
   - The overview states the specific business need, process, or activity being matured, and its boundary is clear.
   - The document explains why this topic warrants a practical scenario rather than being covered by a competency.
   - It identifies, explicitly or implicitly, which competencies it draws on and does not silently duplicate or contradict them.
   - Any principles, challenges, or sub-categories introduced up front are actually used through the levels.
4. Assess the maturity progression, level by level:
   - Each level describes an organizational state for this specific topic, not simply a list of Microsoft 365 features.
   - Levels are meaningfully distinct and move from ad-hoc or reactive practice toward managed, standardized, measured, and continuously improved practice.
   - Any lens established up front (categories, sub-categories, people/process/technology) is carried through every level, or its absence at a level is intentional and explained.
   - Characteristics at a level can coexist in a real organization and are plausible for that stage.
   - Level 400 shows measurement and predictability, not just more process; Level 500 shows feedback-driven optimization and sustained value, not just more tooling.
   - The scenario does not assume an organization must mature every dimension at the same rate.
5. Assess practical, actionable value — this is what distinguishes a practical scenario:
   - A reader can locate their organization's current level from the characteristics without hidden expertise.
   - Development actions, next steps, or transitions between levels are present and specific enough to act on, rather than restating the next level's characteristics.
   - Illustrative scenarios or examples are recognizable and tied to real work.
   - Metrics, where present, measure outcomes rather than activity or licence counts.
   - Named Microsoft 365 services support the topic but do not become a product checklist or imply that technology alone creates maturity.
   - Guidance remains applicable across organization sizes, sectors, and adoption paths where reasonably possible.
6. Check coherence and currency:
   - Terms, category names, and level naming retain the same meaning throughout.
   - Impacts follow from the characteristics stated at that level.
   - Product names, capabilities, and external links are current and not deprecated or renamed.
   - Author credits, `ms.date`, and any versioned claims are consistent with the content.
7. Report findings; do not manufacture findings. Cite the relevant heading or a concise quoted phrase, explain the reader or publishing impact, and propose a specific revision direction.

## Findings Thresholds

Classify findings in this order:

- **Blocker**: Prevents reliable publishing or makes the scenario unusable, such as missing levels, malformed front matter, a missing or broken content disclaimer include, broken required links or images, invalid heading hierarchy, or the document being absent from `toc.yml`.
- **High**: Misleads assessment or weakens the scenario materially, such as indistinguishable levels, a feature list with no organizational outcome, a scenario boundary that duplicates or contradicts a competency, missing or non-actionable development actions, or a stated lens abandoned partway through the levels.
- **Medium**: Reduces clarity or practical application, such as a vague overview, weak or absent illustrative examples, activity-based metrics, uneven depth that leaves a level unexplained, inconsistent terminology, or outdated product names.
- **Low**: Editorial polish, such as grammar, punctuation, date formatting, alt text wording, wording, or nonessential formatting consistency.

Do not raise a finding solely because the document differs from another practical scenario in heading style, level-400 naming, section depth, length, number of images, or whether it uses per-level metrics. Flag those only when they make this document internally inconsistent, unclear, or less useful.

## Review Output

Use this format:

```markdown
# Practical Scenario Review: <scenario name>

## Summary
<Two to four sentences covering publishing readiness, strength of the maturity progression, actionability, and the highest-value improvement.>

## Findings

### Blocker
- None found.

### High
- **<heading or quoted phrase>**: <what is wrong and why it affects the reader or publication>.
  - Recommendation: <specific direction for revision>.

### Medium
- ...

### Low
- ...

## Scenario Assessment
| Area | Assessment | Notes |
| --- | --- | --- |
| Scenario boundary and purpose | Strong / Needs work | ... |
| Relationship to competencies | Strong / Needs work | ... |
| Level differentiation | Strong / Needs work | ... |
| Progression from 100 to 500 | Strong / Needs work | ... |
| Actionability of development steps | Strong / Needs work | ... |
| Measurement and outcomes | Strong / Needs work | ... |

## Strengths
- <Specific strength rooted in the document.>

## Suggested Next Steps
1. <Highest-priority revision.>
2. <Next revision, when needed.>
```

Omit empty severity groups only when the review would otherwise become repetitive. State `None found` for Blocker findings when no publication blocker exists.
