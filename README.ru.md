# Процессы технического письма — Docs-as-Code CI

[English](README.md) | [Русский](README.ru.md)

**Опубликованный сайт:** https://ekatmoz88-alt.github.io/technical-writing-workflows/

Реальный конвейер Docs-as-Code для автоматизированного контроля качества API-спецификаций и Markdown-документации с помощью GitHub Actions.

## Назначение

Репозиторий описывает реально используемый конвейер проверки документации. Он отвечает за CI-валидацию API- и Markdown-материалов; развёртывание прикладного сервиса выполняется отдельно.

## Что проверяется

- **OpenAPI:** проверка спецификации с помощью Spectral.
- **Markdown:** проверка оформления файлов через markdownlint.
- **Ссылки:** проверка Markdown-ссылок инструментом Lychee.
- **CI:** автоматический запуск проверок при push и pull request в `main` или `master`.

Workflow: [`.github/workflows/lint.yml`](.github/workflows/lint.yml).

## Структура

- `openapi/openapi.yaml` — обезличенная спецификация Tasks API из проектных материалов.
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

Tasks API представлен в репозитории обезличенным контрактом из реального проекта. Этот репозиторий содержит CI-проверки контракта и документации, а не исходный код самого API-сервиса.

## Теги

`docs-as-code` · `github-actions` · `spectral` · `markdownlint` · `lychee` · `openapi` · `documentation-qa`
