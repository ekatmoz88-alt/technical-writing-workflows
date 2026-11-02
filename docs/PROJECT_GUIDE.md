# Technical Writing Workflows: обзор проекта

## Назначение

Демонстрационный Docs-as-Code проект, который автоматически проверяет спецификацию OpenAPI, Markdown и ссылки.

## Структура

- `.github/workflows/lint.yml` — проверки документации.
- `.github/workflows/pages.yml` — публикация GitHub Pages.
- `openapi/openapi.yaml` — спецификация вымышленного Tasks API.
- `docs/tasks-api-overview.md` — обзор API.
- `index.html` — главная страница.

## Проверки

- Spectral — валидация OpenAPI.
- markdownlint — стиль Markdown.
- Lychee — проверка ссылок.

## Ограничения

Tasks API — пример для демонстрации автоматизации, не полноценная реализация API.