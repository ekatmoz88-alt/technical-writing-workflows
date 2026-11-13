# Technical Writing Workflows

[English](README.md) | [Русский](README.ru.md)

**Project website:** https://ekatmoz88-alt.github.io/technical-writing-workflows/

A real Docs-as-Code quality workflow used to validate API specifications and Markdown documentation automatically with GitHub Actions.

## What this repository demonstrates

- **OpenAPI validation** with Spectral.
- **Markdown linting** for documentation files.
- **Markdown link checking** with Lychee.
- **Continuous checks** on pushes and pull requests targeting `main` or `master`.

The workflow is defined in [`.github/workflows/lint.yml`](.github/workflows/lint.yml).

## Repository structure

```text
.
├── .github/
│   └── workflows/
│       └── lint.yml
├── docs/
│   └── tasks-api-overview.md
├── openapi/
│   └── openapi.yaml
└── index.html
```

## Run the checks

The GitHub Actions workflow runs automatically when code is pushed to `main` or `master`, and when a pull request targets either branch.

It performs three checks:

1. Spectral validates `openapi/openapi.yaml` as an OpenAPI description.
2. markdownlint checks Markdown files in `docs/`.
3. Lychee checks links in Markdown files across the repository.

To reproduce the first two checks locally, install the Spectral CLI and markdownlint-cli, then run:

```bash
spectral lint openapi/openapi.yaml
markdownlint docs/*.md
```

To check Markdown links locally, install [Lychee](https://github.com/lycheeverse/lychee) and run:

```bash
lychee --verbose --no-progress './**/*.md'
```

## Example API

The repository includes an anonymized Tasks API contract drawn from project documentation. The workflow validates the contract and its supporting Markdown; the CI pipeline itself does not deploy the API service.

## Scope

This repository documents the real documentation-quality pipeline. Its scope is CI validation of API and Markdown artefacts; application deployment is handled separately from this documentation workflow.


## Tags

`docs-as-code` · `github-actions` · `spectral` · `markdownlint` · `lychee` · `openapi` · `documentation-qa`
