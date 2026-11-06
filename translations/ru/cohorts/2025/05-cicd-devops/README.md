> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/cohorts/2025/05-cicd-devops/README.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.
> **Архив курса 2025.** Исторические инструкции, даты и ссылки сохранены, включая встречающиеся в исходнике упоминания 2026 года.

<a id="module-5--ai-for-cicd--devops"></a>
# Модуль 5 — ИИ для CI/CD и DevOps

<a id="overview"></a>
## Обзор

- Ревью и сводки PR с помощью ИИ, подсказки о рисках изменений.
- Автоматическая генерация тестов, проверки порогов покрытия и оценка LLM в CI.
- Примечания к релизам, черновики журналов изменений и инструкции по развёртыванию.
- Разборы инцидентов и ИИ-помощники дежурных инженеров.

<a id="detailed-description"></a>
## Подробное описание

- Пайплайн GitHub Actions с ИИ-шагами: сводка PR, проверка conventional commits, промпт генерации тестов и примечания к релизу.
- Боты для ревью PR (открытые или SaaS) и собственные промпты с учётом правил репозитория.
- Оценка LLM и регрессионные проверки (эталонные наборы промптов и ответов), которые останавливают сборку при ухудшении качества.
- Безопасное использование: секреты, скрытие данных, политика применения ИИ в OSS, хранение артефактов и аудит.
- Результат: репозиторий с CI, который автоматически составляет сводки PR, генерирует черновики тестов и формирует примечания к релизу при создании тега.

<a id="relevant-links"></a>
## Полезные ссылки

- [GitHub Actions — документация](https://docs.github.com/actions)
- [GitHub Copilot for Pull Requests](https://docs.github.com/copilot/using-github-copilot/pull-requests)
- [CodeRabbit AI PR Reviewer (Action)](https://github.com/marketplace/actions/coderabbit-ai-pr-reviewer)
- [Evidently — оценка LLM](https://www.evidentlyai.com/llm-evaluation)
- [Deepchecks LLM](https://docs.deepchecks.com/stable/llm/index.html)
