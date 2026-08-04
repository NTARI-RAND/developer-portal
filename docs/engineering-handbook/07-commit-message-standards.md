# Commit Message Standards

## Overview

Commit messages are part of the engineering record. They help reviewers,
maintainers, release authors, and future contributors understand why a change
exists.

COSDS uses concise, structured commit messages inspired by Conventional Commits.
Repositories may adopt stricter automation later, but contributors should follow
this format now for consistency.

## Format

```text
<type>: <short summary>
```

Optional extended format:

```text
<type>(<scope>): <short summary>

<body explaining why the change is needed>

<footer with issue references or breaking-change notes>
```

## Commit Types

| Type | Use for | Example |
| --- | --- | --- |
| `docs` | Documentation changes | `docs: add branching guidance` |
| `fix` | Bug fixes | `fix: handle missing config file` |
| `feat` | New functionality | `feat: add issue export command` |
| `test` | Tests only | `test: cover invalid issue labels` |
| `refactor` | Internal restructuring | `refactor: split validation helpers` |
| `chore` | Maintenance | `chore: update workflow permissions` |
| `ci` | CI configuration | `ci: add markdown link check` |
| `security` | Security remediation | `security: redact token from logs` |
| `revert` | Reverts | `revert: remove experimental parser` |

## Summary Rules

A good summary:

- Uses the imperative mood.
- Starts with a lowercase verb after the type when practical.
- Is specific enough to understand in a changelog.
- Avoids vague words like "stuff," "updates," or "misc."
- Does not end with a period.

Good examples:

```text
docs: add pull request review checklist
fix: prevent empty repository names
ci: run spellcheck on markdown changes
```

Poor examples:

```text
updated files
fix stuff
WIP
final changes
```

## Scope

Use a scope when it adds clarity:

```text
docs(handbook): add communication standards
ci(markdown): add link checker workflow
fix(auth): reject expired tokens
```

Avoid scopes that are too broad to help, such as `repo` or `code`, unless the
repository has defined those scopes.

## Commit Body

Use a body when the reason is not obvious from the diff.

```text
fix: reject empty project identifiers

Empty identifiers currently pass validation and fail later during repository
lookup. Rejecting them at input validation keeps the error message close to the
user action and avoids an unnecessary database query.
```

The body should explain why the change is needed, not simply repeat what the
diff shows.

## Footers and References

Use footers for issue references, acknowledgements, and breaking-change notes.

```text
docs: add repository standards

Refs: #42
```

If a change intentionally breaks compatibility, call it out clearly:

```text
feat: replace legacy export format

BREAKING CHANGE: export files now use the v2 schema. Existing consumers must
update their import logic before upgrading.
```

## Commit Size

A commit should represent one coherent idea. If a reviewer cannot describe the
commit in one sentence, it may be too large or mixed.

Split commits when:

- Formatting changes hide behavior changes.
- Tests can be separated from implementation.
- Documentation updates describe a separate decision.
- A dependency update is unrelated to the feature work.

## Amend and Squash Guidance

Amending commits is acceptable on a local or personal branch. Once review has
started, avoid rewriting history unless it improves reviewability or a
maintainer asks for cleanup.

Squashing may be appropriate when:

- A pull request has many fixup commits.
- The final history should show one logical change.
- The repository uses squash merges by default.

## Related Chapters

- [GitHub Workflow](05-github-workflow.md)
- [Branching Strategy](06-branching-strategy.md)
- [Pull Request Process](08-pull-request-process.md)
- [Repository Standards](10-repository-standards.md)
