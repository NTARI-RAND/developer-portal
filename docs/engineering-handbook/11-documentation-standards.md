# Documentation Standards

## Overview

Documentation is an engineering deliverable in COSDS. It explains how people
understand, use, operate, review, and maintain NTARI systems. Documentation must
be accurate, accessible, version-controlled, and reviewable through the same
GitHub workflow used for code.

These standards apply to handbook chapters, project documentation, repository
README files, runbooks, RFCs, architecture notes, and contributor guidance.

## Documentation Principles

| Principle | Practice |
| --- | --- |
| Write for the next contributor | Assume the reader was not present for prior discussions. |
| Keep docs close to the work | Place documentation near the repository, feature, or process it describes. |
| Prefer explicit structure | Use headings, lists, tables, and examples to reduce ambiguity. |
| Keep links durable | Prefer relative internal links and stable public references. |
| Document decisions | Capture the reason for important choices, not only the final state. |
| Review documentation like code | Check accuracy, scope, accessibility, and maintainability. |

## Required Qualities

Good NTARI documentation is:

- **Accurate**: it matches the current repository behavior or clearly describes
  future work.
- **Actionable**: it helps the reader complete a task or make a decision.
- **Accessible**: it uses plain language, descriptive links, and text
  alternatives for visual material.
- **Traceable**: it links to related issues, pull requests, RFCs, or chapters.
- **Maintainable**: it has a clear owner or review path.
- **License-aware**: copied material, examples, and assets respect AGPL-3.0 and
  third-party licensing obligations.

## Document Types

| Type | Purpose | Typical location |
| --- | --- | --- |
| README | Repository introduction and navigation | Repository root |
| Handbook chapter | Shared engineering policy or process | `docs/engineering-handbook/` |
| Project documentation | Project-specific overview and usage | Project repository or project docs area |
| Runbook | Operational procedure | Operations documentation area |
| RFC | Proposal for significant change | RFC documentation area or issue form |
| Decision record | Captures a durable technical decision | Architecture or project docs area |

See [Project Documentation](15-project-documentation.md) for project-level
expectations.

## Markdown Structure

Use GitHub-flavored Markdown. Prefer predictable structure:

```markdown
# Page Title

## Overview

A short explanation of what the page covers.

## Requirements

- Requirement one.
- Requirement two.

## Examples

Concrete examples that contributors can adapt.

## Related Chapters

- Related page link
```

Rules:

- Use one top-level `#` heading per page.
- Use sentence-style headings.
- Keep sections focused.
- Use fenced code blocks with language identifiers when practical.
- Use tables for comparisons, ownership, status, or checklists.
- Avoid unexplained acronyms.

## Examples

Good example:

```markdown
## Validation

Run the following before requesting review:

- `npm test`
- `npm run lint`
- Review rendered Markdown for broken formatting.
```

Poor example:

```markdown
## Stuff

Do the normal checks.
```

The good example is specific, actionable, and reviewable. The poor example
requires private knowledge.

## Internal Links

Use relative links for repository files:

```markdown
See [Pull Request Process](08-pull-request-process.md).
```

Avoid absolute GitHub links for files in the same repository unless the link
must point to a specific historical revision.

Internal links should be checked before merge. For pull request guidance, see
[Pull Request Process](08-pull-request-process.md).

## External Links

External links should be:

- Publicly accessible.
- Stable enough for long-term documentation.
- Relevant to the surrounding text.
- Described with meaningful link text.

Avoid linking to private documents, expiring chat threads, or inaccessible
resources from public documentation.

## Accessibility Standards

Documentation should be usable by contributors with different tools, abilities,
and network conditions.

Checklist:

- Use descriptive link text.
- Provide alt text for images.
- Do not rely on color alone to convey meaning.
- Provide text summaries for diagrams.
- Use tables only when tabular structure improves comprehension.
- Keep sentences direct and avoid unnecessary jargon.

Mermaid diagrams are useful when they clarify flow, but the surrounding text
must still explain the process.

## Review Checklist

Before merging documentation changes, confirm:

- The page has a clear purpose.
- The content is accurate for the current repository state.
- Internal links resolve.
- Examples are safe to copy.
- Commands are fenced and include language identifiers where helpful.
- Accessibility expectations are met.
- Licensing and attribution are appropriate.
- Related handbook chapters are linked.

## Maintenance Expectations

Documentation should be updated when:

- A workflow changes.
- A command changes.
- A repository structure changes.
- A policy changes.
- Review comments show repeated confusion.
- A contributor needs private explanation to complete a public task.

Documentation debt should be captured as issues rather than left in untracked
notes.

## Related Chapters

- [Purpose](01-purpose.md)
- [Communication Standards](04-communication-standards.md)
- [Pull Request Process](08-pull-request-process.md)
- [Code Review Standards](09-code-review-standards.md)
- [Repository Standards](10-repository-standards.md)
