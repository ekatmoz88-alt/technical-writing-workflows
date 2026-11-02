# Запуск проверок и публикация

## Локальные проверки

Установите Spectral CLI, markdownlint-cli и Lychee. Из корня репозитория выполните:

```bash
spectral lint openapi/openapi.yaml
markdownlint docs/*.md
lychee --verbose --no-progress './**/*.md'
```

## GitHub Actions

Основные проверки находятся в `.github/workflows/lint.yml`. События запуска, целевые ветки и фильтры определяются этим workflow. Публикация сайта выполняется отдельно через `.github/workflows/pages.yml`.

## Release checklist

- [ ] Spectral не сообщает ошибок спецификации.
- [ ] markdownlint завершается успешно.
- [ ] Lychee не находит битых ссылок (или исключения объяснены).
- [ ] Проверки проходят на push и pull request.
- [ ] Pages build и deployment успешны.
- [ ] Главная страница и ссылки на артефакты открываются.

## Диагностика

Проверяйте первый упавший step в Actions. Если workflow не стартовал, сравните изменённые файлы с `paths` и `branches` в YAML.