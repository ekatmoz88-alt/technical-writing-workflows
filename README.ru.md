# Процессы технического письма — Docs-as-Code CI

[English](README.md) | [Русский](README.ru.md)

**Опубликованный сайт:** https://ekatmoz88-alt.github.io/technical-writing-workflows/

Небольшой пример автоматизированного контроля качества API-спецификаций и Markdown-документации с помощью GitHub Actions.

## Назначение

Репозиторий демонстрирует конвейер проверок документации, а не полноценную реализацию API или production-систему.

## Что проверяется

- **OpenAPI:** проверка спецификации с помощью Spectral.
- **Markdown:** проверка оформления файлов через markdownlint.
- **Ссылки:** проверка Markdown-ссылок инструментом Lychee.
- **CI:** автоматический запуск проверок при push и pull request в `main` или `master`.

Workflow: [`.github/workflows/lint.yml`](.github/workflows/lint.yml).

## Структура

- `openapi/openapi.yaml` — демонстрационная спецификация Tasks API.
- `docs/tasks-api-overview.md` — обзор API.
- `.spectral.yaml` — правила Spectral.
- `.markdownlint-cli2.jsonc` — настройки Markdown lint.
- `.github/workflows/lint.yml` — GitHub Actions workflow.

## Локальный запуск

```bash
spectral lint openapi/openapi.yaml
markdownlint docs/*.md
lychee --verbose --no-progress './**/*.md'
```

## Ограничения

Tasks API — вымышленный пример для проверки процесса документации. Репозиторий не содержит полноценного API-сервиса и не заявляет production-развёртывание.

## Теги

`docs-as-code` · `github-actions` · `spectral` · `markdownlint` · `lychee` · `openapi` · `documentation-qa`
