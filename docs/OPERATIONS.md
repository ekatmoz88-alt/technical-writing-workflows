# Запуск проверок и публикация

## Быстрые ссылки
- [Опубликованный сайт](https://ekatmoz88-alt.github.io/technical-writing-workflows/)
- [Репозиторий](https://github.com/ekatmoz88-alt/technical-writing-workflows)
- [Запуски Actions](https://github.com/ekatmoz88-alt/technical-writing-workflows/actions)
- [Lint workflow](../.github/workflows/lint.yml)
- [Pages workflow](../.github/workflows/pages.yml)

## Локальные проверки
Из корня репозитория:
```bash
spectral lint openapi/openapi.yaml
markdownlint docs/*.md
lychee --verbose --no-progress './**/*.md'
```
Установите инструменты согласно версиям, указанным в workflow.

## Перед публикацией
- [ ] Spectral проходит без ошибок.
- [ ] Markdown lint проходит.
- [ ] Lychee не находит битых ссылок либо исключения документированы.
- [ ] Actions checks и Pages deployment завершились успешно.
- [ ] [Сайт](https://ekatmoz88-alt.github.io/technical-writing-workflows/) открывается.
