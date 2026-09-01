---
name: review-maturity-model-competency
description: "Use when asked to review a Microsoft 365 Maturity Model competency."
argument-hint: "Provide the competency document path to review"
user-invocable: true
disable-model-invocation: false
---

# Review Maturity Model Competency

Review one Microsoft 365 Maturity Model competency document. Assess whether it is complete, internally consistent, useful to an organization assessing its current maturity, and clear about the value of progressing through the model.

## Scope

- Review a primary competency document in `docs/competencies/`.
- Use other primary competency documents as examples of established conventions, not as a rigid template.
- Do not review how-to guides or principles documents unless they are explicitly in scope.
- Do not edit the document unless the user asks for changes after the review.

## Established Document Shape

A primary competency normally contains:

1. YAML front matter including title, date, author/reviewer metadata, service metadata, description, and collection.
2. A title, content disclaimer include, and maturity-model image.
3. `## Overview of the Concepts [tl;dr]` and `## Definition of this competency` sections.
4. `## Evolution of this competency`, including a link to the Maturity Model introduction.
5. The five maturity levels, in order: Level 100 - Initial, Level 200 - Managed, Level 300 - Defined, Level 400 - Predictable, and Level 500 - Optimizing.
6. A short narrative, characteristics, and impacts for each level.
7. Scenarios, benefits or costs, toolsets, resources, related documents, and author credits where appropriate for the competency.

Category headings within levels are competency-specific. They may focus on people, culture, process, technology, governance, information architecture, or other relevant lenses. Do not flag variation merely because another competency uses different categories.

## Review Procedure

1. Read the target document in full. Read the Maturity Model introduction and one or two comparable competency documents only when needed to resolve an ambiguity.
2. Verify the publishing structure:
   - Front matter is present, valid, and consistent with the document title and description.
   - Headings form a logical hierarchy, including `###` headings for levels and `####` headings for their categories and impacts.
   - Required links, includes, images, and internal references use valid repository-relative paths and meaningful link text.
   - All five levels are present, ordered correctly, and include characteristics plus an impacts section.
   - Markdown lists, terminology, capitalization, punctuation, and priority marker usage are consistent within the document.
3. Assess the maturity model itself, level by level:
   - Each level describes an organizational state, not simply a list of Microsoft 365 features.
   - Levels are meaningfully distinct and move from reactive or ad-hoc practice toward managed, standardized, measured, and continuously improved practice.
   - Progression addresses the dimensions that matter to the competency, such as people, process, governance, data, technology, adoption, risk, and measurement.
   - Characteristics at a level can coexist in a real organization and are plausible for that stage.
   - The model does not assume an organization must mature every dimension at the same rate.
   - Level 500 demonstrates feedback-driven optimization, adaptation, and sustained value rather than merely more tooling.
4. Assess practical value for the reader:
   - The overview and definition make the competency boundary and intended outcomes understandable to a non-specialist.
   - The characteristics help a reader recognize their current state without requiring hidden expertise.
   - The impacts explain concrete business consequences, including productivity, risk, compliance, cost, quality, customer or employee experience, resilience, or decision-making as relevant.
   - Scenarios are recognizable and link the competency to real work.
   - Toolsets support the competency but do not become a product checklist or imply that technology alone creates maturity.
   - Recommendations avoid unsupported absolutes and remain applicable across organization sizes, sectors, and Microsoft 365 adoption paths when possible.
5. Check coherence across the document:
   - Terms and category names retain the same meaning from level to level.
   - Claims in impacts follow from the characteristics at that level.
   - The definition, scenarios, toolsets, and related documents reinforce the same competency boundary.
   - Sparkles (`✨`), if used, mark genuinely urgent or foundational characteristics and are not treated as mandatory decoration.
6. Report findings; do not manufacture findings. Cite the relevant heading or a concise quoted phrase, explain the reader or publishing impact, and propose a specific revision direction.

## Findings Thresholds

Classify findings in this order:

- **Blocker**: Prevents reliable publishing or makes the maturity model unusable, such as missing levels, malformed front matter, broken required links/includes, invalid heading hierarchy, or absent impacts.
- **High**: Misleads assessment or weakens the model materially, such as indistinguishable levels, technical feature lists without organizational outcomes, progression that skips a maturity stage, or impacts unsupported by the stated characteristics.
- **Medium**: Reduces clarity or practical application, such as vague definitions, weak scenarios, sparse categories, inconsistent terminology, or uneven depth that leaves a level unexplained.
- **Low**: Editorial polish, such as grammar, punctuation, date formatting, wording, or nonessential formatting consistency.

Do not raise a finding solely because the document differs from another competency in category names, section depth, visual assets, the number of scenarios, or whether it uses priority markers. Flag those only when they make this document inconsistent, unclear, or less useful.

## Review Output

Use this format:

```markdown
# Competency Review: <competency name>

## Summary
<Two to four sentences covering publishing readiness, maturity-model strength, and the highest-value improvement.>

## Findings

### Blocker
- None found.

### High
- **<heading or quoted phrase>**: <what is wrong and why it affects assessment or publication>.
  - Recommendation: <specific direction for revision>.

### Medium
- ...

### Low
- ...

## Maturity Model Assessment
| Area | Assessment | Notes |
| --- | --- | --- |
| Competency boundary | Strong / Needs work | ... |
| Level differentiation | Strong / Needs work | ... |
| Progression from 100 to 500 | Strong / Needs work | ... |
| Practical assessment value | Strong / Needs work | ... |
| Business outcomes and impacts | Strong / Needs work | ... |

## Strengths
- <Specific strength rooted in the document.>

## Suggested Next Steps
1. <Highest-priority revision.>
2. <Next revision, when needed.>
```

Omit empty severity groups only when the review would otherwise become repetitive. State `None found` for Blocker findings when no publication blocker exists.