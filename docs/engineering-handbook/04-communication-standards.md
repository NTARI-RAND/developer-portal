# Communication Standards

## Overview

COSDS depends on clear, respectful, asynchronous communication. Contributors may
be distributed across time zones, experience levels, and availability windows.
Communication should therefore preserve context, reduce ambiguity, and make it
easy for another contributor to continue the work.

All communication must follow the repository
[`../../CODE_OF_CONDUCT.md`](../../CODE_OF_CONDUCT.md).

## Communication Principles

| Principle | Practice |
| --- | --- |
| Default to clarity | State the problem, context, and requested action. |
| Preserve context | Link issues, pull requests, commits, and decisions. |
| Respect volunteer time | Use concise updates and avoid unnecessary urgency. |
| Be kind and direct | Focus on the work, not the person. |
| Make decisions visible | Summarize outcomes where future contributors can find them. |

## Preferred Channels

| Need | Preferred GitHub location | Notes |
| --- | --- | --- |
| Report a defect | Bug Report issue | Include reproduction details when possible. |
| Suggest an improvement | Feature Request issue | Explain motivation and expected value. |
| Improve documentation | Documentation Improvement issue | Link the affected file or proposed location. |
| Propose a major decision | Engineering RFC issue | Include impact and open questions. |
| Review a change | Pull request review | Use comments tied to specific lines when useful. |
| Report sensitive risk | Security reporting path | Follow [`../../SECURITY.md`](../../SECURITY.md). |

## Issue Communication

An issue should answer three questions:

1. What problem or opportunity are we addressing?
2. Why does it matter?
3. What outcome would be considered complete?

Good issue comment example:

```markdown
I can take this. I plan to update the validation logic and add a regression
test. I expect to open a pull request by Friday. If I find that the behavior is
larger than described, I will split follow-up work into a separate issue.
```

Poor issue comment example:

```markdown
This is broken. Someone should fix it.
```

## Pull Request Communication

Pull request descriptions should be written for reviewers who did not watch the
work happen. A useful description includes:

- What changed.
- Why the change is needed.
- How it was validated.
- What risks or follow-ups remain.

Review discussions should distinguish blockers from suggestions:

- **Blocking**: must be addressed before merge.
- **Suggestion**: improves the change but is not required.
- **Question**: requests clarification before deciding.
- **Follow-up**: should become a separate issue if not handled now.

## Status Updates

Use status updates for long-running work. A lightweight update is enough:

```markdown
Status update:

- Completed: issue reproduction and failing test.
- In progress: implementation fix.
- Blocked by: maintainer decision on expected edge-case behavior.
- Next: update PR after decision.
```

## Decision Records

When a decision is made in an issue or pull request, summarize it before moving
on. Future contributors should not need to infer the outcome from a long thread.

Decision summary example:

```markdown
Decision: we will keep this validation in the service layer for now because the
CLI and API paths share the same rule. If a third consumer appears, we will
extract the rule into a shared module.
```

## Meeting and Chat Summaries

If a decision happens outside GitHub, summarize the outcome in the relevant
issue or pull request. Do not rely on private chat as the only record.

A good summary includes:

- Participants or roles involved.
- Decision made.
- Alternatives considered.
- Follow-up owner.
- Link to the related issue or pull request.

## Accessibility in Communication

Accessible communication helps all contributors participate.

Use:

- Descriptive links instead of "click here."
- Plain language when possible.
- Expanded acronyms on first use.
- Alt text for future images or diagrams.
- Code blocks for commands, logs, and examples.

Avoid:

- Screenshots of text without transcription.
- Unexplained abbreviations.
- Long unstructured comments.
- Tone that discourages questions.

## Related Chapters

- [Engineering Principles](02-engineering-principles.md)
- [Engineering Roles](03-engineering-roles.md)
- [GitHub Workflow](05-github-workflow.md)
- [Code Review Standards](09-code-review-standards.md)
