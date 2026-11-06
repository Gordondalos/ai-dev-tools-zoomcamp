<a id="homework-1-ai-native-developer-workflow"></a>

# Домашнее задание 1: Рабочий процесс разработчика с ИИ

[Оригинал](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/b47dff65161c878d095e288e9f9e5b907f5aa3c6/cohorts/2026/homework/01-ai-native-workflow/homework.md)

В этом домашнем задании мы создадим приложение с помощью ИИ. Но вместо готовой спецификации вы получите расплывчатую идею, самостоятельно превратите её в спецификацию, а затем реализуете приложение на Django.

Можно использовать любого агента для программирования: Claude Code, Codex CLI, Gemini CLI, Cursor, Aider, GitHub Copilot и других. Выберите одного и работайте с ним на протяжении всего задания. С чат-инструментами пришлось бы постоянно копировать код туда и обратно, поэтому рекомендуем агента, который умеет редактировать файлы и запускать команды прямо в репозитории с домашним заданием.

Для начала понадобится только Python (также рекомендуем использовать `uv`). Знать Python или Django для выполнения этого задания не обязательно.

<a id="homework-idea"></a>

## Идея домашнего задания

Начнём с очень расплывчатой идеи:

> Инструмент для распределения совместных домашних обязанностей

Других требований мы не задаём, поэтому у большинства из вас получатся разные решения.

В этом задании мы хотим превратить это расплывчатое описание в чёткую спецификацию.

<a id="question-1-select-your-coding-agent"></a>

## Вопрос 1: Выберите агента для программирования

Можно использовать любого агента для программирования. Какого вы выбрали?

<a id="question-2-turn-the-idea-into-a-spec"></a>

## Вопрос 2: Превратите идею в спецификацию

Откройте чат с ассистентом и обсудите идею, используя примерно такой запрос:

```text
I want to build a tool for managing shared household chores.

Help me set the scope for this homework precisely. I want to brainstorm with you
and understand how the tool should work. Give me options.

Ask me one question at a time and keep your output short.
```

Перевод примера:

> Я хочу создать инструмент для распределения совместных домашних обязанностей.
>
> Помоги мне точно определить объём работы для этого домашнего задания. Я хочу обсудить с тобой идеи и понять, как должен работать инструмент. Предложи варианты.
>
> Задавай по одному вопросу за раз и отвечай кратко.

Ответьте на его вопросы, а затем попросите сохранить всё в файл Markdown.

Какие 2–4 функции вошли в итоговую спецификацию?

<a id="github-repository"></a>

## Репозиторий GitHub

Создайте пустой репозиторий GitHub и клонируйте его локально. Создайте в нём два файла:

- `.gitignore`
- `README.md`
- `_docs/plan.md` с планом

*Примечание переводчика: в оригинале сказано «два файла», но в списке приведены три.*

Создайте коммит и отправьте его в удалённый репозиторий.

<a id="question-3-django-project"></a>

## Вопрос 3: Проект Django

Для этого задания мы будем использовать Django.

Попросите агента установить Django, создать проект и приложение для него. На определённом этапе вам понадобится включить созданное приложение в проект.

Какой файл нужно для этого отредактировать?

- `settings.py`
- `manage.py`
- `urls.py`
- `wsgi.py`

В этом и следующих вопросах можно попросить ассистента для программирования выбрать правильный вариант.

<a id="question-4-backlog"></a>

## Вопрос 4: Бэклог

Затем передайте агенту `plan.md` и попросите предложить небольшой бэклог задач для реализации приложения на Django. Сохраните результат в `backlog.md`.

Какую задачу агент поставил первой в бэклоге?

<a id="question-5-first-version"></a>

## Вопрос 5: Первая версия

Реализуйте первые несколько задач. Просто откройте агента и напишите:

```
Implement task #1 from backlog.md
```

Перевод примера:

> Реализуй задачу № 1 из `backlog.md`.

Запустите сервер. Какую команду вы используете для запуска сервера разработки Django?

- `uv run python manage.py runserver`
- `uv run django-admin startserver`
- `python manage.py start`
- `uv run python app.py runserver`

<a id="question-6-tests"></a>

## Вопрос 6: Тесты

После реализации нескольких задач из бэклога убедимся, что код покрыт тестами.

- Скажите агенту, что мы хотим покрыть код тестами
- Спросите, какие сценарии стоит проверить
- Убедитесь, что предложенные сценарии имеют смысл
- Поручите агенту реализовать и запустить тесты

Какую команду вы используете для запуска тестов в терминале?

- `pytest`
- `uv run python manage.py test`
- `python -m django run_tests`
- `django-admin test`

<a id="submission"></a>

## Сдача задания

Отправьте домашнее задание здесь: https://courses.datatalks.club/ai-dev-tools-2026/homework/hw1

В форме сдачи задания укажите ссылку на созданный вами репозиторий.

<a id="learning-in-public"></a>

## Учимся публично

Мы призываем всех делиться тем, чему они научились. Это называется «обучение на публике» (learning in public). Подробнее о том, почему это важно: https://datatalks.club/blog/benefits-of-learning-in-public.html

Обучение на публике — один из самых эффективных способов ускорить свой рост. Вот почему:

1. Ответственность: рассказывая о своём прогрессе, вы укрепляете намерение продолжать и поддерживаете мотивацию
2. Обратная связь: сообщество может дать ценные советы и указать на ошибки
3. Знакомства: вы находите единомышленников и потенциальных партнёров для совместной работы
4. Документирование: ваши публикации становятся учебным дневником, к которому можно вернуться
5. Возможности: работодатели и клиенты нередко находят талантливых специалистов благодаря их публичному обучению

Не стремитесь к совершенству. Все с чего-то начинают, а людям нравится следить за настоящим процессом обучения!

<a id="example-post-for-linkedin"></a>

### Пример публикации для LinkedIn:

```
🚀 Week 1 of AI Dev Tools Zoomcamp by @DataTalksClub complete!

Turned a vague one-line idea into a spec, broke it into a backlog, and let an AI coding agent build a Django app for managing shared household chores!

Today I learned how to:

✅ Turn a vague idea into a written spec
✅ Break a spec into a backlog of tasks
✅ Set up a Django project and app with AI
✅ Implement backlog tasks one at a time with a coding agent
✅ Cover the app with tests

Here's my repo: <LINK>

Following along with this amazing course - who else is exploring AI development tools?

You can sign up here: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/
```

Перевод примера:

> 🚀 Первая неделя AI Dev Tools Zoomcamp от @DataTalksClub завершена!
>
> Превратил расплывчатую идею из одной строки в спецификацию, разбил её на бэклог задач и поручил ИИ-агенту для программирования создать на Django приложение для распределения совместных домашних обязанностей!
>
> Сегодня я научился:
>
> ✅ Превращать расплывчатую идею в письменную спецификацию
> ✅ Разбивать спецификацию на бэклог задач
> ✅ Создавать проект и приложение Django с помощью ИИ
> ✅ Последовательно реализовывать задачи из бэклога с агентом для программирования
> ✅ Покрывать приложение тестами
>
> Мой репозиторий: `<LINK>`
>
> Прохожу этот замечательный курс. Кто ещё изучает ИИ-инструменты для разработки?
>
> Присоединиться можно здесь: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/

<a id="example-post-for-twitterx"></a>

### Пример публикации для Twitter/X:

```
🤖 Built a Django app with AI in @Al_Grigor's AI Dev Tools Zoomcamp!

📝 Spec first, code second
🗂️ Backlog-driven implementation
✨ Household chores app from scratch
✅ Tests

My repo: <LINK>

Zero Django knowledge → working app in one session!

Join me: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/
```

Перевод примера:

> 🤖 Создал приложение Django с помощью ИИ на AI Dev Tools Zoomcamp от @Al_Grigor!
>
> 📝 Сначала спецификация, потом код
> 🗂️ Реализация по задачам из бэклога
> ✨ Приложение для домашних обязанностей с нуля
> ✅ Тесты
>
> Мой репозиторий: `<LINK>`
>
> Нулевые знания Django → работающее приложение за одну сессию!
>
> Присоединяйтесь: https://github.com/DataTalksClub/ai-dev-tools-zoomcamp/
