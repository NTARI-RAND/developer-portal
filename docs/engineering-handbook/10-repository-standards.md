# Repository Standards

## Overview

Repository standards keep NTARI projects understandable, maintainable, and ready
for open-source collaboration. COSDS repositories should make it easy for a new
volunteer to understand the project purpose, contribution path, license,
security expectations, and review workflow.

These standards apply to NTARI repositories unless a repository-specific guide
sets stricter requirements.

## Required Root Files

| File | Purpose |
| --- | --- |
| `README.md` | Introduces the repository and points contributors to next steps. |
| `LICENSE` | Declares the repository license, such as AGPL-3.0. |
| `CONTRIBUTING.md` | Explains how to contribute. |
| `CODE_OF_CONDUCT.md` | Defines community behavior expectations. |
| `SECURITY.md` | Explains how to report sensitive or repository integrity issues. |
| `CODEOWNERS` | Routes review responsibility to maintainers or teams. |
| `.gitignore` | Keeps local, generated, and sensitive files out of version control. |
| `.editorconfig` | Encourages consistent formatting across editors. |

## Recommended GitHub Files

| Path | Purpose |
| --- | --- |
| `.github/PULL_REQUEST_TEMPLATE.md` | Standardizes pull request descriptions. |
| `.github/ISSUE_TEMPLATE/` | Provides structured issue intake. |
| `.github/workflows/` | Runs repository automation and quality checks. |

## README Expectations

A repository README should answer:

- What is this repository?
- Who maintains it?
- What is the current status?
- How do contributors get started?
- Where are contribution, conduct, security, and license policies?

A README should not become a dumping ground for detailed operating procedures.
Link to dedicated documentation when the content grows.

## License Expectations

NTARI repositories that use AGPL-3.0 must keep the license visible and intact.
Contributors should not add third-party code, assets, or generated files unless
license compatibility is understood.

Before adding dependencies or copied material, ask:

- What license applies?
- Is attribution required?
- Is the license compatible with AGPL-3.0 distribution obligations?
- Does the dependency introduce network-service source availability concerns?
- Is there a simpler implementation that avoids the dependency?

## Repository Layout

A simple documentation-oriented repository may use:

```text
.
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── workflows/
├── docs/
│   └── engineering-handbook/
├── CODEOWNERS
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SECURITY.md
```

A software repository may add source, tests, examples, and scripts as needed.
Do not create empty trees without a near-term purpose.

## Configuration Standards

Repository configuration should be minimal, explicit, and documented.

Good practices:

- Use least-privilege permissions in GitHub Actions.
- Keep workflow triggers narrow enough to avoid unnecessary runs.
- Prefer relative links in Markdown.
- Ignore generated files and local environment files.
- Store secrets only in approved secret management systems.

Avoid:

- Committing `.env` files or credentials.
- Adding generated build output without a clear reason.
- Adding toolchains before the repository needs them.
- Depending on private resources from public workflows.

## Documentation Standards

Repository documentation should be discoverable and maintainable.

Use:

- Clear headings.
- Descriptive link text.
- GitHub-flavored Markdown tables where helpful.
- Mermaid diagrams when they clarify process or architecture.
- Relative links for internal references.

Avoid:

- Screenshots of text without transcription.
- Broken links to planned files.
- Placeholder text in production chapters.
- Private links in public documentation.

Future detailed guidance belongs in
[Documentation Standards](11-documentation-standards.md).

## Automation Standards

Automation should improve quality without creating unnecessary friction.

Recommended checks:

- Markdown linting.
- Broken link checking.
- Spellcheck.
- Unit and integration tests for software repositories.
- Security or dependency scanning when dependencies exist.

Workflow failures should be actionable. If a check is noisy, tune the
configuration rather than expecting contributors to ignore it.

## Repository Creation Checklist

Before a repository is considered ready for COSDS participation, confirm:

- Root community health files are present.
- The license is clear.
- Contribution and security paths are documented.
- CODEOWNERS entries point to real maintainers or teams.
- Issue and pull request templates are available.
- CI checks are appropriate for the repository type.
- Generated and sensitive files are ignored.
- The README describes current scope accurately.

## Future Docusaurus Compatibility

Documentation repositories may later be published with Docusaurus. To keep that
path open:

- Store documentation as Markdown under `docs/`.
- Prefer stable filenames and relative links.
- Avoid relying on GitHub-only rendering features when a portable alternative is
  practical.
- Delay Docusaurus-specific configuration until publication is approved.

## Related Chapters

- [Purpose](01-purpose.md)
- [Engineering Principles](02-engineering-principles.md)
- [GitHub Workflow](05-github-workflow.md)
- [Pull Request Process](08-pull-request-process.md)
- [Code Review Standards](09-code-review-standards.md)
