# Technical Writing Workflows

A small Docs-as-Code example showing how API specifications and Markdown documentation can be checked automatically with GitHub Actions.

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
└── openapi/
    └── openapi.yaml
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

The repository includes a deliberately small fictional Tasks API. Its specification and overview are sample content for demonstrating documentation quality checks; they do not describe a production service.

## Scope

This repository focuses on documentation quality automation. It is an example workflow, not a complete API implementation or a production deployment pipeline.
