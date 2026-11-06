> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/research/article3-deployment/wiki/synthesis.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

> **Исследовательский архив.** Это перевод рабочих исследовательских материалов, а не актуальная инструкция. Утверждения, статусы и сведения об инструментах отражают даты исходника и могут устареть; перед практическим использованием проверьте текущую документацию.

<a id="synthesis"></a>
# Синтез

<a id="recommended-through-line"></a>
## Рекомендуемая сквозная линия

- [HUMAN] Продолжить пример interview-canvas из статьи 2 и сохранить прямой обучающий голос.
- [INFERENCE article-2-end-to-end,full-stack-workshop-deployment] Сохранить тот же пошаговый подход, что и при разработке: внести одно эксплуатационное изменение, проверить полученный артефакт и только затем добавлять следующий слой.
- [INFERENCE article-3-live-workshop,interview-canvas-repository] Использовать последовательность живого воркшопа: один контейнер → Postgres → Compose → интеграционные и сквозные тесты → AWS → GitHub Actions → удаление ресурсов.

<a id="required-translations"></a>
## Необходимая адаптация

- [FACT interview-canvas-repository] Настройка базы данных называется `SDIP_DATABASE_URL`, а не `SNAKE_ROYALE_DATABASE_URL` из воркшопа.
- [FACT interview-canvas-repository] Существующий многоэтапный Dockerfile копирует `frontend/dist/client` в `app/static` и обслуживает приложение на порту 8000.
- [FACT interview-canvas-repository] Тесты бэкенда запускаются командой `make test`. Репозиторий после воркшопа также содержит наборы тестов фронтенда, интеграционные тесты и Playwright с целями Make.
- [FACT interview-canvas-repository] Особая точка взаимодействия приложения при развёртывании: WebSocket-комната с аутентификацией, поэтому полезный интеграционный тест должен включать двух клиентов и передачу изменения холста.
- [INFERENCE article-2-end-to-end,interview-canvas-repository] Команды и примеры должны использовать имена вроде `interview-canvas`, `interview-canvas-db` и `sdip`, а не `snake-royale` или `snakearena`.

<a id="workshop-material-to-preserve"></a>
## Материал воркшопа, который нужно сохранить

- [FACT full-stack-workshop-deployment] Воркшоп собирает фронтенд React на этапе Node и отдаёт его статические файлы с этапа Python/FastAPI.
- [FACT full-stack-workshop-deployment] Сначала он проверяет сохранность данных с именованным томом SQLite, затем добавляет драйвер Postgres и запускает Postgres локально.
- [FACT full-stack-workshop-deployment] Compose даёт базе данных стабильное сетевое имя сервиса и использует проверку работоспособности перед запуском приложения.
- [FACT article-3-live-workshop] Прототип в AWS использует инфраструктуру как код и запускает приложение и Postgres на одном экземпляре EC2. Для серьёзного использования автор рекомендует управляемый RDS и резервные копии.
- [FACT full-stack-workshop-deployment] Процесс CI/CD сначала запускает быстрые тесты фронтенда и бэкенда, затем интеграционные тесты, а развёртывание выполняет только из `main`; для аутентификации в AWS используется GitHub OIDC вместо сохранённого ключа доступа.
- [FACT full-stack-workshop-deployment] Воркшоп явно удаляет облачные ресурсы после работы, поскольку за работающий стек AWS начисляется плата.

<a id="material-article-3-must-add-or-correct"></a>
## Что статья 3 должна добавить или исправить

- [FACT article-2-end-to-end] Статья 2 обещала интеграционные тесты, Postgres, Docker Compose, миграции базы данных, публичное развёртывание и непрерывную доставку.
- [HUMAN] Автор решил отложить миграции базы данных, чтобы статья 3 оставалась согласованной с воркшопом.
- [INFERENCE full-stack-workshop-deployment,interview-canvas-repository] Первую ошибку Docker нужно подать как общий урок: проверяйте сгенерированный результат сборки фронтенда. Для этого репозитория проверенный целевой каталог: `dist/client`; обходной приём Snake Royale копировать не следует.
- [INFERENCE full-stack-workshop-deployment,interview-canvas-repository] Промпт для AWS должен упоминать поддержку WebSocket и HTTPS, поскольку совместная работа в реальном времени является ключевой функцией развёрнутого приложения.

<a id="ending-and-caveats"></a>
## Заключение и оговорки

- [FACT interview-canvas-repository] Репозиторий после воркшопа содержит файлы Compose, тестов, CloudFormation и GitHub Actions на коммите `e536482`.
- [FACT full-stack-workshop-deployment] Развёрнутый прототип всё ещё нужно укреплять: ограниченный CORS, надёжная аутентификация, хранение секретов, миграции, проверки работоспособности, логи и путь отката.
- [INFERENCE article-2-end-to-end,full-stack-workshop-deployment] Завершить статью переходом к материалу о DevOps и наблюдаемости, где в центре внимания будет эксплуатация после первого успешного развёртывания.
