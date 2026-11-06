> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/cohorts/2025/02-end-to-end/README.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.
> **Архив курса 2025.** Исторические инструкции, даты и ссылки сохранены, включая встречающиеся в исходнике упоминания 2026 года.

<a id="module-2--end-to-end-application-snake"></a>
# Модуль 2 — Приложение от начала до конца («Змейка»)

<a id="overview"></a>
## Обзор

[🎥 Видео](https://www.youtube.com/watch?v=vMNJru1y2Uc&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)

В этом модуле мы с помощью ИИ создадим приложение от начала до конца:

- создадим фронтенд с Lovable и React
- извлечём спецификации OpenAPI из фронтенда 
- реализуем бэкенд на FastAPI по спецификациям
- добавим в бэкенд поддержку базы данных
- упакуем всё в контейнеры
- развернём на Render
- создадим пайплайн CI/CD с тестами и развёртыванием

Весь код находится здесь: https://github.com/alexeygrigorev/snake-arena-online

<a id="frontend"></a>
## Фронтенд

[🎥 Видео](https://www.youtube.com/watch?v=F1XJuV1V-BU&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)

Сначала реализуем фронтенд с помощью Lovable.

Можно выбрать другой инструмент: генератор проектов вроде Bolt или ИИ-ассистент, например Cursor, Claude Code, Codex, Copilot или Antigravity.

Для Lovable я использовал такой промпт (оригинал):

> create the snake game with two models: pass-through and walls. prepare to make it multiplayers - we will have this functionality: leaderboard and watching (me following other players that currently play). add mockups for that and also for log in.
> everything should be interactive - I can log in, sign up, see my username when I'm logged in, see leaderboard, see
> other people play (in this case just implement some playing logic yourself as if somebody is playing) 
> make sure that all the logic is covered with tests 
> 
> don't implement backend, so everything is mocked. But centralize all the calls to the backend in one place

Перевод промпта:

> Создай игру «Змейка» с двумя режимами: проход сквозь границы и стены. Подготовь её к многопользовательскому режиму: нужны таблица лидеров и наблюдение за игроками, которые сейчас играют. Добавь макеты для этих функций и для входа.
> Всё должно быть интерактивным: я могу войти, зарегистрироваться, видеть своё имя пользователя после входа, смотреть таблицу лидеров и игру других людей (пока реализуй игровую логику сам, как будто кто-то играет).
> Убедись, что вся логика покрыта тестами.
> Бэкенд не реализуй, всё должно быть имитацией. Но собери все обращения к бэкенду в одном месте.

Создайте фронтенд и разместите его на Github.


<a id="optional-connecting-antigravity-to-codespaces"></a>
## (Необязательно) Подключение Antigravity к Codespaces

[🎥 Видео](https://www.youtube.com/watch?v=D7vrd8SJENg&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


В остальных видео я буду использовать 
[Google Antrigravity](https://antigravity.google/) как ИИ-ассистента и [Codespaces](https://github.com/features/codespaces) как окружение.

Если хотите такую же конфигурацию, в этом разделе я покажу, как подключить Antigravity к Codespaces. Инструкции подходят и для Cursor.

Если используете Copilot или Codex, это не нужно: просто подключайтесь к Codespaces через VS Code.

При локальном запуске это тоже не нужно. Но потребуется установить NodeJS, Python и Docker (в Codespaces они уже есть). 

Шаг 1: установите GitHub CLI

* Скачать: https://github.com/cli/cli/releases

Шаг 2: выполните аутентификацию

```bash
# Authenticate with GitHub using SSH
gh auth login
# Select: SSH protocol and your existing SSH key for GitHub
# Follow the remaining prompts

# authenticate for codespaces
gh auth refresh -h github.com -s codespace
```

Шаг 3: создайте и используйте Codespace

```bash
gh codespace create
# Note the ID that's generated (e.g., expert-doodle-wr7wg9p5gqcgggw)
```

Шаг 4: подключитесь по SSH

```bash
gh codespace ssh -c expert-doodle-wr7wg9p5gqcgggw
```

Затем получите конфигурацию SSH:

```bash
gh codespace ssh --config -c expert-doodle-wr7wg9p5gqcgggw
```

Добавьте вывод в `~/.ssh/config`

**Если возникла ошибка "cannot find the key" («не удаётся найти ключ»):**

```bash
ssh-keygen -t ed25519 -f ~/.ssh/codespaces.auto
ssh <codespace-name>
```

Шаг 5: используйте с Antigravity

- Подключитесь к codespace через режим удалённого SSH-подключения в Antigravity
- Откройте папку проекта в `/workspaces/`

Шаг 6: по завершении остановите Codespace

```bash
gh cs stop -c expert-doodle-wr7wg9p5gqcgggw
```


<a id="running-and-testing-the-frontend-locally"></a>
## Локальный запуск и тестирование фронтенда

* [🎥 Видео №1 (начиная с 12:00)](https://www.youtube.com/watch?v=D7vrd8SJENg&t=719&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)
* [🎥 Видео №2 о тестах](https://www.youtube.com/watch?v=xbsV_RarTUM&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


Запустите приложение:

```bash
# Install dependencies and start the development server
npm install
npm run dev
```

Запустите тесты:

```bash
npm test
```


<a id="creating-the-backend"></a>
## Создание бэкенда

[🎥 Видео](https://www.youtube.com/watch?v=jHVbbw-v_zY&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


Сначала перенесите все файлы фронтенда в отдельную папку:

```bash
mkdir frontend
mv * frontend/
```

Затем сгенерируем спецификации OpenAPI

Спецификации OpenAPI дают стандартный способ описания REST API. Это позволяет автоматически генерировать документацию, клиентский и серверный код, а также поддерживать согласованность контракта между фронтендом и бэкендом.

Создадим их (оригинал промпта):

> analyse the content of the client and create an OpenAPI specs based on what it needs. later we want to implement backend based on these specs

Перевод промпта:

> Проанализируй содержимое клиента и создай спецификации OpenAPI на основе его потребностей. Позже мы хотим реализовать бэкенд по этим спецификациям.

Теперь можно создать проект бэкенда:

```bash
pip install uv
mkdir backend && cd backend
uv init
```

ИИ-агенты не знают, как правильно пользоваться `uv` (это относительно новый инструмент). Поэтому нужно объяснить им, как его использовать. Обычно для этого служит файл `AGENTS.md`.

Создадим его (оригинал): 

```markdown
For backend development, use `uv` for dependency management.

Useful Commands

    # Sync dependencies from lockfile
    uv sync

    # Add a new package
    uv add <PACKAGE-NAME>

    # Run Python files
    uv run python <PYTHON-FILE>
```

Перевод инструкций для AGENTS.md (команды сохранены):

```markdown
Для разработки бэкенда используйте `uv` для управления зависимостями.

Полезные команды

    # Синхронизировать зависимости из lock-файла
    uv sync

    # Добавить новый пакет
    uv add <PACKAGE-NAME>

    # Запустить файлы Python
    uv run python <PYTHON-FILE>
```


**Примечание:** на момент создания курса Antigravity не следует автоматически инструкциям из AGENTS.md. Пока это не исправят, явно просите его соблюдать эти правила.

Теперь создадим бэкенд. Оригинал промпта:

> based on the OpenAPI specs, create fastapi backend 
> for now use a mock database, which we will later replace with a real one
> create tests to make sure the implementation works
> 
> follow the guidelines in AGENTS.md

Перевод промпта:

> На основе спецификаций OpenAPI создай бэкенд FastAPI.
> Пока используй имитацию базы данных, позже заменим её настоящей.
> Создай тесты, чтобы проверить работоспособность реализации.
> Следуй правилам в AGENTS.md.

Дополнительно можно попросить ИИ реализовать скрипт `verify_api.py`, который тестирует работающий сервер и проверяет корректность всех эндпоинтов.


<a id="integrating-frontend-and-backend"></a>
## Интеграция фронтенда и бэкенда

[🎥 Видео](https://www.youtube.com/watch?v=Y46XU8MYnmY&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


Бэкенд готов. Подключим его к фронтенду. Оригинал промпта:

> Make frontend use backend. use OpenAPI specs for guidance
> follow the guidelines in AGENTS.md

Перевод промпта:

> Подключи фронтенд к бэкенду. Ориентируйся на спецификации OpenAPI.
> Следуй правилам в AGENTS.md.

Нужен и способ запускать их одновременно. Оригинал промпта: 

> How can I run both frontend and backend at the same time? 
> Let's use concurrently instead of our own script

Перевод промпта:

> Как запускать фронтенд и бэкенд одновременно?
> Давай используем concurrently вместо собственного скрипта.

Если возникла ошибка, просто попросите ИИ её исправить. Например, при подготовке материала я пытался создать аккаунт в приложении и получал сообщение "Not Found". Вот как я это исправил (оригинал промпта):

> I tried creating an account and it says Not Found
> write a test on backend to reproduce it, fix it, and make sure the frontend works fine too

Перевод промпта:

> Я попробовал создать аккаунт и получил Not Found.
> Напиши тест бэкенда, воспроизводящий ошибку, исправь её и убедись, что фронтенд тоже работает нормально.

<a id="database-support"></a>
## Поддержка базы данных

* [🎥 Видео (добавление базы данных)](https://www.youtube.com/watch?v=q8r_ugvQxEE&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)
* [🎥 Видео (интеграционные тесты)](https://www.youtube.com/watch?v=kfEjwDD5Vv8&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)

Наш бэкенд использует имитацию базы данных. Перейдём к настоящей. Оригинал промпта:
> now for backend let's use postgres and sqlite database (via sqlalchemy) 
> follow the guidelines in AGENTS.md

Перевод промпта:

> Теперь используем для бэкенда базы данных postgres и sqlite через sqlalchemy.
> Следуй правилам в AGENTS.md.

Не забудьте и о тестах слоя базы данных (оригинал промпта):

> let's also add some integration tests (using sqlite) to make sure things work 
> put the integration test in a separate folder tests_integration

Перевод промпта:

> Добавим интеграционные тесты с sqlite, чтобы убедиться, что всё работает.
> Положи интеграционный тест в отдельную папку tests_integration.


<a id="containerization-with-docker"></a>
## Контейнеризация с Docker

[🎥 Видео (контейнеризация)](https://www.youtube.com/watch?v=mftbW-QXFRI&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


С SQLite всё работает, но как насчёт Postgres? Упакуем всё в контейнеры
и добавим поддержку Postgres (оригинал промпта): 

> right now we have frontend, backend, and database (sqlite)
> 
> let's put everything into docker compose and use postgres there. we can serve frontend with nginx or whatever you recommend

Перевод промпта:

> Сейчас у нас есть фронтенд, бэкенд и база данных sqlite.
> Поместим всё в docker compose и используем там postgres. Фронтенд можно раздавать через nginx или другой вариант, который ты порекомендуешь.

Запустите:

```bash
docker-compose up --build
```

По завершении остановите:

```bash
docker-compose down
```


<a id="deloyment"></a>
## Развёртывание

[🎥 Видео](https://www.youtube.com/watch?v=Y7OnXqYs30k&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)

Для развёртывания нам нужен один контейнер с фронтендом и бэкендом.
Попросим ИИ объединить их (оригинал промпта):

> For deployment we need to put together backend
> and frontend in one container. let's do that

Перевод промпта:

> Для развёртывания нужно объединить бэкенд
> и фронтенд в одном контейнере. Давай сделаем это.

Затем спросите (оригинал):

> I want to deploy it to the cloud now. what are the options

Перевод промпта:

> Теперь я хочу развернуть приложение в облаке. Какие есть варианты?

Мой ответ (оригинал):

> let's go with render

Перевод промпта:

> Выберем render.

<a id="cicd"></a>
## CI/CD

[🎥 Видео](https://www.youtube.com/watch?v=lcmP9YCUmYw&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


Оригинал промпта:

> I want to create a CI/CD pipeline with github actions with two parts
> 
> - first we run tests (frontend + backend)
> - if tests pass, I want to deploy the update to render

Перевод промпта:

> Я хочу создать пайплайн CI/CD в github actions из двух частей:
> - сначала запускаем тесты фронтенда и бэкенда;
> - если тесты проходят, разворачиваем обновление на render.

Также добавим интеграционные тесты (оригинал промпта):

> let's also run integration tests for backend separately before running deployment

Перевод промпта:

> Давай также отдельно запустим интеграционные тесты бэкенда перед развёртыванием.

Если вы… [В исходнике фраза обрывается.]


<a id="cleanup"></a>
## Очистка ресурсов

Не забудьте остановить codespaces:


```bash
gh cs stop -c <CODESPACE_NAME>
```

Если вы развернули приложение в облаке, не забудьте удалить инстансы, когда они больше не нужны.


<a id="homework"></a>
## Домашнее задание

- [Домашнее задание 2026](../../2026/homework/02-development/homework.md)


<a id="community-notes"></a>
## Заметки сообщества

Вы делали заметки? Ими можно поделиться здесь

* Добавьте ссылку на свои заметки выше этой строки

> **Примечание к навигации:** в исходнике ссылка `../../2026/02-development/homework.md` пропускает каталог `homework` и не существует в снимке `9b9527b`. Ссылка выше исправлена на проверенный путь `../../2026/homework/02-development/homework.md`; содержание задания не изменялось.
