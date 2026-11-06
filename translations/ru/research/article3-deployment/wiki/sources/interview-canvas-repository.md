> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/research/article3-deployment/wiki/sources/interview-canvas-repository.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

> **Исследовательский архив.** Это перевод рабочих исследовательских материалов, а не актуальная инструкция. Утверждения, статусы и сведения об инструментах отражают даты исходника и могут устареть; перед практическим использованием проверьте текущую документацию.

<a id="interview-canvas-share-repository"></a>
# Репозиторий interview-canvas-share

Расположение: `https://github.com/alexeygrigorev/interview-canvas-share`

Репозиторий является источником истины для реализации после воркшопа. Проверен на коммите `e536482` 2026-08-12.

- [FACT interview-canvas-repository] Корень содержит `backend/`, `frontend/`, `Dockerfile`, `Makefile`, `openapi.yaml` и `AGENTS.md`.
- [FACT interview-canvas-repository] `SDIP_DATABASE_URL` настраивает SQLAlchemy; значение по умолчанию: `sqlite:///./sdip.db`.
- [FACT interview-canvas-repository] Dockerfile использует этапы с Node 24 и Python 3.12, копирует `frontend/dist/client` в `app/static` и открывает порт 8000.
- [FACT interview-canvas-repository] Makefile предоставляет `make run` и `make test` для бэкенда, а также цели для Compose, интеграционных тестов, тестов фронтенда и Playwright.
- [FACT interview-canvas-repository] `docker-compose.yaml` запускает приложение и Postgres, ожидает успешной проверки работоспособности базы данных и по умолчанию публикует приложение на порту 8100.
- [FACT interview-canvas-repository] Интеграционные тесты проверяют поведение HTTP и WebSocket на развёрнутом стеке. Playwright воспроизводит сценарий интервьюера и кандидата в двух браузерных контекстах.
- [FACT interview-canvas-repository] `deploy/aws/sdip-stack.yaml` развёртывает один экземпляр EC2 и поддерживает либо Caddy с доменом, либо CloudFront без домена. Postgres остаётся на томе экземпляра.
- [FACT interview-canvas-repository] `.github/workflows/ci.yml` параллельно запускает задания бэкенда и фронтенда, затем интеграционные и сквозные тесты, а затем развёртывание через документ AWS Systems Manager с ограниченными возможностями и роль OIDC.

Ограничение: ветка по умолчанию может измениться после фиксации. Развёртывание в AWS представляет собой прототип на одном экземпляре, а не управляемую или высокодоступную конфигурацию.

Зафиксировано: 2026-08-12.
