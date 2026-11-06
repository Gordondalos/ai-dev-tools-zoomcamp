> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/docs/2026-syllabus-proposal.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

<a id="ai-dev-tools-zoomcamp-2026-syllabus-proposal"></a>
# Предложение программы AI Dev Tools Zoomcamp 2026

> **Примечание к переводу:** это черновик предложения за июль 2026 года, а не текущая утверждённая программа курса. Содержание и сведения об инструментах отражают исходный документ. Исполняемый код, команды, идентификаторы, пути, числа и URL сохранены; для естественно-языковых примеров и промптов в блоках ниже рядом с оригиналом дан перевод.

**Подготовлено для:** DataTalks.Club / AI Dev Tools Zoomcamp  
**Дата:** 2026-07-05  
**Статус:** черновое предложение для обсуждения с преподавателями и участниками разработки курса  
**Рекомендуемое название курса:** **AI Dev Tools Zoomcamp: разработка ПО с ИИ в основе рабочего процесса**

---

<a id="1-executive-summary"></a>
## 1. Краткое резюме

В нынешнем AI Dev Tools Zoomcamp уже есть сильные составляющие: практический обзор ИИ-инструментов для разработчиков, создание full-stack-приложения от начала до конца, MCP, агенты для программирования, CI/CD и low-code-автоматизация. В версии 2026 года курс стоит переориентировать на более устойчивый рабочий процесс разработчика:

> **Выбирайте подходящий ИИ-инструмент, давайте ему нужный контекст, расширяйте его необходимыми возможностями и безопасно выпускайте результат, используя ревью, аудит, меры безопасности и DevOps-контроль.**

Рекомендуемая структура курса 2026 года состоит из **четырёх модулей**:

1. **Рабочий процесс разработчика с ИИ в основе**  
   Сравнить основные категории ИИ-инструментов для разработчиков и научить проектированию контекста.

2. **Создание и выпуск full-stack-приложения с помощью ИИ**  
   Сохранить сильный модуль сквозной разработки приложения: продуктовая спецификация, фронтенд, OpenAPI, бэкенд, база данных, Docker, развёртывание и CI/CD.

3. **Возможности агентов для программирования: MCP, навыки, плагины и собственные агенты**  
   Превратить прежний модуль, сосредоточенный на MCP, в более широкий модуль о расширении и настройке агентов для программирования. MCP становится одной из возможностей наряду с повторно используемыми рабочими процессами, хуками, субагентами, плагинами/расширениями и собственными агентами. Прежде всего модуль должен быть независимым от инструментов; Claude Code, Codex, OpenCode, Cursor, GitHub Copilot, Aider и подобные инструменты можно использовать как примеры.

4. **ИИ-инструменты с открытым исходным кодом для безопасности, аудита и DevOps**  
   Ограничить модуль ИИ-инструментами с открытым исходным кодом для безопасности, аудита и DevOps, поскольку именно здесь нужен тщательно подобранный стек. Без оценивания LLM. Без универсальных агентов для программирования. Без отдельного модуля генерации тестов. Сосредоточиться на аудите PR, оркестрации инструментов безопасности, проверке безопасности MCP/агентов, диагностике Kubernetes, расследовании инцидентов и управлении использованием ИИ-инструментов.

Логика курса становится такой:

**Оригинал:**

```text
Module 1: Learn the AI tool landscape and context engineering
Module 2: Build and deploy a real app with AI assistance
Module 3: Extend coding agents around the app
Module 4: Audit, secure, and operate the AI-assisted workflow
```

**Перевод:**

```text
Модуль 1: изучить обзор ИИ-инструментов и проектирование контекста
Модуль 2: создать и развернуть реальное приложение с помощью ИИ
Модуль 3: расширить агентов для программирования вокруг приложения
Модуль 4: проверить, защитить и эксплуатировать рабочий процесс с помощью ИИ
```

---

<a id="2-course-design-principles"></a>
## 2. Принципы построения курса

<a id="21-the-course-should-teach-workflows-not-tool-worship"></a>
### 2.1 Курс должен учить рабочим процессам, а не поклонению инструментам

Инструменты быстро меняются. В курсе по-прежнему нужно упоминать важные инструменты, но долговечный навык заключается в понимании того, какая категория инструментов подходит для задачи.

Например:

**Оригинал:**

```text
Use chat assistants when you need thinking, explanation, design, or review.
Use terminal agents when you need repo edits and command execution.
Use agentic IDEs when you need interactive coding inside an editor.
Use bootstrappers when you need prototypes quickly.
Use agent extension capabilities when a repeated workflow should become a reusable skill/tool/agent.
Use security/audit/DevOps AI tools when code is ready to be reviewed, diagnosed, or operated.
```

**Перевод:**

```text
Используйте чат-ассистентов, когда нужны размышление, объяснение, проектирование или ревью.
Используйте терминальных агентов, когда нужны правки в репозитории и выполнение команд.
Используйте агентные IDE, когда нужна интерактивная разработка внутри редактора.
Используйте генераторы начальных проектов, когда нужно быстро получить прототип.
Используйте возможности расширения агентов, когда повторяющийся рабочий процесс пора превратить в повторно используемый навык/инструмент/агент.
Используйте ИИ-инструменты безопасности/аудита/DevOps, когда код готов к ревью, диагностике или эксплуатации.
```

<a id="22-the-course-should-be-practical-and-repo-centered"></a>
### 2.2 Курс должен быть практическим и строиться вокруг репозитория

Результатом каждого модуля должны быть файлы в репозитории учащегося. Так выполненная работа становится видимой и доступной для проверки.

Репозиторий итогового проекта должен включать, например, такие материалы:

```text
AGENTS.md
CLAUDE.md
product-spec.md
openapi.yaml
docker-compose.yml
.github/workflows/
agent-capabilities/
agent-hooks/
mcp-server/
security/
ops/
docs/
```

<a id="23-module-3-should-be-tool-agnostic-first"></a>
### 2.3 Модуль 3 прежде всего должен быть независимым от инструментов

Модуль 3 должен объяснять возможности агентов для программирования в общем виде. Для конкретных демонстраций можно использовать один или несколько инструментов, но понятия не должны зависеть от одного продукта:

**Оригинал:**

```text
instructions
context
tools
permissions
reusable workflows
specialized agents
extension packaging
custom agent loops
audit trails
```

**Перевод:**

```text
инструкции
контекст
инструменты
разрешения
повторно используемые рабочие процессы
специализированные агенты
упаковка расширений
собственные циклы работы агента
аудиторские следы
```

Разные инструменты по-разному называют эти возможности. Например, один инструмент может называть повторно используемый рабочий процесс навыком, а другой — командой, правилом, рецептом, промптом или расширением. Благодаря этому модуль останется полезным для пользователей Claude Code, Codex, OpenCode, Cursor, GitHub Copilot, Aider, Windsurf, Zed, Antigravity и будущих инструментов.

<a id="24-module-4-should-be-narrower-and-stricter"></a>
### 2.4 Модуль 4 должен быть более узким и строгим по рамкам

Ограничения модуля 4 намеренные:

**Оригинал:**

```text
Only open-source AI tools.
Only security / audit / DevOps.
No general coding agents.
No LLM application evals.
No test generation as the main topic.
```

**Перевод:**

```text
Только ИИ-инструменты с открытым исходным кодом.
Только безопасность / аудит / DevOps.
Без универсальных агентов для программирования.
Без оценивания LLM-приложений.
Генерация тестов не является основной темой.
```

Это сохраняет фокус модуля и позволяет не дублировать модули 1–3.

---

<a id="3-high-level-2026-syllabus"></a>
## 3. Общая программа на 2026 год

<a id="module-1-ai-native-developer-workflow"></a>
### Модуль 1: Рабочий процесс разработчика с ИИ в основе

Сравните современные ИИ-инструменты для разработчиков: чат-ассистенты, терминальные агенты для программирования, агентные IDE / настольные рабочие среды, облачные агенты и генераторы начальных проектов. Научитесь выбирать подходящий инструмент для задачи и давать ИИ-инструментам полезный контекст проекта.

**Результат:** настроить репозиторий для разработки с помощью ИИ и реализовать одну небольшую функцию с использованием дисциплинированного ИИ-процесса.

<a id="module-2-build-and-ship-an-ai-assisted-full-stack-app"></a>
### Модуль 2: Создание и выпуск full-stack-приложения с помощью ИИ

Создайте приложение от начала до конца с помощью ИИ: продуктовая спецификация, прототип фронтенда, контракт OpenAPI, бэкенд на FastAPI или Django, база данных, тесты, Docker, развёртывание и CI/CD.

**Результат:** развёрнутое full-stack-приложение с тестами, настройкой Docker, контрактом OpenAPI и воспроизводимым процессом разработки.

<a id="module-3-coding-agent-capabilities-mcp-skills-plugins-and-custom-agents"></a>
### Модуль 3: Возможности агентов для программирования: MCP, навыки, плагины и собственные агенты

Узнайте, как расширяют и настраивают современных агентов для программирования. Изучите инструкции проекта, MCP, повторно используемые рабочие процессы/навыки, хуки, специализированных субагентов, плагины/расширения и собственных агентов независимо от конкретного инструмента, с примерами из современных агентов для программирования.

**Результат:** пакет расширений агента для приложения из модуля 2, включающий инструкции проекта, собственный навык, субагента, хук, инструмент/сервер MCP и небольшой плагин либо собственного агента.

<a id="module-4-open-source-ai-tools-for-security-audit-and-devops"></a>
### Модуль 4: ИИ-инструменты с открытым исходным кодом для безопасности, аудита и DevOps

Узнайте, как использовать ИИ-инструменты с открытым исходным кодом в процессе подготовки к промышленной эксплуатации и самой эксплуатации. В центре внимания: ИИ-аудит PR, сканирование безопасности, доступное ИИ, проверка безопасности агентов/MCP/навыков, диагностика Kubernetes, расследование инцидентов и управление использованием ИИ-инструментов.

**Результат:** пакет усиления безопасности, аудита и DevOps для итогового проекта, включая результаты аудита PR, находки Semgrep MCP, отчёт Agent Scan, диагностику K8sGPT, необязательное резюме инцидента от HolmesGPT и политику использования ИИ-инструментов и данных.

---

<a id="module-1--ai-native-developer-workflow"></a>
# Модуль 1 — Рабочий процесс разработчика с ИИ в основе

<a id="4-module-1-positioning"></a>
## 4. Позиционирование модуля 1

Нынешний акцент на «вайб-кодинге» следует ослабить. Упоминать вайб-кодинг как культурный термин вполне уместно, но образ курса должен быть профессиональнее:

> **Рабочий процесс разработчика с ИИ в основе**: осознанно использовать ИИ-инструменты, учитывая контекст, ограничения, проверку и ревью человеком.

Основная проблема, которую решает модуль 1:

**Оригинал:**

```text
Developers are overwhelmed by tools.
They do not know when to use chat vs terminal vs IDE vs bootstrapper.
They do not know how to give the tool enough context.
They do not know how to review AI-generated changes.
```

**Перевод:**

```text
Разработчики перегружены множеством инструментов.
Они не знают, когда использовать чат, терминал, IDE или генератор начального проекта.
Они не знают, как дать инструменту достаточно контекста.
Они не знают, как проверять изменения, созданные ИИ.
```

Модуль 1 должен дать ориентиры.

---

<a id="5-tool-categories-for-module-1"></a>
## 5. Категории инструментов для модуля 1

<a id="51-chat-assistants"></a>
### 5.1 Чат-ассистенты

**Примеры**

**Оригинал:**

```text
ChatGPT
Claude
Gemini
Microsoft Copilot chat
DeepSeek chat
```

**Перевод:**

```text
ChatGPT
Claude
Gemini
чат Microsoft Copilot
чат DeepSeek
```

**Лучше всего подходят для**

**Оригинал:**

```text
architecture discussion
explaining code
debugging ideas
design trade-offs
writing specs
reviewing pasted diffs
generating small snippets
learning unfamiliar libraries
```

**Перевод:**

```text
обсуждение архитектуры
объяснение кода
идеи для отладки
компромиссы при проектировании
написание спецификаций
ревью вставленных изменений (diff)
генерация небольших фрагментов кода
изучение незнакомых библиотек
```

**Слабые стороны**

**Оригинал:**

```text
weak repo awareness unless context is pasted/uploaded
easy to produce plausible but unverified answers
manual copy/paste between chat and repo
not ideal for multi-file edits
```

**Перевод:**

```text
слабое понимание репозитория, если контекст не вставлен или не загружен
легко получить правдоподобные, но непроверенные ответы
ручное копирование и вставка между чатом и репозиторием
не лучший вариант для правок в нескольких файлах
```

**Учебная демонстрация**

Попросите три чат-ассистента решить одну и ту же задачу:

**Оригинал:**

```text
"Here is a small FastAPI endpoint and its failing test. Explain the bug, propose a fix, and suggest one additional test."
```

**Перевод:**

```text
«Вот небольшой эндпоинт FastAPI и его падающий тест. Объясни ошибку, предложи исправление и один дополнительный тест».
```

Затем сравните:

**Оригинал:**

```text
quality of reasoning
specificity of the fix
test suggestions
hallucinated assumptions
need for repo context
```

**Перевод:**

```text
качество рассуждений
конкретность исправления
предложения тестов
выдуманные предположения
потребность в контексте репозитория
```

---

<a id="52-terminal-based-coding-agents"></a>
### 5.2 Терминальные агенты для программирования

**Примеры**

```text
Claude Code
Codex CLI
Gemini CLI
Aider
```

**Лучше всего подходят для**

**Оригинал:**

```text
working in an existing repo
multi-file edits
running tests
fixing lint/type errors
small refactors
debugging from logs
creating commits
```

**Перевод:**

```text
работа в существующем репозитории
правки в нескольких файлах
запуск тестов
исправление ошибок линтера и типов
небольшой рефакторинг
отладка по логам
создание коммитов
```

**Слабые стороны**

**Оригинал:**

```text
can run commands and modify many files
requires permission discipline
must review diffs frequently
can over-edit if instructions are vague
may spend tokens/cost on irrelevant context
```

**Перевод:**

```text
могут запускать команды и изменять много файлов
требуют дисциплины в управлении разрешениями
необходимо часто просматривать diff
при расплывчатых инструкциях могут вносить чрезмерные изменения
могут тратить токены и деньги на нерелевантный контекст
```

**Учебная демонстрация**

Используйте ту же задачу в репозитории, что и для чат-ассистентов:

**Оригинал:**

```text
"Add a leaderboard filter, update the tests, run the tests, and show the diff."
```

**Перевод:**

```text
«Добавь фильтр таблицы лидеров, обнови тесты, запусти их и покажи diff».
```

Сравните:

**Оригинал:**

```text
how it finds relevant files
how many files it edits
how it runs tests
how easy the diff is to review
```

**Перевод:**

```text
как агент находит нужные файлы
сколько файлов он редактирует
как запускает тесты
насколько удобно проверять diff
```

---

<a id="53-agentic-ides--desktop-agent-workbenches"></a>
### 5.3 Агентные IDE / настольные рабочие среды для агентов

Это лучшее название для категории «настольных инструментов».

**Примеры**

**Оригинал:**

```text
Cursor
Windsurf
VS Code Copilot agent mode
Zed agent panel
Claude Code Desktop / Web
Google Antigravity
Z.ai ZCode
Anthropic Cowork-style graphical agents
```

**Перевод:**

```text
Cursor
Windsurf
агентный режим VS Code Copilot
панель агента Zed
Claude Code Desktop / Web
Google Antigravity
Z.ai ZCode
графические агенты в стиле Anthropic Cowork
```

**Примечания**

- Некоторые инструменты этой категории являются полноценными IDE.
- Некоторые представляют собой настольные или веб-рабочие среды.
- Некоторые являются графическими версиями терминальных агентов.
- Некоторые скорее «менеджеры агентов», чем редакторы.

Категория важнее точного списка. Курс 2026 года должен научить учащихся задавать вопросы:

**Оригинал:**

```text
Does this tool see my repo?
Can it edit files?
Can it run commands?
Can it use the browser?
Can it show a diff?
Can it make a PR?
Can I control permissions?
Can I understand what context it used?
Can I control cost?
```

**Перевод:**

```text
Видит ли этот инструмент мой репозиторий?
Может ли он редактировать файлы?
Может ли запускать команды?
Может ли использовать браузер?
Может ли показать diff?
Может ли создать PR?
Могу ли я управлять разрешениями?
Могу ли я понять, какой контекст он использовал?
Могу ли я контролировать расходы?
```

**Лучше всего подходят для**

**Оригинал:**

```text
interactive coding
UI changes
exploring a repo visually
reviewing diffs
running app and browser checks
working with project files and terminal together
```

**Перевод:**

```text
интерактивное программирование
изменения интерфейса
визуальное изучение репозитория
ревью diff
запуск проверок приложения и проверок в браузере
одновременная работа с файлами проекта и терминалом
```

**Слабые стороны**

**Оригинал:**

```text
editor lock-in
hidden context behavior
rate-limit/pricing surprises
too much autonomy if not reviewed
tool behavior changes quickly
```

**Перевод:**

```text
зависимость от редактора
скрытые механизмы работы с контекстом
неожиданные лимиты запросов и расходы
слишком большая автономность без проверки
быстро меняющееся поведение инструмента
```

---

<a id="54-cloud--github-native-agents"></a>
### 5.4 Облачные агенты / агенты, встроенные в GitHub

**Примеры**

**Оригинал:**

```text
GitHub Copilot coding agent
Codex cloud-style workflows
Devin-like tools
Claude Code web/background sessions
```

**Перевод:**

```text
агент для программирования GitHub Copilot
облачные рабочие процессы в стиле Codex
инструменты, похожие на Devin
веб-сессии и фоновые сессии Claude Code
```

**Лучше всего подходят для**

**Оригинал:**

```text
assigning issues
background PRs
repo maintenance
documentation updates
low-to-medium complexity tasks
```

**Перевод:**

```text
поручение задач из трекера
создание PR в фоне
поддержка репозитория
обновление документации
задачи низкой и средней сложности
```

**Слабые стороны**

**Оригинал:**

```text
asynchronous review burden
unclear ownership
governance and auditability
cost
CI and permission boundaries
```

**Перевод:**

```text
нагрузка от асинхронного ревью
неясная ответственность
управление использованием и возможность аудита
стоимость
границы CI и разрешений
```

Эту категорию стоит упомянуть в модуле 1, но использовать её в обязательной лабораторной работе необязательно.

---

<a id="55-project-bootstrappers"></a>
### 5.5 Генераторы начальных проектов

**Примеры**

**Оригинал:**

```text
Lovable
Bolt
Replit Agent
v0-style UI generators
```

**Перевод:**

```text
Lovable
Bolt
Replit Agent
генераторы интерфейсов в стиле v0
```

**Лучше всего подходят для**

**Оригинал:**

```text
fast prototypes
landing pages
CRUD apps
UI mockups
demo apps
first draft of frontend
```

**Перевод:**

```text
быстрые прототипы
лендинги
CRUD-приложения
макеты интерфейса
демонстрационные приложения
первый набросок фронтенда
```

**Слабые стороны**

**Оригинал:**

```text
generated code may be messy
architecture may not match production needs
must migrate into a normal repo workflow
can hide complexity behind prompts
```

**Перевод:**

```text
сгенерированный код может быть неаккуратным
архитектура может не подходить для промышленной эксплуатации
необходим переход к обычному процессу работы с репозиторием
могут скрывать сложность за промптами
```

В модуле 2 эту категорию следует применить на практике.

---

<a id="6-module-1-content-flow"></a>
## 6. Последовательность тем модуля 1

<a id="lesson-11--the-ai-tool-landscape"></a>
### Урок 1.1 — Обзор ИИ-инструментов

**Цель:** дать студентам ориентиры.

**Темы**

**Оригинал:**

```text
chat assistants
terminal agents
agentic IDEs / desktop workbenches
cloud agents
bootstrappers
AI PR/review tools
security/audit/DevOps AI tools
```

**Перевод:**

```text
чат-ассистенты
терминальные агенты
агентные IDE / настольные рабочие среды
облачные агенты
генераторы начальных проектов
ИИ-инструменты для PR/ревью
ИИ-инструменты безопасности/аудита/DevOps
```

**Упражнение**

Студенты распределяют 10 инструментов по категориям и объясняют, когда использовали бы каждый из них.

---

<a id="lesson-12--the-same-task-in-four-tool-styles"></a>
### Урок 1.2 — Одна задача в четырёх типах инструментов

**Цель:** показать, как выбор инструмента меняет рабочий процесс.

**Задача**

**Оригинал:**

```text
Add a small feature to a simple repo:
- add a leaderboard filter
- update a UI label
- fix one failing test
- update README
```

**Перевод:**

```text
Добавьте небольшую функцию в простой репозиторий:
- добавьте фильтр таблицы лидеров
- обновите надпись в интерфейсе
- исправьте один падающий тест
- обновите README
```

Студенты пробуют как минимум два подхода:

**Оригинал:**

```text
chat assistant
terminal agent
agentic IDE
bootstrapper
```

**Перевод:**

```text
чат-ассистент
терминальный агент
агентная IDE
генератор начального проекта
```

**Материал для сдачи**

```text
docs/tool-comparison.md
```

Шаблон:

**Оригинал:**

```markdown
# Tool comparison

## Task

## Tool 1

- What I asked
- What it did well
- What it got wrong
- How I verified it

## Tool 2

- What I asked
- What it did well
- What it got wrong
- How I verified it

## Recommendation

For this kind of task, I would use...
```

**Перевод:**

```markdown
# Сравнение инструментов

## Задача

## Инструмент 1

- Что я попросил
- Что инструмент сделал хорошо
- В чём ошибся
- Как я проверил результат

## Инструмент 2

- Что я попросил
- Что инструмент сделал хорошо
- В чём ошибся
- Как я проверил результат

## Рекомендация

Для такого типа задач я бы использовал...
```

---

<a id="lesson-13--the-ai-development-loop"></a>
### Урок 1.3 — Цикл разработки с ИИ

Научите повторяемому циклу:

**Оригинал:**

```text
spec
→ context
→ plan
→ edit
→ run
→ test
→ inspect diff
→ review
→ commit
```

**Перевод:**

```text
спецификация
→ контекст
→ план
→ правка
→ запуск
→ тестирование
→ просмотр diff
→ ревью
→ коммит
```

Подчеркните:

**Оригинал:**

```text
do not start with "build the whole thing"
start with a small specification
ask for a plan
ask what files will change
make small commits
review the diff
run deterministic checks
```

**Перевод:**

```text
не начинайте с «сделай всё целиком»
начните с небольшой спецификации
попросите составить план
спросите, какие файлы будут изменены
делайте небольшие коммиты
проверяйте diff
запускайте детерминированные проверки
```

---

<a id="lesson-14--context-engineering"></a>
### Урок 1.4 — Проектирование контекста

Это должен быть один из важнейших уроков.

**Файлы, с которыми нужно познакомить студентов**

```text
AGENTS.md
CLAUDE.md
.github/copilot-instructions.md
.cursor/rules
product-spec.md
architecture.md
testing.md
security-checklist.md
openapi.yaml
runbook.md
```

**Ключевая идея**

Проектирование контекста не сводится к тому, чтобы «написать промпт получше». Оно означает:

**Оригинал:**

```text
make the project understandable to agents
make conventions explicit
make commands discoverable
make constraints visible
make review criteria repeatable
```

**Перевод:**

```text
сделать проект понятным для агентов
явно описать принятые соглашения
сделать команды легко обнаруживаемыми
сделать ограничения видимыми
сделать критерии ревью воспроизводимыми
```

---

<a id="lesson-15--human-in-the-loop-review"></a>
### Урок 1.5 — Ревью с участием человека

**Темы**

**Оригинал:**

```text
reviewing diffs
checking unrelated changes
detecting over-editing
checking tests
checking generated dependencies
checking auth and secrets
checking CI/deployment changes
knowing when to stop the agent
```

**Перевод:**

```text
ревью diff
проверка посторонних изменений
выявление чрезмерных правок
проверка тестов
проверка добавленных ИИ зависимостей
проверка аутентификации/авторизации и секретов
проверка изменений CI/развёртывания
понимание, когда остановить агента
```

**Материал для сдачи**

```text
docs/ai-usage-report.md
```

Шаблон:

**Оригинал:**

```markdown
# AI usage report

## What I delegated

## What I reviewed manually

## What I rejected

## What tests prove it works

## What I would not let the agent do automatically

## Cost / limits / friction

## What I learned
```

**Перевод:**

```markdown
# Отчёт об использовании ИИ

## Что я делегировал

## Что я проверил вручную

## Что я отклонил

## Какие тесты доказывают работоспособность

## Что я не разрешил бы агенту делать автоматически

## Стоимость / ограничения / неудобства

## Чему я научился
```

---

<a id="module-2--build-and-ship-an-ai-assisted-full-stack-app"></a>
# Модуль 2 — Создание и выпуск full-stack-приложения с помощью ИИ

<a id="7-module-2-positioning"></a>
## 7. Позиционирование модуля 2

Модуль 2 уже хорошо проработан и должен остаться основой практического курса. Он должен провести студентов от идеи до развёрнутого приложения.

Нынешняя структура приложения Snake по-прежнему хорошо подходит: оно наглядное, интерактивное и достаточно небольшое, чтобы довести его до конца, но при этом требует фронтенда, бэкенда, API, базы данных, тестов, Docker, развёртывания и CI/CD.

---

<a id="8-module-2-content-flow"></a>
## 8. Последовательность тем модуля 2

<a id="lesson-21--product-spec-and-acceptance-criteria"></a>
### Урок 2.1 — Продуктовая спецификация и критерии приёмки

Прежде чем использовать генератор начального проекта, студенты пишут:

**Оригинал:**

```text
product-spec.md
user stories
acceptance criteria
non-goals
technical constraints
```

**Перевод:**

```text
product-spec.md
пользовательские истории
критерии приёмки
то, что не входит в цели
технические ограничения
```

Пример:

**Оригинал:**

```markdown
# Product spec

## App

Snake Arena

## Users

- anonymous visitor
- registered player
- admin / maintainer

## Features

- play snake
- register/login
- leaderboard
- watch simulated games
- submit score

## Non-goals

- real-time multiplayer in this version
- payment
- social login

## Acceptance criteria

- user can play a local game
- user can submit score
- leaderboard shows top scores
- app works locally with Docker Compose
- backend tests pass
- frontend smoke test passes
```

**Перевод:**

```markdown
# Продуктовая спецификация

## Приложение

Snake Arena

## Пользователи

- анонимный посетитель
- зарегистрированный игрок
- администратор / сопровождающий проекта

## Функции

- играть в змейку
- регистрироваться/входить
- таблица лидеров
- смотреть симулированные игры
- отправлять результат

## Не входит в цели

- многопользовательская игра в реальном времени в этой версии
- оплата
- вход через социальные сети

## Критерии приёмки

- пользователь может играть локально
- пользователь может отправить результат
- таблица лидеров показывает лучшие результаты
- приложение работает локально с Docker Compose
- тесты бэкенда проходят
- дымовой тест фронтенда проходит
```

---

<a id="lesson-22--frontend-prototype"></a>
### Урок 2.2 — Прототип фронтенда

**Инструменты**

**Оригинал:**

```text
Lovable
Bolt
Replit Agent
Cursor / Claude Code / Codex as fallback
```

**Перевод:**

```text
Lovable
Bolt
Replit Agent
Cursor / Claude Code / Codex как запасной вариант
```

**Цель**

Сгенерировать начальный фронтенд, а затем перенести его в обычный процесс работы с репозиторием.

**Главная учебная мысль**

Прототип — не готовый продукт. Это первый набросок.

---

<a id="lesson-23--openapi-contract"></a>
### Урок 2.3 — Контракт OpenAPI

Студенты извлекают или пишут:

```text
openapi.yaml
```

Объясните:

**Оригинал:**

```text
API-first development
contract between frontend and backend
schema validation
generated clients/servers
how AI can hallucinate endpoints
```

**Перевод:**

```text
разработка от API (API-first)
контракт между фронтендом и бэкендом
валидация схемы
сгенерированные клиенты/серверы
как ИИ может выдумывать эндпоинты
```

---

<a id="lesson-24--backend-implementation"></a>
### Урок 2.4 — Реализация бэкенда

**Варианты**

```text
FastAPI
Django
Node/Express
```

Вероятно, основным вариантом стоит оставить FastAPI, поскольку он соответствует нынешним материалам.

**Темы**

**Оригинал:**

```text
backend scaffolding
uv dependency management
OpenAPI-guided implementation
mock DB first
tests first for key endpoints
```

**Перевод:**

```text
создание каркаса бэкенда
управление зависимостями через uv
реализация на основе OpenAPI
сначала имитация БД
сначала тесты для ключевых эндпоинтов
```

---

<a id="lesson-25--database-support"></a>
### Урок 2.5 — Поддержка базы данных

**Темы**

**Оригинал:**

```text
SQLite for local tests
Postgres for Docker/production
SQLAlchemy or Django ORM
migrations
integration tests
```

**Перевод:**

```text
SQLite для локальных тестов
Postgres для Docker/промышленной эксплуатации
SQLAlchemy или Django ORM
миграции
интеграционные тесты
```

---

<a id="lesson-26--containerization"></a>
### Урок 2.6 — Контейнеризация

**Материалы для сдачи**

```text
Dockerfile
docker-compose.yml
.env.example
```

---

<a id="lesson-27--deployment"></a>
### Урок 2.7 — Развёртывание

**Варианты**

```text
Render
Fly.io
Railway
Cloud Run
```

Основной вариант должен быть простым.

---

<a id="lesson-28--cicd"></a>
### Урок 2.8 — CI/CD

**Обязательно**

**Оригинал:**

```text
backend tests
frontend tests
integration tests if feasible
build check
deployment trigger
```

**Перевод:**

```text
тесты бэкенда
тесты фронтенда
интеграционные тесты, если осуществимо
проверка сборки
триггер развёртывания
```

---

<a id="9-module-2-deliverable"></a>
## 9. Итоговый результат модуля 2

К концу модуля 2 у каждого студента должны быть:

**Оригинал:**

```text
/product-spec.md
/AGENTS.md
/CLAUDE.md or equivalent
/frontend
/backend
/openapi.yaml
/docker-compose.yml
/tests
/.github/workflows
/docs/ai-usage-report.md
```

**Перевод:**

```text
/product-spec.md
/AGENTS.md
/CLAUDE.md или аналог
/frontend
/backend
/openapi.yaml
/docker-compose.yml
/tests
/.github/workflows
/docs/ai-usage-report.md
```

Приложение должно быть развёрнуто, а работа с репозиторием — воспроизводима.

---

<a id="module-3--coding-agent-capabilities-mcp-skills-plugins-and-custom-agents"></a>
# Модуль 3 — Возможности агентов для программирования: MCP, навыки, плагины и собственные агенты

<a id="10-module-3-positioning"></a>
## 10. Позиционирование модуля 3

Этот модуль должен учесть предложение второго преподавателя, сохранив общий характер:

> «Возможно, стоит изменить модуль 3 и добавить больше о возможностях агентов для программирования: MCP, навыки, плагины, создание собственных агентов. Я много пользуюсь Claude, поэтому темы ориентированы на него».

Это подходящее направление с точки зрения примеров и опыта преподавателя, но курс не должен превращаться в модуль исключительно о Claude.

Прежний модуль больше не должен быть «углублённым изучением MCP». Вместо этого:

> **Модуль 3 учит расширять, настраивать и ограничивать агентов для программирования, а также встраивать их в реальные рабочие процессы разработчиков.**

MCP остаётся важным, но становится частью более широкого набора возможностей.

---

<a id="11-module-3-mental-model"></a>
## 11. Концептуальная модель модуля 3

Каждая возможность агента для программирования относится к одной из этих категорий:

**Оригинал:**

```text
Instructions: What should the agent know and follow?
Context: What files, docs, schemas, and state can it see?
Tools: What can it do?
Permissions: What is it allowed to do automatically?
Workflows: What repeated procedures can be packaged?
Specialists: Which subagents handle specific tasks?
Distribution: How do teams share agent capabilities?
Custom agents: When do we build our own agent loop?
Audit: What did the agent do and why?
```

**Перевод:**

```text
Инструкции: что агент должен знать и соблюдать?
Контекст: какие файлы, документы, схемы и состояние ему доступны?
Инструменты: что он может делать?
Разрешения: что ему разрешено делать автоматически?
Рабочие процессы: какие повторяющиеся процедуры можно упаковать?
Специалисты: какие субагенты выполняют конкретные задачи?
Распространение: как команды делятся возможностями агентов?
Собственные агенты: когда мы создаём собственный цикл работы агента?
Аудит: что сделал агент и почему?
```

Конкретные инструменты реализуют эти понятия по-разному. Примеры:

**Оригинал:**

```text
project instructions        AGENTS.md, CLAUDE.md, repo rules, editor instructions
tool/context protocols      MCP, built-in tools, extension APIs
reusable workflows          skills, commands, prompts, recipes, rules
hooks and guardrails        lifecycle automation, command checks, formatting, logging
specialized agents          subagents, specialist agents, reviewer agents
extension packaging         plugins, extensions, shared config packs
custom agent loops          SDKs, scripts, CI jobs, internal apps
```

**Перевод:**

```text
инструкции проекта          AGENTS.md, CLAUDE.md, правила репозитория, инструкции редактора
протоколы инструментов/контекста MCP, встроенные инструменты, API расширений
повторно используемые процессы навыки, команды, промпты, рецепты, правила
хуки и защитные ограничения  автоматизация жизненного цикла, проверки команд, форматирование, логирование
специализированные агенты    субагенты, агенты-специалисты, агенты-ревьюеры
упаковка расширений          плагины, расширения, общие наборы конфигураций
собственные циклы агента     SDK, скрипты, задания CI, внутренние приложения
```

---

<a id="12-module-3-lesson-flow"></a>
## 12. Последовательность уроков модуля 3

<a id="lesson-31--how-coding-agents-work"></a>
## Урок 3.1 — Как работают агенты для программирования

<a id="goal"></a>
### Цель

Объяснить цикл работы агента.

<a id="concepts"></a>
### Понятия

**Оригинал:**

```text
user goal
context gathering
planning
tool calls
file edits
command execution
test execution
result inspection
iteration
diff/PR output
```

**Перевод:**

```text
цель пользователя
сбор контекста
планирование
вызовы инструментов
редактирование файлов
выполнение команд
запуск тестов
проверка результатов
повторение цикла
результат в виде diff/PR
```

<a id="lab"></a>
### Лабораторная работа

Используйте приложение из модуля 2. Попросите агента для программирования:

**Оригинал:**

```text
understand the repo
summarize architecture
find test commands
identify app entry points
propose one small feature
make a plan
implement it
run tests
show the diff
```

**Перевод:**

```text
разобраться в репозитории
кратко описать архитектуру
найти команды запуска тестов
определить точки входа приложения
предложить одну небольшую функцию
составить план
реализовать её
запустить тесты
показать diff
```

<a id="deliverables"></a>
### Материалы для сдачи

**Оригинал:**

```text
docs/agent-workflow-notes.md
AGENTS.md or equivalent project instructions
```

**Перевод:**

```text
docs/agent-workflow-notes.md
AGENTS.md или аналогичные инструкции проекта
```

---

<a id="lesson-32--context-engineering-for-coding-agents"></a>
## Урок 3.2 — Проектирование контекста для агентов для программирования

<a id="goal-1"></a>
### Цель

Выйти за рамки общих промптов и создать контекст на уровне проекта.

<a id="files-to-add"></a>
### Файлы, которые нужно добавить

```text
CLAUDE.md
AGENTS.md
docs/architecture.md
docs/testing.md
docs/agent-rules.md
docs/security-notes.md
```

<a id="example-project-instructions"></a>
### Пример инструкций проекта

**Оригинал:**

```markdown
# Project context

This is a full-stack Snake app with a React frontend, FastAPI backend, PostgreSQL in production, and SQLite for tests.

# Development rules

- Use uv for Python dependency management.
- Use npm for frontend dependencies.
- Always run backend tests before changing API behavior.
- Do not modify CI/CD without asking.
- Do not introduce new dependencies unless justified.
- Prefer small, reviewable diffs.

# Testing

- Backend: uv run pytest
- Frontend: npm test
- Integration: docker compose up --build

# API contract

- The source of truth is openapi.yaml.
- If backend routes change, update openapi.yaml.
- If frontend API calls change, check openapi.yaml.

# Review checklist

- Is the OpenAPI contract still valid?
- Are errors handled?
- Are tests updated?
- Are there unrelated changes?
- Did the change affect auth, secrets, CI, or deployment?
```

**Перевод:**

```markdown
# Контекст проекта

Это full-stack-приложение Snake с фронтендом на React, бэкендом на FastAPI, PostgreSQL в промышленной эксплуатации и SQLite для тестов.

# Правила разработки

- Используй uv для управления зависимостями Python.
- Используй npm для зависимостей фронтенда.
- Всегда запускай тесты бэкенда перед изменением поведения API.
- Не изменяй CI/CD без разрешения.
- Не добавляй новые зависимости без обоснования.
- Предпочитай небольшие diff, удобные для ревью.

# Тестирование

- Бэкенд: uv run pytest
- Фронтенд: npm test
- Интеграция: docker compose up --build

# Контракт API

- Источник истины — openapi.yaml.
- При изменении маршрутов бэкенда обновляй openapi.yaml.
- При изменении вызовов API во фронтенде проверяй openapi.yaml.

# Чек-лист ревью

- Контракт OpenAPI по-прежнему действителен?
- Обрабатываются ли ошибки?
- Обновлены ли тесты?
- Есть ли посторонние изменения?
- Затронуло ли изменение аутентификацию/авторизацию, секреты, CI или развёртывание?
```

<a id="teaching-point"></a>
### Главная учебная мысль

`AGENTS.md`, `CLAUDE.md`, правила редактора или аналогичные инструкции проекта должны содержать устойчивые факты и правила проекта. Повторяющиеся процедуры впоследствии следует оформлять в повторно используемые рабочие процессы: навыки, команды, промпты, правила или рецепты.

---

<a id="lesson-33--mcp-as-one-integration-capability"></a>
## Урок 3.3 — MCP как одна из возможностей интеграции

<a id="goal-2"></a>
### Цель

Преподавать MCP как протокол доступа к инструментам и контексту, а не посвящать ему весь модуль.

<a id="concepts-1"></a>
### Понятия

**Оригинал:**

```text
MCP host/client/server
tools
resources
prompts
stdio transport
HTTP transport
remote vs local servers
project vs user config
approval and permissions
```

**Перевод:**

```text
хост/клиент/сервер MCP
инструменты
ресурсы
промпты
транспорт stdio
транспорт HTTP
удалённые и локальные серверы
конфигурация проекта и пользователя
одобрение и разрешения
```

<a id="app-specific-mcp-server-idea"></a>
### Идея MCP-сервера для приложения

Создайте MCP-сервер для приложения из модуля 2.

```text
tools:
  get_leaderboard
  get_recent_games
  create_bug_report
  run_backend_tests
  run_frontend_tests

resources:
  openapi.yaml
  product-spec.md
  latest-test-results.json

prompts:
  review-api-change
  generate-release-summary
```

<a id="deliverables-1"></a>
### Материалы для сдачи

```text
mcp-server/
  server.py
  README.md
.mcp.json
docs/mcp-tools.md
```

<a id="teaching-point-1"></a>
### Главная учебная мысль

MCP должен предоставлять полезные возможности в безопасных границах. Он не должен превращаться в способ «дать агенту доступ ко всему».

---

<a id="lesson-34--reusable-workflows-skills-commands-rules-and-recipes"></a>
## Урок 3.4 — Повторно используемые рабочие процессы: навыки, команды, правила и рецепты

<a id="goal-3"></a>
### Цель

Научить определять, когда повторяющиеся инструкции стоит превратить в повторно используемую возможность.

<a id="when-to-create-one"></a>
### Когда создавать такой процесс

Создавайте повторно используемый рабочий процесс, когда снова и снова вставляете один и тот же:

**Оригинал:**

```text
checklist
review procedure
debugging procedure
deployment procedure
project-specific convention
multi-step workflow
```

**Перевод:**

```text
чек-лист
процедуру ревью
процедуру отладки
процедуру развёртывания
соглашение, специфичное для проекта
многошаговый рабочий процесс
```

<a id="good-course-workflows"></a>
### Подходящие рабочие процессы для курса

```text
/review-api-change
/debug-ci-failure
/add-backend-endpoint
/add-frontend-component
/prepare-pr
/check-generated-code
/deploy-staging
```

<a id="example-workflow"></a>
### Пример рабочего процесса

Путь:

```text
agent-capabilities/review-api-change/README.md
```

Содержимое:

**Оригинал:**

```markdown
---
name: review-api-change
description: Review backend or frontend changes that may affect the OpenAPI contract.
---

# API Change Review

When reviewing an API change:

1. Check whether `openapi.yaml` needs to change.
2. Check whether frontend API calls still match the backend.
3. Check whether backend tests cover the changed endpoint.
4. Check whether error responses are documented.
5. Check whether the database schema is affected.
6. Produce a concise report with:
   - contract changes
   - required tests
   - compatibility risks
   - suggested fixes
```

**Перевод:**

```markdown
---
name: review-api-change
description: Проверка изменений бэкенда или фронтенда, которые могут затронуть контракт OpenAPI.
---

# Ревью изменения API

При ревью изменения API:

1. Проверь, нужно ли изменить `openapi.yaml`.
2. Проверь, по-прежнему ли вызовы API во фронтенде соответствуют бэкенду.
3. Проверь, покрывают ли тесты бэкенда изменённый эндпоинт.
4. Проверь, задокументированы ли ответы с ошибками.
5. Проверь, затрагивается ли схема базы данных.
6. Подготовь краткий отчёт, включающий:
   - изменения контракта
   - необходимые тесты
   - риски совместимости
   - предлагаемые исправления
```

<a id="deliverables-2"></a>
### Материалы для сдачи

```text
agent-capabilities/review-api-change/
agent-capabilities/debug-ci-failure/
docs/reusable-workflows.md
```

---

<a id="lesson-35--hooks-for-guardrails-and-automation"></a>
## Урок 3.5 — Хуки для ограничений и автоматизации

<a id="goal-4"></a>
### Цель

Показать, что рабочие процессы агентов можно контролировать и автоматизировать.

<a id="hook-use-cases"></a>
### Сценарии использования хуков

**Оригинал:**

```text
auto-format after edits
run ruff after Python edits
run prettier after frontend edits
block dangerous shell commands
block editing .github/workflows without confirmation
log every Bash command
notify when a long task finishes
run tests before commit
```

**Перевод:**

```text
автоформатирование после правок
запуск ruff после правок Python
запуск prettier после правок фронтенда
блокировка опасных команд оболочки
запрет редактирования .github/workflows без подтверждения
логирование каждой команды Bash
уведомление о завершении длительной задачи
запуск тестов перед коммитом
```

<a id="example-hook-idea"></a>
### Пример идеи хука

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "python scripts/agent-hooks/check_bash_command.py"
          }
        ]
      }
    ],
    "PostToolUse": [
      {
        "matcher": "Edit",
        "hooks": [
          {
            "type": "command",
            "command": "python scripts/agent-hooks/format_changed_file.py"
          }
        ]
      }
    ]
  }
}
```

<a id="deliverables-3"></a>
### Материалы для сдачи

```text
.claude/settings.json
scripts/agent-hooks/
docs/hooks.md
```

<a id="teaching-point-2"></a>
### Главная учебная мысль

Хуки превращают просьбу «пожалуйста, будь осторожен» в воспроизводимые защитные ограничения.

---

<a id="lesson-36--subagents-for-specialized-tasks"></a>
## Урок 3.6 — Субагенты для специализированных задач

<a id="goal-5"></a>
### Цель

Объяснить специализированных агентов с собственным контекстом и разрешениями.

<a id="why-subagents-matter"></a>
### Зачем нужны субагенты

Они полезны, когда побочная задача загромоздила бы основной контекст логами, результатами поиска или содержимым файлов.

<a id="course-subagents"></a>
### Субагенты для курса

```text
api-contract-reviewer
debugger
browser-tester
security-reviewer
database-query-validator
release-note-writer
```

<a id="example-subagent"></a>
### Пример субагента

Путь:

```text
agent-capabilities/subagents/api-contract-reviewer.md
```

Содержимое:

**Оригинал:**

```markdown
---
name: api-contract-reviewer
description: Reviews changes that may affect the OpenAPI contract.
tools: Read, Grep, Glob
model: sonnet
---

You are an API contract reviewer.

Check:
- whether backend routes match openapi.yaml
- whether frontend clients match openapi.yaml
- whether tests cover success and error responses
- whether any breaking change is introduced

Do not edit files. Return a concise report with:
- changed endpoints
- compatibility risks
- missing tests
- required fixes
```

**Перевод:**

```markdown
---
name: api-contract-reviewer
description: Проверяет изменения, которые могут затронуть контракт OpenAPI.
tools: Read, Grep, Glob
model: sonnet
---

Ты ревьюер контракта API.

Проверь:
- соответствуют ли маршруты бэкенда openapi.yaml
- соответствуют ли клиенты фронтенда openapi.yaml
- покрывают ли тесты успешные ответы и ответы с ошибками
- появляются ли изменения, нарушающие обратную совместимость

Не редактируй файлы. Верни краткий отчёт, включающий:
- изменённые эндпоинты
- риски совместимости
- недостающие тесты
- необходимые исправления
```

<a id="deliverables-4"></a>
### Материалы для сдачи

```text
agent-capabilities/subagents/api-contract-reviewer.md
agent-capabilities/subagents/debugger.md
agent-capabilities/subagents/browser-tester.md
docs/subagents.md
```

<a id="teaching-point-3"></a>
### Главная учебная мысль

Субагенты — это инструмент управления разрешениями и контекстом, а не просто «крутая мультиагентная функция».

---

<a id="lesson-37--plugins-for-packaging-reusable-capabilities"></a>
## Урок 3.7 — Плагины для упаковки повторно используемых возможностей

<a id="goal-6"></a>
### Цель

Научить определять, когда отдельную конфигурацию `.claude/` следует превратить в плагин, которым можно делиться.

<a id="standalone-config-vs-plugin"></a>
### Отдельная конфигурация и плагин

**Оригинал:**

```text
Use .claude/ for:
- one project
- personal workflows
- experiments
- short local skill names

Use plugins for:
- team sharing
- versioned releases
- cross-project reuse
- community distribution
- namespaced skills
```

**Перевод:**

```text
Используйте .claude/ для:
- одного проекта
- личных рабочих процессов
- экспериментов
- коротких локальных имён навыков

Используйте плагины для:
- совместного использования командой
- версионированных выпусков
- повторного использования в разных проектах
- распространения в сообществе
- навыков с пространствами имён
```

<a id="example-plugin-layout"></a>
### Пример структуры плагина

```text
plugins/ai-devtools-plugin/
  .claude-plugin/
    plugin.json
  skills/
    review-api-change/
      SKILL.md
    debug-ci-failure/
      SKILL.md
  agents/
    api-contract-reviewer.md
  hooks/
    guardrails.json
  README.md
```

<a id="example-pluginjson"></a>
### Пример `plugin.json`

**Оригинал:**

```json
{
  "name": "ai-devtools",
  "description": "Reusable AI Dev Tools Zoomcamp agent capabilities",
  "version": "0.1.0",
  "author": {
    "name": "DataTalks.Club"
  }
}
```

**Перевод:**

```text
Перевод значения description: «Повторно используемые возможности агентов AI Dev Tools Zoomcamp».
```

<a id="deliverables-5"></a>
### Материалы для сдачи

```text
plugins/ai-devtools-plugin/
docs/plugin-usage.md
```

---

<a id="lesson-38--creating-custom-agents-with-sdks"></a>
## Урок 3.8 — Создание собственных агентов с помощью SDK

<a id="goal-7"></a>
### Цель

Научить определять, когда стоит создать собственного агента вместо использования интерактивного агента для программирования.

<a id="when-to-use-a-custom-agent"></a>
### Когда использовать собственного агента

**Оригинал:**

```text
CI/CD integration
custom internal app
scheduled automation
team-specific workflow
controlled tool access
structured output
repeatable pipeline
```

**Перевод:**

```text
интеграция CI/CD
собственное внутреннее приложение
автоматизация по расписанию
рабочий процесс конкретной команды
контролируемый доступ к инструментам
структурированный вывод
повторяемый конвейер
```

<a id="custom-agent-sketch"></a>
### Набросок собственного агента

**Оригинал:**

```python
import asyncio
from claude_agent_sdk import query, ClaudeAgentOptions

TASK = """
Review the current repository for changes that affect the API contract.
Return:
- files inspected
- endpoints affected
- tests needed
- risks
Do not edit files.
"""

async def main():
    options = ClaudeAgentOptions(
        allowed_tools=["Read", "Grep", "Glob", "Bash"],
    )

    async for message in query(prompt=TASK, options=options):
        print(message)

if __name__ == "__main__":
    asyncio.run(main())
```

**Перевод:**

```text
Перевод промпта TASK:

Проверь текущий репозиторий на изменения, затрагивающие контракт API.
Верни:
- проверенные файлы
- затронутые эндпоинты
- необходимые тесты
- риски
Не редактируй файлы.
```

<a id="deliverables-6"></a>
### Материалы для сдачи

```text
custom-agent/
  agent.py
  README.md
docs/custom-agent-design.md
```

<a id="teaching-point-4"></a>
### Главная учебная мысль

Собственные агенты нужны рабочим процессам, которым необходимы программное управление, структурированные результаты и повторяемость.

---

<a id="13-module-3-final-assignment-agent-extension-pack"></a>
## 13. Итоговое задание модуля 3: пакет расширений агента

Студенты дополняют приложение из модуля 2 пакетом расширений агента.

<a id="required-files"></a>
### Обязательные файлы

**Оригинал:**

```text
AGENTS.md or equivalent project instructions

agent-capabilities/
  review-api-change/
  debug-ci-failure/
  subagents/
    api-contract-reviewer.md
    debugger.md

agent-hooks/

mcp-server/
  server.py
  README.md

plugins/
  ai-devtools-agent-pack/
    capabilities/
    subagents/
    README.md

custom-agent/
  agent.py
  README.md

docs/
  agent-extension-pack.md
  permissions.md
  demo.md
```

**Перевод:**

```text
AGENTS.md или аналогичные инструкции проекта

agent-capabilities/
  review-api-change/
  debug-ci-failure/
  subagents/
    api-contract-reviewer.md
    debugger.md

agent-hooks/

mcp-server/
  server.py
  README.md

plugins/
  ai-devtools-agent-pack/
    capabilities/
    subagents/
    README.md

custom-agent/
  agent.py
  README.md

docs/
  agent-extension-pack.md
  permissions.md
  demo.md
```

<a id="minimum-requirements"></a>
### Минимальные требования

**Оригинал:**

```text
1 project instructions file
1 reusable workflow/skill/command
1 specialized subagent
1 MCP tool/server
1 hook or guardrail
1 small custom agent OR plugin/extension package
1 permission/security note
```

**Перевод:**

```text
1 файл инструкций проекта
1 повторно используемый рабочий процесс/навык/команда
1 специализированный субагент
1 инструмент/сервер MCP
1 хук или защитное ограничение
1 небольшой собственный агент ИЛИ пакет плагина/расширения
1 заметка о разрешениях/безопасности
```

<a id="demo-script"></a>
### Сценарий демонстрации

Студенты должны записать или описать демонстрацию, которая показывает:

**Оригинал:**

```text
1. The agent reads the project instructions.
2. The agent invokes a reusable workflow.
3. A subagent reviews an API change.
4. The agent calls an MCP tool.
5. A hook prevents or logs a risky action.
6. The student reviews the final diff.
```

**Перевод:**

```text
1. Агент читает инструкции проекта.
2. Агент вызывает повторно используемый рабочий процесс.
3. Субагент проверяет изменение API.
4. Агент вызывает инструмент MCP.
5. Хук предотвращает или логирует рискованное действие.
6. Студент проверяет итоговый diff.
```

<a id="rubric"></a>
### Критерии оценки

| Критерий | Отлично | Хорошо | Требует доработки |
|---|---|---|---|
| Контекст проекта | Ясный, полный, полезный | В основном полезный | Общий или отсутствует |
| Повторно используемый процесс | Пригоден для повторного использования и имеет чёткий фокус | Работает, но слишком широк | Просто набор промптов |
| Субагент | Чёткие роль и разрешения | Роль определена | Разрешения не продуманы |
| MCP | Полезный инструмент для конкретного приложения | Учебный инструмент работает | Не связан с приложением |
| Хук | Реальное ограничение или автоматизация | Простой хук | Не продемонстрирован |
| Собственный агент/плагин | Работает и документирован | Частично готов | Отсутствует |
| Разрешения | Явные и продуманные | Базовые | Не рассмотрены |

---

<a id="module-4--open-source-ai-tools-for-security-audit-and-devops"></a>
# Модуль 4 — ИИ-инструменты с открытым исходным кодом для безопасности, аудита и DevOps

<a id="14-module-4-positioning"></a>
## 14. Позиционирование модуля 4

Модуль 4 должен иметь чёткий фокус и рамки:

**Оригинал:**

```text
Only open-source AI tools.
Only security, audit, and DevOps.
No general coding agents.
No LLM application evals.
No AI test-generation focus.
```

**Перевод:**

```text
Только ИИ-инструменты с открытым исходным кодом.
Только безопасность, аудит и DevOps.
Без универсальных агентов для программирования.
Без оценивания LLM-приложений.
Без акцента на генерации тестов с помощью ИИ.
```

Это означает, что следующие инструменты **не относятся к модулю 4**, хотя полезны в других частях курса:

```text
Cline
goose
OpenCode
Aider
Codex CLI
Claude Code
Gemini CLI
OpenHands
SWE-agent
mini-SWE-agent
CoverUp
DeepEval
promptfoo
LangSmith
Braintrust
```

Они относятся к более ранним модулям или другим курсам.

---

<a id="15-module-4-core-tool-stack"></a>
## 15. Основной стек инструментов модуля 4

<a id="required-stack"></a>
### Обязательный стек

```text
PR-Agent
Semgrep MCP Server
Snyk Agent Scan
K8sGPT
LiteLLM
Ollama
```

<a id="optional--instructor-demo-stack"></a>
### Необязательный стек / инструменты для демонстраций преподавателя

**Оригинал:**

```text
HolmesGPT
Stakpak
garak
MCPSafetyScanner
Agent Audit / future agent security scanners
```

**Перевод:**

```text
HolmesGPT
Stakpak
garak
MCPSafetyScanner
Agent Audit / будущие сканеры безопасности агентов
```

---

<a id="16-module-4-tool-table"></a>
## 16. Таблица инструментов модуля 4

| Инструмент | Категория | Почему относится к модулю 4 | Обязателен? |
|---|---|---|---|
| PR-Agent | ИИ-аудит PR | Проверяет PR, резюмирует изменения, предлагает улучшения, обновляет журнал изменений | Да |
| Semgrep MCP | Сканирование безопасности, доступное ИИ | Позволяет ИИ-ассистенту запускать детерминированные проверки Semgrep вместо догадок | Да |
| Snyk Agent Scan | Аудит безопасности агентов/MCP/навыков | Проверяет MCP-серверы, инструменты, промпты, ресурсы и навыки на специфические для агентов риски | Да |
| K8sGPT | ИИ-диагностика Kubernetes | Объясняет проблемы кластера Kubernetes и может предоставлять интеграцию MCP | Да |
| LiteLLM | ИИ-шлюз / управление использованием ИИ | Централизует доступ к моделям, виртуальные ключи, отслеживание расходов, маршрутизацию и защитные ограничения | Да |
| Ollama | Локальный запуск моделей | Позволяет проводить лабораторные работы с локальными/приватными моделями на данных безопасности и эксплуатации | Да |
| HolmesGPT | ИИ-расследования для SRE | Расследует инциденты промышленной эксплуатации по логам, метрикам, трассировкам, оповещениям и инструкциям по эксплуатации | Необязательно / демонстрация |
| Stakpak | ИИ-агент для DevOps | Автономный DevOps-агент; интересен, но более сложен | Необязательно / упоминание |

---

<a id="17-tool-notes"></a>
## 17. Примечания об инструментах

<a id="171-pr-agent"></a>
### 17.1 PR-Agent

Использовать для:

**Оригинал:**

```text
AI PR descriptions
AI PR review
suggested improvements
questions about diff
changelog updates
risk hints
```

**Перевод:**

```text
описания PR с помощью ИИ
ревью PR с помощью ИИ
предложения улучшений
вопросы о diff
обновление журнала изменений
указания на риски
```

Чем полезен:

**Оригинал:**

```text
it sits at the PR boundary
it is easy to demo
it produces concrete review artifacts
it can run as GitHub Action or CLI
it can be customized
```

**Перевод:**

```text
работает на этапе PR
легко продемонстрировать
создаёт конкретные материалы ревью
может запускаться как GitHub Action или CLI
поддаётся настройке
```

Рекомендуемые команды для курса:

```text
/describe
/review
/improve
/ask
/update_changelog
```

Рекомендуемые файлы:

```text
.github/workflows/pr-agent.yml
.pr_agent.toml
docs/pr-audit-checklist.md
```

---

<a id="172-semgrep-mcp-server"></a>
### 17.2 Semgrep MCP Server

Использовать для:

**Оригинал:**

```text
security scans through MCP
custom Semgrep rules
AI-assisted explanation of findings
deterministic security evidence
```

**Перевод:**

```text
сканирование безопасности через MCP
собственные правила Semgrep
объяснение находок с помощью ИИ
детерминированные доказательства для проверки безопасности
```

Важная учебная мысль:

> ИИ не должен выдумывать проблемы безопасности. Он должен вызывать настоящий сканер и объяснять результаты.

Среди полезных инструментов Semgrep MCP:

```text
security_check
semgrep_scan
semgrep_scan_with_custom_rule
get_abstract_syntax_tree
```

Рекомендуемые файлы:

```text
.vscode/mcp.json
.cursor/mcp.json
security/custom-rule.yml
security/semgrep-findings.md
```

---

<a id="173-snyk-agent-scan"></a>
### 17.3 Snyk Agent Scan

Важное замечание о названии:

> Старый URL репозитория `mcp-scan` теперь перенаправляет на **Snyk Agent Scan**. В курсе используйте текущее название: **Snyk Agent Scan**. Он по-прежнему покрывает ту же категорию, ради которой мы рассматривали mcp-scan: сканирование компонентов агентов, MCP-серверов, инструментов, промптов, ресурсов и навыков.

Использовать для:

**Оригинал:**

```text
agent component inventory
MCP server security review
skills security review
prompt injection detection
tool poisoning detection
toxic flow detection
hardcoded secret / credential handling checks in skills
```

**Перевод:**

```text
инвентаризация компонентов агента
ревью безопасности MCP-сервера
ревью безопасности навыков
обнаружение инъекций в промпт
обнаружение отравления инструментов (tool poisoning)
обнаружение опасных потоков взаимодействия (toxic flow)
проверки жёстко заданных секретов и обращения с учётными данными в навыках
```

Важное замечание о безопасности:

**Оригинал:**

```text
Scanning MCP configs can execute the commands defined in those configs.
Run untrusted scans in a sandbox.
Review commands before approving them.
Use non-interactive flags only in trusted CI environments.
```

**Перевод:**

```text
Сканирование конфигураций MCP может выполнять команды, заданные в этих конфигурациях.
Запускайте проверки недоверенных конфигураций в песочнице.
Проверяйте команды перед их одобрением.
Используйте неинтерактивные флаги только в доверенных средах CI.
```

Рекомендуемые файлы:

```text
security/agent-scan-report.json
security/agent-scan-notes.md
security/mcp-threat-model.md
security/tool-permissions.md
```

---

<a id="174-k8sgpt"></a>
### 17.4 K8sGPT

Использовать для:

**Оригинал:**

```text
Kubernetes issue diagnosis
pod/deployment/service/ingress analysis
plain-English explanations
JSON reports
anonymized analysis
MCP integration with compatible clients
```

**Перевод:**

```text
диагностика проблем Kubernetes
анализ pod/deployment/service/ingress
объяснения простым английским языком
отчёты JSON
анонимизированный анализ
интеграция MCP с совместимыми клиентами
```

Подходящие сбои для лабораторной работы новичков:

**Оригинал:**

```text
wrong image tag
missing environment variable
bad service selector
failing readiness probe
insufficient resources
crash loop
bad ingress target
```

**Перевод:**

```text
неверный тег образа
отсутствующая переменная окружения
неверный селектор сервиса
сбой проверки готовности (readiness probe)
нехватка ресурсов
цикл аварийных перезапусков
неверная цель ingress
```

Рекомендуемые команды:

```bash
k8sgpt auth add
k8sgpt analyze --explain
k8sgpt analyze --explain --with-doc
k8sgpt analyze --explain --filter=Pod --namespace=default
k8sgpt analyze --explain --output=json --anonymize
k8sgpt serve --mcp --mcp-http
```

Рекомендуемые файлы:

```text
ops/k8s-broken-deployment.yaml
ops/k8sgpt-report.json
ops/k8sgpt-diagnosis.md
```

---

<a id="175-holmesgpt"></a>
### 17.5 HolmesGPT

Использовать для:

**Оригинал:**

```text
incident investigation
alert triage
root-cause hypothesis
log/metric/trace correlation
runbook-aware investigation
SRE assistant demos
```

**Перевод:**

```text
расследование инцидентов
первичный разбор оповещений
гипотеза о первопричине
сопоставление логов/метрик/трассировок
расследование с учётом инструкций по эксплуатации
демонстрации SRE-ассистента
```

Почему необязателен:

**Оригинал:**

```text
it is powerful
it may require more setup
it benefits from observability data
it may be better as an instructor demo first
```

**Перевод:**

```text
это мощный инструмент
может потребовать дополнительной настройки
выигрывает от наличия данных наблюдаемости
для начала может лучше подойти в качестве демонстрации преподавателя
```

Рекомендуемое применение в курсе:

**Оригинал:**

```text
prepared alert/log bundle
small Kubernetes incident
Prometheus/Loki demo if available
incident summary exercise
```

**Перевод:**

```text
подготовленный набор оповещений/логов
небольшой инцидент Kubernetes
демонстрация Prometheus/Loki, если доступна
упражнение по составлению резюме инцидента
```

Рекомендуемые файлы:

```text
ops/alert-example.json
ops/holmes-investigation.md
ops/incident-summary.md
ops/follow-up-actions.md
```

---

<a id="176-litellm"></a>
### 17.6 LiteLLM

Использовать для:

**Оригинал:**

```text
central model gateway
virtual keys
routing between providers
spend tracking
guardrails
logging
OpenAI-compatible API for tools
MCP gateway patterns
```

**Перевод:**

```text
центральный шлюз моделей
виртуальные ключи
маршрутизация между провайдерами
отслеживание расходов
защитные ограничения
логирование
OpenAI-совместимый API для инструментов
схемы использования MCP-шлюза
```

Почему нужен:

Модуль 4 должен обучать не только использованию ИИ-инструментов безопасности и аудита, но и контролю их доступа к моделям.

Рекомендуемая архитектура:

**Оригинал:**

```text
PR-Agent        -> LiteLLM -> hosted model
K8sGPT          -> LiteLLM or Ollama
HolmesGPT       -> LiteLLM
Semgrep MCP     -> scanner first, model only for explanation
Snyk Agent Scan -> scanner first, no broad model access needed
```

**Перевод:**

```text
PR-Agent        -> LiteLLM -> внешняя модель
K8sGPT          -> LiteLLM или Ollama
HolmesGPT       -> LiteLLM
Semgrep MCP     -> сначала сканер, модель только для объяснения
Snyk Agent Scan -> сначала сканер, широкий доступ к модели не нужен
```

Рекомендуемые файлы:

```text
ops/litellm-config.yaml
docs/model-routing.md
docs/ai-tool-policy.md
```

---

<a id="177-ollama"></a>
### 17.7 Ollama

Использовать для:

**Оригинал:**

```text
local model runs
privacy-sensitive demos
offline-ish labs
model fallback
local experiments with K8sGPT or other tools
```

**Перевод:**

```text
локальные запуски моделей
демонстрации с требованиями к приватности
лабораторные работы с минимальной зависимостью от интернета
резервная модель
локальные эксперименты с K8sGPT или другими инструментами
```

Рекомендуемые команды:

```bash
ollama run qwen
ollama run deepseek-coder
ollama run gemma
```

Точные названия моделей следует проверить на момент записи курса.

---

<a id="18-module-4-content-flow"></a>
## 18. Последовательность тем модуля 4

<a id="lesson-41--production-ai-risk-model"></a>
## Урок 4.1 — Модель рисков ИИ в промышленной эксплуатации

<a id="goal-8"></a>
### Цель

Дать учащимся концептуальную модель до знакомства с инструментами.

<a id="topics"></a>
### Темы

**Оригинал:**

```text
AI-generated code risk
agent tool risk
MCP server risk
skill/plugin supply-chain risk
CI/CD risk
Kubernetes/operations risk
model gateway/data exposure risk
```

**Перевод:**

```text
риски кода, сгенерированного ИИ
риски инструментов агента
риски MCP-сервера
риски цепочки поставок навыков/плагинов
риски CI/CD
риски Kubernetes/эксплуатации
риски шлюза моделей/раскрытия данных
```

<a id="main-message"></a>
### Основная мысль

**Оригинал:**

```text
AI can help audit and operate software, but it must be grounded in evidence:
- diffs
- scanner results
- cluster state
- logs
- metrics
- traces
- policies
```

**Перевод:**

```text
ИИ может помогать в аудите и эксплуатации ПО, но должен опираться на доказательства:
- diff
- результаты сканеров
- состояние кластера
- логи
- метрики
- трассировки
- политики
```

<a id="deliverable"></a>
### Материал для сдачи

```text
security/ai-production-risk-model.md
```

Шаблон:

**Оригинал:**

```markdown
# AI production risk model

## What can AI tools read?

## What can AI tools change?

## What secrets or sensitive data could be exposed?

## Which tools are read-only?

## Which tools can write?

## Which actions require human approval?

## What logs or audit trails exist?
```

**Перевод:**

```markdown
# Модель рисков ИИ в промышленной эксплуатации

## Что ИИ-инструменты могут читать?

## Что ИИ-инструменты могут изменять?

## Какие секреты или чувствительные данные могут раскрыться?

## Какие инструменты работают только на чтение?

## Какие инструменты могут записывать данные?

## Какие действия требуют одобрения человека?

## Какие логи или аудиторские следы существуют?
```

---

<a id="lesson-42--ai-pr-audit-with-pr-agent"></a>
## Урок 4.2 — ИИ-аудит PR с PR-Agent

<a id="goal-9"></a>
### Цель

Научить ревью с помощью ИИ на этапе pull request.

<a id="setup"></a>
### Настройка

**Оригинал:**

```yaml
# .github/workflows/pr-agent.yml
name: PR Agent

on:
  pull_request:
    types: [opened, synchronize, reopened]

permissions:
  contents: read
  pull-requests: write
  issues: write

jobs:
  pr_agent_job:
    runs-on: ubuntu-latest
    steps:
      - name: PR Agent action step
        uses: the-pr-agent/pr-agent@main
        env:
          OPENAI_KEY: ${{ secrets.OPENAI_KEY }}
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

**Перевод:**

```text
Перевод подписи шага PR Agent action step: «Шаг действия PR Agent».
```

В курсе можно обращаться к поставщику модели через LiteLLM, а не напрямую к внешнему провайдеру.

<a id="security-focused-pr-agent-configuration"></a>
### Конфигурация PR-Agent с акцентом на безопасность

**Оригинал:**

```toml
[pr_reviewer]
extra_instructions = """
Focus on security, auditability, and operational risk.

Check for:
- missing auth or authorization checks
- unsafe user input handling
- secrets or tokens in code
- suspicious dependency changes
- Dockerfile or deployment risks
- broad GitHub Actions permissions
- unsafe use of pull_request_target
- changes to CI/CD without clear rationale
- missing tests for security-sensitive behavior
- unrelated changes
"""
```

**Перевод:**

```text
Перевод промпта extra_instructions:

Сосредоточься на безопасности, возможности аудита и эксплуатационных рисках.

Проверь наличие:
- отсутствующих проверок аутентификации или авторизации
- небезопасной обработки пользовательского ввода
- секретов или токенов в коде
- подозрительных изменений зависимостей
- рисков Dockerfile или развёртывания
- широких разрешений GitHub Actions
- небезопасного использования pull_request_target
- изменений CI/CD без ясного обоснования
- отсутствующих тестов для поведения, критичного для безопасности
- посторонних изменений
```

<a id="lab-1"></a>
### Лабораторная работа

Студенты создают PR с изменениями приложения из модуля 2.

Запустите PR-Agent, чтобы:

**Оригинал:**

```text
describe the PR
review the PR
suggest improvements
ask a question about a risky file
update changelog
```

**Перевод:**

```text
описать PR
проверить PR
предложить улучшения
задать вопрос о рискованном файле
обновить журнал изменений
```

<a id="deliverables-7"></a>
### Материалы для сдачи

```text
.github/workflows/pr-agent.yml
.pr_agent.toml
docs/pr-agent-output.md
docs/pr-audit-checklist.md
```

<a id="teaching-point-5"></a>
### Главная учебная мысль

> ИИ-ревью PR не означает одобрение. Это помощь в аудите.

---

<a id="lesson-43--ai-accessible-security-scanning-with-semgrep-mcp"></a>
## Урок 4.3 — Сканирование безопасности, доступное ИИ, с Semgrep MCP

<a id="goal-10"></a>
### Цель

Показать, как ИИ-ассистент может использовать детерминированный сканер безопасности.

<a id="setup-example"></a>
### Пример настройки

**Оригинал:**

```json
{
  "mcpServers": {
    "semgrep": {
      "command": "uvx",
      "args": ["semgrep-mcp"],
      "env": {
        "SEMGREP_APP_TOKEN": "<optional-token>"
      }
    }
  }
}
```

**Перевод:**

```text
Перевод заполнителя <optional-token>: «необязательный токен».
```

<a id="lab-2"></a>
### Лабораторная работа

1. Добавьте в приложение заведомо уязвимую конструкцию.
2. Попросите MCP-совместимого ассистента запустить Semgrep MCP.
3. Изучите найденную проблему.
4. Попросите ассистента объяснить её.
5. Исправьте проблему.
6. Повторите сканирование.
7. Задокументируйте исправление.

<a id="good-toy-vulnerabilities"></a>
### Подходящие учебные уязвимости

**Оригинал:**

```text
hardcoded fake API key
unsafe string interpolation into SQL-like query
missing authorization check
unsafe redirect
unsafe shell command construction
```

**Перевод:**

```text
жёстко заданный фиктивный API-ключ
небезопасная интерполяция строки в SQL-подобный запрос
отсутствующая проверка авторизации
небезопасное перенаправление
небезопасное формирование команды оболочки
```

<a id="example-custom-rule-skeleton"></a>
### Пример заготовки собственного правила

**Оригинал:**

```yaml
rules:
  - id: python-dangerous-subprocess-shell-true
    message: Avoid shell=True with user-controlled input.
    severity: WARNING
    languages: [python]
    pattern: subprocess.run(..., shell=True, ...)
```

**Перевод:**

```text
Перевод сообщения правила: «Не используйте shell=True с вводом, контролируемым пользователем».
```

<a id="deliverables-8"></a>
### Материалы для сдачи

```text
security/semgrep-findings.md
security/custom-rule.yml
security/remediation-notes.md
```

<a id="teaching-point-6"></a>
### Главная учебная мысль

> LLM объясняет и координирует действия; Semgrep предоставляет доказательства.

---

<a id="lesson-44--agent-mcp-and-skill-security-scanning-with-snyk-agent-scan"></a>
## Урок 4.4 — Проверка безопасности агентов, MCP и навыков с Snyk Agent Scan

<a id="goal-11"></a>
### Цель

Провести аудит пакета расширений агента из модуля 3.

<a id="setup-1"></a>
### Настройка

```bash
uvx snyk-agent-scan@latest
```

Проверка определённой конфигурации MCP:

```bash
uvx snyk-agent-scan@latest ~/.vscode/mcp.json
```

Проверка повторно используемых процессов проекта или каталогов навыков конкретного инструмента:

```bash
uvx snyk-agent-scan@latest agent-capabilities
```

<a id="lab-3"></a>
### Лабораторная работа

1. Используйте инструкции проекта, повторно используемые процессы, субагентов, хуки и MCP-сервер из модуля 3.
2. Запустите Agent Scan.
3. Изучите выявленные риски.
4. Исправьте одну проблему в навыке или описании инструмента.
5. Повторите сканирование.
6. Составьте таблицу разрешений.

<a id="example-permission-table"></a>
### Пример таблицы разрешений

| Инструмент / навык | Чтение | Запись | Сеть | Секреты | Требуется одобрение человека |
|---|---|---|---|---|---|
| Semgrep MCP | исходный код | нет | необязательно | токен необязателен | нет |
| MCP-сервер приложения: get_leaderboard | БД приложения | нет | локальное приложение | нет | нет |
| MCP-сервер приложения: create_bug_report | трекер задач | да | да | токен | да |
| навык развёртывания | репозиторий + конфигурация облака | да | да | облачный токен | да |

<a id="deliverables-9"></a>
### Материалы для сдачи

```text
security/agent-scan-report.json
security/agent-scan-notes.md
security/tool-permissions.md
security/mcp-threat-model.md
```

<a id="teaching-point-7"></a>
### Главная учебная мысль

> Расширения агентов образуют цепочку поставок. Навыки, MCP-серверы, плагины и описания инструментов требуют проверки.

---

<a id="lesson-45--kubernetes-diagnostics-with-k8sgpt"></a>
## Урок 4.5 — Диагностика Kubernetes с K8sGPT

<a id="goal-12"></a>
### Цель

Познакомить с DevOps-диагностикой с помощью ИИ, не превращая курс в курс Kubernetes.

<a id="suggested-environment"></a>
### Рекомендуемая среда

```text
kind
k3d
minikube
```

<a id="lab-scenario"></a>
### Сценарий лабораторной работы

Разверните учебную версию приложения из модуля 2 в локальном кластере, затем намеренно сломайте её.

Примеры неисправных конфигураций:

**Оригинал:**

```yaml
# wrong image
image: snake-backend:does-not-exist

# bad selector
selector:
  app: backend-wrong

# missing env var
env:
  - name: DATABASE_URL
    value: ""
```

**Перевод:**

```text
Перевод комментариев к конфигурации:
- wrong image: неверный образ
- bad selector: неверный селектор
- missing env var: отсутствующая переменная окружения
```

<a id="commands"></a>
### Команды

```bash
k8sgpt auth add
k8sgpt analyze --explain
k8sgpt analyze --explain --filter=Pod --namespace=default
k8sgpt analyze --explain --output=json --anonymize
```

<a id="deliverables-10"></a>
### Материалы для сдачи

```text
ops/k8s-broken-deployment.yaml
ops/k8sgpt-report.json
ops/k8sgpt-diagnosis.md
```

<a id="diagnosis-template"></a>
### Шаблон диагностики

**Оригинал:**

```markdown
# K8sGPT diagnosis

## Incident

## Symptoms

## K8sGPT findings

## Evidence from kubectl

## Root cause

## Fix

## Prevention

## What AI got right

## What needed human verification
```

**Перевод:**

```markdown
# Диагностика K8sGPT

## Инцидент

## Симптомы

## Находки K8sGPT

## Доказательства из kubectl

## Первопричина

## Исправление

## Предотвращение

## В чём ИИ оказался прав

## Что потребовало проверки человеком
```

<a id="teaching-point-8"></a>
### Главная учебная мысль

> K8sGPT должен опираться на состояние кластера. Учащиеся обязаны проверять выводы с помощью `kubectl`.

---

<a id="lesson-46--incident-investigation-with-holmesgpt"></a>
## Урок 4.6 — Расследование инцидентов с HolmesGPT

<a id="goal-13"></a>
### Цель

Показать ИИ в роли помощника SRE при расследовании.

<a id="status"></a>
### Статус

Для первого потока этот урок может быть необязательным или проходить под руководством преподавателя.

<a id="lab-option-a-prepared-data-bundle"></a>
### Вариант лабораторной работы A: подготовленный набор данных

Выдайте студентам:

```text
alert.json
pod-describe.txt
app.log
prometheus-snapshot.txt
runbook.md
```

Используйте HolmesGPT или демонстрацию преподавателя для расследования.

<a id="lab-option-b-live-mini-stack"></a>
### Вариант лабораторной работы B: работающий мини-стек

Используйте:

**Оригинал:**

```text
local Kubernetes
Prometheus
Loki
sample app
one triggered alert
```

**Перевод:**

```text
локальный Kubernetes
Prometheus
Loki
пример приложения
одно сработавшее оповещение
```

Этот вариант реалистичнее, но сложнее в подготовке.

<a id="deliverables-11"></a>
### Материалы для сдачи

```text
ops/holmes-investigation.md
ops/incident-summary.md
ops/follow-up-actions.md
```

<a id="incident-summary-template"></a>
### Шаблон резюме инцидента

**Оригинал:**

```markdown
# Incident summary

## What happened

## Impact

## Timeline

## Signals reviewed

- Alerts
- Logs
- Metrics
- Kubernetes events
- Recent deployments

## Root-cause hypothesis

## Confirmed root cause

## Fix

## Follow-up actions

## What HolmesGPT helped with

## What humans verified
```

**Перевод:**

```markdown
# Резюме инцидента

## Что произошло

## Последствия

## Хронология

## Рассмотренные сигналы

- Оповещения
- Логи
- Метрики
- События Kubernetes
- Недавние развёртывания

## Гипотеза о первопричине

## Подтверждённая первопричина

## Исправление

## Последующие действия

## В чём помог HolmesGPT

## Что проверили люди
```

<a id="teaching-point-9"></a>
### Главная учебная мысль

> ИИ может сопоставлять и обобщать эксплуатационные данные, но первопричину подтверждают люди, и они же отвечают за устранение проблемы.

---

<a id="lesson-47--ai-tool-governance-with-litellm-and-ollama"></a>
## Урок 4.7 — Управление использованием ИИ-инструментов с LiteLLM и Ollama

<a id="goal-14"></a>
### Цель

Научить контролировать доступ ИИ-инструментов к моделям и чувствительным данным.

<a id="topics-1"></a>
### Темы

**Оригинал:**

```text
open-source tool vs hosted model
local model vs hosted model
virtual keys
tool-specific keys
budget limits
model routing
audit logs
prompt/data retention
redaction
local model fallback
```

**Перевод:**

```text
инструмент с открытым исходным кодом и внешняя модель
локальная и внешняя модель
виртуальные ключи
отдельные ключи для инструментов
ограничения бюджета
маршрутизация моделей
журналы аудита
хранение промптов/данных
удаление чувствительных данных
локальная модель как резервный вариант
```

<a id="example-litellm-config"></a>
### Пример конфигурации LiteLLM

```yaml
model_list:
  - model_name: fast-default
    litellm_params:
      model: openai/gpt-4o-mini
      api_key: os.environ/OPENAI_API_KEY

  - model_name: local-qwen
    litellm_params:
      model: ollama/qwen
      api_base: http://localhost:11434

general_settings:
  master_key: os.environ/LITELLM_MASTER_KEY
```

<a id="suggested-policy"></a>
### Рекомендуемая политика

**Оригинал:**

```markdown
# AI tool policy

## Allowed tools

- PR-Agent for PR audit
- Semgrep MCP for security scanning
- Snyk Agent Scan for agent/MCP/skill scanning
- K8sGPT for local/dev cluster diagnosis
- HolmesGPT for instructor demo or approved environments

## Model routing

- PR summaries may use hosted models.
- Security scans must not send secrets.
- Logs must be anonymized before hosted model use.
- Local model is preferred for sensitive operational data.

## Approval rules

- AI tools may comment on PRs.
- AI tools may not merge PRs.
- AI tools may not deploy to production.
- AI tools may not rotate secrets.
- Any tool with write access requires human approval.
```

**Перевод:**

```markdown
# Политика использования ИИ-инструментов

## Разрешённые инструменты

- PR-Agent для аудита PR
- Semgrep MCP для сканирования безопасности
- Snyk Agent Scan для проверки агентов/MCP/навыков
- K8sGPT для диагностики локальных кластеров и кластеров разработки
- HolmesGPT для демонстрации преподавателя или одобренных сред

## Маршрутизация моделей

- Для резюме PR можно использовать внешние модели.
- Проверки безопасности не должны отправлять секреты.
- Перед использованием внешних моделей логи должны быть анонимизированы.
- Для чувствительных эксплуатационных данных предпочтительна локальная модель.

## Правила одобрения

- ИИ-инструменты могут комментировать PR.
- ИИ-инструменты не могут сливать PR.
- ИИ-инструменты не могут выполнять развёртывание в промышленной среде.
- ИИ-инструменты не могут выполнять ротацию секретов.
- Любой инструмент с доступом на запись требует одобрения человека.
```

<a id="deliverables-12"></a>
### Материалы для сдачи

```text
ops/litellm-config.yaml
docs/ai-tool-policy.md
docs/model-routing.md
docs/data-handling.md
```

<a id="teaching-point-10"></a>
### Главная учебная мысль

> «ИИ-инструмент с открытым исходным кодом» не означает автоматически «приватный». Имеют значение модель, шлюз, логи и потоки данных.

---

<a id="19-module-4-final-assignment-ai-securityauditdevops-report"></a>
## 19. Итоговое задание модуля 4: отчёт об ИИ-инструментах безопасности, аудита и DevOps

Студенты применяют материалы модуля 4 к своему проекту из модулей 2/3.

<a id="required-deliverables"></a>
### Обязательные материалы для сдачи

```text
security/
  ai-production-risk-model.md
  semgrep-findings.md
  agent-scan-report.json
  agent-scan-notes.md
  tool-permissions.md
  mcp-threat-model.md

ops/
  k8sgpt-report.json
  k8sgpt-diagnosis.md
  litellm-config.yaml

docs/
  pr-agent-output.md
  pr-audit-checklist.md
  ai-tool-policy.md
  data-handling.md
```

<a id="optional-deliverables"></a>
### Необязательные материалы для сдачи

```text
ops/
  holmes-investigation.md
  incident-summary.md
  follow-up-actions.md
```

<a id="capstone-narrative"></a>
### Содержание итогового отчёта

Итоговый отчёт должен отвечать на вопросы:

**Оригинал:**

```text
What did we audit?
Which AI tools were used?
Which findings were real?
Which findings were false positives or not relevant?
What was fixed?
What remains risky?
Which tools have read/write access?
Which model provider sees which data?
Which actions require human approval?
```

**Перевод:**

```text
Что мы проверили в ходе аудита?
Какие ИИ-инструменты использовали?
Какие находки подтвердились?
Какие находки оказались ложноположительными или нерелевантными?
Что исправлено?
Какие риски остаются?
Какие инструменты имеют доступ на чтение/запись?
Какой провайдер модели видит какие данные?
Какие действия требуют одобрения человека?
```

<a id="module-4-rubric"></a>
### Критерии оценки модуля 4

| Критерий | Отлично | Хорошо | Требует доработки |
|---|---|---|---|
| Аудит PR | PR-Agent настроен, результаты проверены, есть заметки о безопасности | Базовый запуск PR-Agent | Нет материалов ревью |
| Semgrep MCP | Сканирование выполнено, находка объяснена, добавлено собственное правило или исправление | Сканирование выполнено | Нет детерминированных доказательств |
| Agent Scan | MCP/навыки проверены, риски интерпретированы, разрешения исправлены | Сканирование выполнено | Безопасность агентов не продумана |
| K8sGPT | Неисправное развёртывание диагностировано, выводы проверены через kubectl | Диагностика выполнена | Нет проверки |
| Управление использованием ИИ | Ясная политика, маршрутизация моделей, обработка данных и правила одобрения | Базовая политика | Отсутствует |
| Итоговый отчёт | Объясняет доказательства и решения | Перечисляет результаты | Трудно понять |

---

<a id="20-what-belongs-where"></a>
# 20. Что к чему относится

<a id="module-1"></a>
## Модуль 1

**Оригинал:**

```text
ChatGPT
Claude
Gemini
Cursor
Windsurf
VS Code Copilot
Claude Code
Codex CLI
Gemini CLI
Aider
Cline
goose
OpenCode
Lovable
Bolt
Replit
Zed
Antigravity
ZCode
Cowork-style tools
```

**Перевод:**

```text
ChatGPT
Claude
Gemini
Cursor
Windsurf
VS Code Copilot
Claude Code
Codex CLI
Gemini CLI
Aider
Cline
goose
OpenCode
Lovable
Bolt
Replit
Zed
Antigravity
ZCode
инструменты в стиле Cowork
```

Назначение: сравнивать категории и выбирать подходящий инструмент.

<a id="module-2"></a>
## Модуль 2

**Оригинал:**

```text
Lovable / Bolt / Replit for prototype
Claude Code / Codex / Cursor for implementation
OpenAPI
FastAPI / Django
Docker
GitHub Actions
Render / Fly / Railway
```

**Перевод:**

```text
Lovable / Bolt / Replit для прототипа
Claude Code / Codex / Cursor для реализации
OpenAPI
FastAPI / Django
Docker
GitHub Actions
Render / Fly / Railway
```

Назначение: создать и выпустить приложение.

<a id="module-3"></a>
## Модуль 3

**Оригинал:**

```text
Claude Code
CLAUDE.md
AGENTS.md
MCP
skills
hooks
subagents
plugins
Agent SDK
custom MCP server
custom agent
```

**Перевод:**

```text
Claude Code
CLAUDE.md
AGENTS.md
MCP
навыки
хуки
субагенты
плагины
Agent SDK
собственный MCP-сервер
собственный агент
```

Назначение: расширять и настраивать агентов для программирования.

<a id="module-4"></a>
## Модуль 4

**Оригинал:**

```text
PR-Agent
Semgrep MCP
Snyk Agent Scan
K8sGPT
LiteLLM
Ollama
HolmesGPT optional
Stakpak optional
```

**Перевод:**

```text
PR-Agent
Semgrep MCP
Snyk Agent Scan
K8sGPT
LiteLLM
Ollama
HolmesGPT необязательно
Stakpak необязательно
```

Назначение: безопасность, аудит, DevOps и управление использованием ИИ.

---

<a id="21-suggested-readme-syllabus-block"></a>
# 21. Предлагаемый блок программы для README

**Оригинал:**

```markdown
## Syllabus

### Module 1: AI-Native Developer Workflow

Compare modern AI developer tools: chat assistants, terminal coding agents, agentic IDEs, desktop workbenches, cloud agents, and project bootstrappers. Learn when to use ChatGPT/Claude/Gemini-style chat, Claude Code/Codex/Gemini CLI-style terminal agents, Cursor/Windsurf/Zed/Antigravity-style IDEs, and Lovable/Bolt/Replit-style bootstrappers.

You will also learn context engineering with `AGENTS.md`, `CLAUDE.md`, repository instructions, product specs, architecture notes, testing guidelines, and security checklists.

Outcome: configure a repository for AI-assisted development and complete one small feature using a disciplined AI workflow.

### Module 2: Build and Ship an AI-Assisted Full-Stack App

Build an end-to-end application with AI assistance: product spec, frontend prototype, OpenAPI contract, FastAPI or Django backend, database, tests, Docker, deployment, and CI/CD.

Outcome: a deployed full-stack app with tests, Docker setup, OpenAPI contract, and a reproducible development workflow.

### Module 3: Coding Agent Capabilities: MCP, Skills, Plugins, and Custom Agents

Learn how modern coding agents are extended and customized. MCP is covered as one important capability, alongside project instructions, reusable workflows/skills, hooks, specialized subagents, plugins/extensions, and custom agents. Examples can use specific tools, but the concepts should transfer across modern agentic coding tools.

Outcome: create an agent extension pack for your app, including project instructions, a custom skill, a specialized subagent, a hook, an MCP tool/server, and either a small plugin or custom agent.

### Module 4: Open-Source AI Tools for Security, Audit, and DevOps

Learn how to use open-source AI tools around the production workflow. This module focuses on AI pull request audit, AI-accessible security scanning, agent/MCP/skill security scanning, Kubernetes diagnostics, incident investigation, and AI tool governance.

Outcome: harden and audit your final project using PR-Agent, Semgrep MCP, Snyk Agent Scan, K8sGPT, LiteLLM, Ollama, and optionally HolmesGPT.
```

**Перевод:**

```markdown
## Программа

### Модуль 1: Рабочий процесс разработчика с ИИ в основе

Сравните современные ИИ-инструменты для разработчиков: чат-ассистенты, терминальные агенты для программирования, агентные IDE, настольные рабочие среды, облачные агенты и генераторы начальных проектов. Узнайте, когда использовать чаты типа ChatGPT/Claude/Gemini, терминальных агентов типа Claude Code/Codex/Gemini CLI, IDE типа Cursor/Windsurf/Zed/Antigravity и генераторы начальных проектов типа Lovable/Bolt/Replit.

Вы также освоите проектирование контекста с помощью `AGENTS.md`, `CLAUDE.md`, инструкций репозитория, продуктовых спецификаций, заметок об архитектуре, рекомендаций по тестированию и чек-листов безопасности.

Результат: настроить репозиторий для разработки с помощью ИИ и реализовать одну небольшую функцию с использованием дисциплинированного ИИ-процесса.

### Модуль 2: Создание и выпуск full-stack-приложения с помощью ИИ

Создайте приложение от начала до конца с помощью ИИ: продуктовая спецификация, прототип фронтенда, контракт OpenAPI, бэкенд на FastAPI или Django, база данных, тесты, Docker, развёртывание и CI/CD.

Результат: развёрнутое full-stack-приложение с тестами, настройкой Docker, контрактом OpenAPI и воспроизводимым процессом разработки.

### Модуль 3: Возможности агентов для программирования: MCP, навыки, плагины и собственные агенты

Узнайте, как расширяют и настраивают современных агентов для программирования. MCP рассматривается как одна из важных возможностей наряду с инструкциями проекта, повторно используемыми процессами/навыками, хуками, специализированными субагентами, плагинами/расширениями и собственными агентами. В примерах можно использовать конкретные инструменты, но понятия должны быть применимы к разным современным агентным инструментам программирования.

Результат: создать пакет расширений агента для своего приложения, включая инструкции проекта, собственный навык, специализированного субагента, хук, инструмент/сервер MCP и небольшой плагин либо собственного агента.

### Модуль 4: ИИ-инструменты с открытым исходным кодом для безопасности, аудита и DevOps

Узнайте, как использовать ИИ-инструменты с открытым исходным кодом в процессе промышленной эксплуатации. Модуль сосредоточен на ИИ-аудите pull request, сканировании безопасности, доступном ИИ, проверке безопасности агентов/MCP/навыков, диагностике Kubernetes, расследовании инцидентов и управлении использованием ИИ-инструментов.

Результат: усилить защиту и провести аудит итогового проекта с помощью PR-Agent, Semgrep MCP, Snyk Agent Scan, K8sGPT, LiteLLM, Ollama и, при желании, HolmesGPT.
```

---

<a id="22-suggested-repository-structure"></a>
# 22. Предлагаемая структура репозитория

```text
ai-dev-tools-zoomcamp/
  README.md

  01-ai-native-workflow/
    README.md
    labs/
    examples/
    homework.md

  02-build-and-ship/
    README.md
    snake-app/
    examples/
    homework.md

  03-coding-agent-capabilities/
    README.md
    agent-capabilities/
      reusable-workflows/
      subagents/
      hooks/
      plugins/
    mcp-server/
    custom-agent/
    homework.md

  04-ai-security-audit-devops/
    README.md
    pr-agent/
    semgrep-mcp/
    agent-scan/
    k8sgpt/
    holmesgpt/
    litellm-ollama/
    homework.md

  project/
    README.md
    rubric.md
```

---

<a id="23-suggested-recording-order"></a>
# 23. Предлагаемый порядок записи

<a id="first-pass"></a>
## Первый проход

1. Обзор модуля 1 и сравнение инструментов
2. Создание приложения в модуле 2
3. Обзор возможностей агентов в модуле 3
4. Навыки + субагенты в модуле 3
5. MCP + собственный агент в модуле 3
6. PR-Agent в модуле 4
7. Semgrep MCP + Agent Scan в модуле 4
8. K8sGPT в модуле 4
9. Управление использованием LiteLLM/Ollama в модуле 4
10. Необязательная демонстрация HolmesGPT в модуле 4

<a id="why-this-order"></a>
## Почему именно такой порядок

В таком порядке учащиеся получат работающее приложение ещё до того, как им потребуется разбираться в глубокой настройке агентов и инструментах промышленной эксплуатации.

---

<a id="24-instructor-ownership-suggestion"></a>
# 24. Предложение по распределению ответственности между преподавателями

<a id="alex--main-course-flow"></a>
## Alex / основная линия курса

**Оригинал:**

```text
Module 1 framing
Module 2 full-stack app
overall project and cohort structure
```

**Перевод:**

```text
позиционирование модуля 1
full-stack-приложение модуля 2
общая структура проекта и учебного потока
```

<a id="co-instructor-with-coding-agent-expertise"></a>
## Второй преподаватель с опытом работы с агентами для программирования

**Оригинал:**

```text
Module 3 coding agent capabilities
reusable workflows / skills / commands
hooks and guardrails
specialized subagents
plugins and extensions
MCP
custom agents
```

**Перевод:**

```text
возможности агентов для программирования в модуле 3
повторно используемые рабочие процессы / навыки / команды
хуки и защитные ограничения
специализированные субагенты
плагины и расширения
MCP
собственные агенты
```

<a id="securitydevops-contributor-or-research-time"></a>
## Участник с опытом безопасности/DevOps или время на исследование

**Оригинал:**

```text
Module 4 tool selection
PR-Agent
Semgrep MCP
Snyk Agent Scan
K8sGPT
LiteLLM/Ollama
HolmesGPT demo
```

**Перевод:**

```text
выбор инструментов модуля 4
PR-Agent
Semgrep MCP
Snyk Agent Scan
K8sGPT
LiteLLM/Ollama
демонстрация HolmesGPT
```

---

<a id="25-reply-draft-to-co-instructor"></a>
# 25. Черновик ответа второму преподавателю

**Оригинал:**

```text
Hey, this sounds great and aligns well with the 2026 direction.

I’m thinking we move Module 3 away from being only an MCP deep dive and make it about coding agent capabilities more broadly: how agents get context, how they use tools, how we extend them with MCP, skills, hooks, plugins, subagents, and how to build small custom agents.

Since you use Claude extensively, Claude Code can be one concrete demo environment. But we should explain the concepts in a way that transfers to other coding agents too, including Codex, OpenCode, Cursor, GitHub Copilot, Aider, and similar tools.

A possible outcome for the module is an “agent extension pack” for the app built in Module 2:
- project instructions such as AGENTS.md, CLAUDE.md, or equivalent
- one reusable workflow / skill / command
- one specialized subagent
- one hook
- one MCP tool/server
- one small plugin/extension package or custom agent
- a permissions/security note

That would make Module 3 much more useful than just MCP, and it gives students something concrete to add to their project repo.
```

**Перевод:**

```text
Привет! Отличная идея, она хорошо соответствует направлению курса на 2026 год.

Думаю, стоит перестать посвящать модуль 3 только углублённому изучению MCP и шире рассмотреть возможности агентов для программирования: как агенты получают контекст, как используют инструменты, как мы расширяем их с помощью MCP, навыков, хуков, плагинов и субагентов и как создаём небольших собственных агентов.

Поскольку ты много используешь Claude, Claude Code может стать одной из конкретных сред для демонстраций. Но понятия стоит объяснить так, чтобы они были применимы и к другим агентам для программирования, включая Codex, OpenCode, Cursor, GitHub Copilot, Aider и подобные инструменты.

Возможным результатом модуля может стать «пакет расширений агента» для приложения, созданного в модуле 2:
- инструкции проекта, например AGENTS.md, CLAUDE.md или аналог
- один повторно используемый рабочий процесс / навык / команда
- один специализированный субагент
- один хук
- один инструмент/сервер MCP
- один небольшой пакет плагина/расширения или собственный агент
- заметка о разрешениях/безопасности

Так модуль 3 станет гораздо полезнее, чем просто раздел о MCP, а студенты получат конкретный результат, который смогут добавить в репозиторий своего проекта.
```

---

<a id="26-source-notes-checked-for-this-proposal"></a>
# 26. Источники, проверенные при подготовке предложения

Студентам необязательно их читать, но они легли в основу предложения и должны пригодиться преподавателям.

<a id="claude--module-3"></a>
## Claude / модуль 3

- [Обзор Claude Code](https://code.claude.com/docs/en/overview) — Claude Code читает кодовые базы, редактирует файлы, запускает команды, интегрируется с инструментами и доступен в терминале, IDE, настольном приложении и браузере.
- [Документация Claude Code по MCP](https://code.claude.com/docs/en/mcp) — MCP соединяет Claude Code с внешними инструментами, источниками данных, базами данных и API.
- [Документация Claude Code по навыкам](https://code.claude.com/docs/en/skills) — навыки используют `SKILL.md`, могут вызываться слеш-командами и полезны для повторяемых рабочих процессов.
- [Документация Claude Code по хукам](https://code.claude.com/docs/en/hooks) — хуки представляют собой команды оболочки, HTTP-эндпоинты или промпты LLM, выполняемые в определённых точках жизненного цикла.
- [Документация Claude Code по субагентам](https://code.claude.com/docs/en/sub-agents) — субагенты являются специализированными ассистентами с собственным контекстом, инструментами и разрешениями.
- [Документация Claude Code по плагинам](https://code.claude.com/docs/en/plugins) — плагины упаковывают навыки, агентов, хуки и MCP-серверы для совместного использования.
- [Документация Claude Agent SDK](https://code.claude.com/docs/en/agent-sdk) — Agent SDK поддерживает собственных агентов на Python/TypeScript с инструментами и циклом работы Claude Code.
- [Архитектура Model Context Protocol](https://modelcontextprotocol.io/docs/learn/architecture) — клиент-серверная архитектура MCP, инструменты, ресурсы, промпты и транспорты.

<a id="module-4-tools"></a>
## Инструменты модуля 4

- [Репозиторий PR-Agent на GitHub](https://github.com/The-PR-Agent/pr-agent) — ИИ-агент для ревью PR с открытым исходным кодом и поддержкой `/describe`, `/review`, `/improve`, `/ask` и журнала изменений.
- [Semgrep MCP Server](https://github.com/semgrep/mcp) — MCP-сервер для сканирования кода на уязвимости с помощью Semgrep.
- [Snyk Agent Scan](https://github.com/snyk/agent-scan) — сканер безопасности ИИ-агентов, MCP-серверов и навыков агентов. Старый URL `invariantlabs-ai/mcp-scan` перенаправляет сюда.
- [K8sGPT](https://github.com/k8sgpt-ai/k8sgpt) — диагностика Kubernetes с ИИ-объяснениями и режимом MCP-сервера.
- [HolmesGPT](https://github.com/HolmesGPT/holmesgpt) — SRE-агент с открытым исходным кодом для расследования инцидентов промышленной эксплуатации и их первопричин; проект CNCF Sandbox.
- [LiteLLM](https://github.com/BerriAI/litellm) — ИИ-шлюз с открытым исходным кодом для множества провайдеров LLM с виртуальными ключами, учётом затрат, защитными ограничениями, маршрутизацией и логированием.
- [Ollama](https://github.com/ollama/ollama) — средство локального запуска моделей с REST API.
- [Stakpak](https://github.com/stakpak/agent) — необязательный DevOps-агент, который можно упомянуть или продемонстрировать.

<a id="tool-landscape--module-1-watchlist"></a>
## Обзор инструментов / список наблюдения для модуля 1

- [Материал о Google Antigravity](https://www.theverge.com/news/822833/google-antigravity-ide-coding-agent-gemini-3-pro) — инструмент программирования с агентом в центре, редактором, терминалом, браузером и проверкой по создаваемым артефактам.
- [Материал о Z.ai ZCode](https://www.businessinsider.com/z-ai-zcode-ai-coding-tool-chinese-startup-lower-cost-2026-7) — новый инструмент программирования Z.ai; стоит следить за его развитием.
- [Материал о Claude Cowork](https://www.techradar.com/pro/put-claude-to-work-claude-can-now-use-your-computer-autonomously-you-just-have-to-tell-it-what-to-do) — графический/автономный рабочий ассистент Claude; упоминать осторожно как смежный продукт в категории рабочих сред, а не как основной инструмент программирования.

---

<a id="27-final-recommendation"></a>
# 27. Итоговая рекомендация

Принять структуру из четырёх модулей.

Самые важные изменения:

**Оригинал:**

```text
1. Rename Module 1 from vibe coding to AI-native developer workflow.
2. Keep Module 2 as the main end-to-end app build.
3. Convert Module 3 from MCP-only to coding agent capabilities:
   MCP + skills + hooks + subagents + plugins + custom agents.
4. Make Module 4 a focused open-source AI security/audit/DevOps module:
   PR-Agent + Semgrep MCP + Snyk Agent Scan + K8sGPT + LiteLLM + Ollama,
   with HolmesGPT as optional/instructor demo.
```

**Перевод:**

```text
1. Переименовать модуль 1: вместо вайб-кодинга — рабочий процесс разработчика с ИИ в основе.
2. Сохранить модуль 2 как основной модуль создания приложения от начала до конца.
3. Перевести модуль 3 с одного MCP на возможности агентов для программирования:
   MCP + навыки + хуки + субагенты + плагины + собственные агенты.
4. Сделать модуль 4 специализированным модулем ИИ-инструментов с открытым исходным кодом для безопасности/аудита/DevOps:
   PR-Agent + Semgrep MCP + Snyk Agent Scan + K8sGPT + LiteLLM + Ollama,
   с HolmesGPT как необязательным инструментом/демонстрацией преподавателя.
```

Это придаёт курсу ясную направленность на 2026 год:

> **Создавайте с помощью ИИ, расширяйте агента, затем безопасно проверяйте и эксплуатируйте результат.**
