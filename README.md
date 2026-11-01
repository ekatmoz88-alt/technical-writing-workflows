# Technical Writing Workflows

A small Docs-as-Code example showing how API specifications and Markdown documentation can be checked automatically with GitHub Actions.

## What this repository demonstrates

- **OpenAPI validation** with Spectral.
- **Markdown linting** for documentation files.
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

It performs two checks:

1. Spectral validates `openapi/openapi.yaml` as an OpenAPI description.
2. markdownlint checks Markdown files in `docs/`.

To reproduce the checks locally, install the Spectral CLI and markdownlint-cli, then run:

```bash
spectral lint openapi/openapi.yaml
markdownlint docs/*.md
```

## Example API

The repository includes a deliberately small fictional Tasks API. Its specification and overview are sample content for demonstrating documentation quality checks; they do not describe a production service.

## Scope

This repository focuses on documentation quality automation. It is an example workflow, not a complete API implementation or a production deployment pipeline.
