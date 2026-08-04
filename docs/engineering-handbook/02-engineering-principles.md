# Engineering Principles

## Overview

NTARI engineering work is guided by principles that help volunteers and
maintainers make consistent decisions under uncertainty. These principles apply
across COSDS planning, implementation, review, documentation, and maintenance.

The principles are not slogans. They are decision tools. When a team faces a
tradeoff, the preferred choice should be the one that best preserves openness,
clarity, safety, and long-term maintainability.

## Core Principles

| Principle | Meaning | Practical signal |
| --- | --- | --- |
| Open by default | Work should be understandable from the public repository whenever possible. | Decisions are linked in issues, pull requests, or documentation. |
| Small changes win | Smaller changes are easier to review, test, and revert. | Pull requests have focused scope and clear acceptance criteria. |
| Security is shared | Every contributor helps protect users, contributors, and infrastructure. | Secrets, unsafe defaults, and dependency risks are treated as blockers. |
| Documentation is engineering | Documentation is part of the delivered system. | Behavior changes include docs or a clear reason docs are not needed. |
| Review is collaboration | Review improves the work; it is not a gatekeeping performance. | Comments are specific, respectful, and tied to project outcomes. |
| Maintainability over cleverness | Future contributors must be able to understand and change the system. | Simple, explicit solutions are preferred over hidden complexity. |
| License compliance is design | AGPL-3.0 and dependency obligations influence architecture and reuse. | License impact is considered before copying or importing third-party work. |

## Decision Hierarchy

When principles conflict, use this order:

1. Protect people, private information, and production systems.
2. Preserve legal and license compliance.
3. Maintain correctness and user trust.
4. Keep the change reviewable and reversible.
5. Optimize for speed only after the first four conditions are met.

## Open by Default

COSDS work should leave a public trail that a future contributor can follow.
This does not mean everything is public. Security-sensitive information,
private reports, credentials, and protected operational details must remain
private. It does mean that non-sensitive decisions should be captured in issues,
pull requests, RFCs, or documentation.

Good examples:

- Linking a pull request to the issue that explains the problem.
- Summarizing a design decision in the pull request description.
- Moving a recurring review concern into documentation.

Poor examples:

- Relying on an unrecorded chat conversation to explain why code works.
- Merging a large change without review context.
- Adding third-party code without attribution or license notes.

## Small Changes Win

A small change is not defined by line count alone. A change is small when a
reviewer can understand its purpose, risk, and validation path without guessing.

Prefer:

- One bug fix per pull request.
- One documentation topic per pull request.
- Separate pull requests for refactoring and behavior changes.
- Follow-up issues for work discovered during review.

Avoid:

- Combining formatting, refactoring, and feature logic in one pull request.
- Renaming files while changing behavior unless the rename is required.
- Adding broad abstractions before a repeated pattern is proven.

## Security Is Shared

Security is not only the responsibility of security specialists. Every COSDS
participant must stop and ask for help when a change could expose sensitive
information, weaken access controls, or create unsafe behavior.

Security-sensitive changes include:

- Authentication, authorization, and session handling.
- Secrets, tokens, credentials, keys, and environment files.
- Dependency updates with known vulnerabilities.
- Deployment, networking, or infrastructure configuration.
- User data collection, storage, processing, or deletion.

Report sensitive concerns using the repository security policy in
[`../../SECURITY.md`](../../SECURITY.md).

## Documentation Is Engineering

Documentation is part of how NTARI systems are designed, operated, and trusted.
A contribution is incomplete when it changes behavior but leaves future users or
maintainers unable to understand the change.

Documentation should be:

- Accurate enough to guide action.
- Clear enough for a new volunteer.
- Close to the system or process it describes.
- Updated in the same pull request when practical.

See [Documentation Standards](11-documentation-standards.md) for future
repository-wide documentation practices.

## Principle Application Example

Scenario: a volunteer proposes a large pull request that fixes a bug, changes
formatting across many files, and introduces a new dependency.

Recommended response:

1. Thank the contributor and identify the useful work.
2. Ask them to split formatting from behavior changes.
3. Request dependency rationale and license review.
4. Review the bug fix independently once scope is clear.
5. Capture remaining ideas in follow-up issues.

## Related Chapters

- [Purpose](01-purpose.md)
- [Communication Standards](04-communication-standards.md)
- [Pull Request Process](08-pull-request-process.md)
- [Code Review Standards](09-code-review-standards.md)
- [Repository Standards](10-repository-standards.md)
