# Code Review Standards

## Overview

Code review is a collaborative quality practice. In COSDS, review protects users,
contributors, maintainers, and NTARI's open-source obligations. A good review is
specific, respectful, and focused on the goals of the change.

Review applies to code, documentation, configuration, workflows, tests, and
repository governance.

## Review Goals

Reviewers should evaluate whether the change is:

- Correct for the stated problem.
- Safe for users, contributors, and infrastructure.
- Maintainable by future volunteers.
- Consistent with repository standards.
- Compatible with AGPL-3.0 and dependency obligations.
- Adequately tested or otherwise validated.
- Documented where behavior or process changes.

## Review Comment Types

Use clear labels when helpful.

| Label | Meaning | Example |
| --- | --- | --- |
| `blocking` | Must be resolved before merge. | `blocking: this exposes a token in logs.` |
| `suggestion` | Optional improvement. | `suggestion: consider naming this helper parseIssueId.` |
| `question` | Clarification needed. | `question: should this handle archived projects?` |
| `nit` | Minor style or wording issue. | `nit: this sentence can be shorter.` |
| `follow-up` | Separate work after merge. | `follow-up: add a migration guide in a new issue.` |

## What to Review

### Correctness

Ask:

- Does the change solve the stated problem?
- Are edge cases handled?
- Are failure modes clear?
- Does the implementation match the documentation?

### Security and Privacy

Ask:

- Does the change expose secrets, tokens, private data, or internal URLs?
- Does it weaken authentication, authorization, or validation?
- Are error messages safe to show publicly?
- Are dependencies trustworthy and license-compatible?

Sensitive issues should follow [`../../SECURITY.md`](../../SECURITY.md), not a
public review thread.

### Maintainability

Ask:

- Can a new contributor understand this change?
- Is the design simpler than the problem requires?
- Are names clear and consistent?
- Does the change avoid unnecessary coupling?

### Tests and Validation

Ask:

- Are automated tests included when appropriate?
- Is manual validation described clearly?
- Do CI checks cover the changed files?
- Are skipped tests or warnings explained?

### Documentation

Ask:

- Does user-facing behavior require documentation?
- Are internal links valid?
- Are examples accurate?
- Is the language accessible to volunteers?

## Review Tone

Review should be direct and respectful.

Prefer:

```markdown
blocking: this writes the access token to the debug log. Please remove the token
from the log message and add a regression test for redaction.
```

Avoid:

```markdown
This is obviously wrong. Why would you do this?
```

Good review comments focus on the work, explain the risk, and provide a path to
resolution.

## Approval Guidance

Approve when:

- The change meets the stated goal.
- Blocking concerns are resolved.
- Validation is adequate for the risk level.
- The change fits repository standards.

Request changes when:

- The change is incorrect or unsafe.
- Required tests or documentation are missing.
- The pull request scope is unclear or too broad.
- License, security, or privacy concerns remain unresolved.

Comment without approval when:

- You have questions but are not a required reviewer.
- You reviewed only part of the change.
- You want to provide suggestions without blocking.

## Review Latency

Maintainers should set expectations for review timing during each sprint. When a
review is delayed, leave a status comment so the author knows the work is not
lost.

Example:

```markdown
Thanks for the update. I will review this by Wednesday. If another maintainer
has context before then, please feel free to review sooner.
```

## Handling Disagreement

When reviewers and authors disagree:

1. Restate the shared goal.
2. Identify whether the disagreement is about facts, risk, preference, or scope.
3. Look for a smaller reversible step.
4. Ask a maintainer or technical lead to decide when needed.
5. Capture the decision in the pull request or issue.

## Related Chapters

- [Engineering Principles](02-engineering-principles.md)
- [Communication Standards](04-communication-standards.md)
- [Pull Request Process](08-pull-request-process.md)
- [Repository Standards](10-repository-standards.md)
