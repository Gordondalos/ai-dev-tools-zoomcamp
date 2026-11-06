> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/cohorts/2025/01-overview/README.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.
> **Архив курса 2025.** Исторические инструкции, даты и ссылки сохранены, включая встречающиеся в исходнике упоминания 2026 года.

<a id="module-1--introduction-to-vibe-coding"></a>
# Модуль 1 — Введение в вайб-кодинг  

[▶️ Смотреть запись практикума](https://www.youtube.com/watch?v=NSMXQk4Axig&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)


<a id="overview"></a>
## Обзор 

Этот модуль знакомит участников с современными ИИ-инструментами разработки и показывает, как разные категории инструментов могут облегчить работу разработчика. 

- Чат-приложения: отлично подходят для изучения темы и поиска идей, но менее удобны для итеративной разработки.  
- Ассистенты программирования и интеграции с IDE: помогают писать, рефакторить и тестировать код прямо в среде разработки.  
- Генераторы проектов: быстро создают заготовки проектов по запросам на естественном языке.  
- Агенты: более продвинутые системы, которые могут работать с несколькими файлами, выполнять действия через инструменты и автоматизировать рабочие процессы.  


<a id="snake-game-and-chat-applications"></a>
## Игра «Змейка» и чат-приложения

Разработка игры «Змейка» с помощью ChatGPT и Claude

Чат-приложения позволяют быстро получать ответы и создавать прототипы, но часто требуют переключаться между чатом и IDE.  

- [ChatGPT](https://chatgpt.com/) — Универсальная LLM с сильными возможностями программирования.  
- [Claude](https://claude.ai/) — ИИ-ассистент Anthropic, сильный в рассуждениях и работе с длинным контекстом.  
- [DeepSeek](https://www.deepseek.com/en) — Открытая LLM для программирования и анализа, оптимизированная по производительности.  
- [Ernie](https://ernie.baidu.com/) — Платформа больших моделей Baidu.  
- [Microsoft Copilot](https://copilot.microsoft.com/) — Универсальный ИИ-ассистент Microsoft, отдельный от GitHub Copilot.  



<a id="ai-coding-assistants--ide-integrations"></a>
## ИИ-ассистенты программирования и интеграции с IDE  

Эти инструменты встраиваются в редакторы и IDE: предлагают код прямо при вводе, генерируют тесты, редактируют несколько файлов и многое другое.  

- [Claude Code](https://www.anthropic.com/claude-code) — Помощник для программирования с ИИ в командной строке и IDE.  
	```bash
	npm install -g @anthropic-ai/claude-code
	```  
- [GitHub Copilot](https://github.com/features/copilot) — ИИ-помощник GitHub для программирования, интегрированный в IDE, например VS Code и JetBrains.  
- [Cursor](https://cursor.com/) — IDE, изначально построенная вокруг программирования с LLM.  
- [Pear](https://trypear.ai/) — ИИ-ассистент с открытым исходным кодом.  

<a id="3-project-bootstrappers"></a>
## 3. Генераторы проектов  

Генераторы создают целые проекты по запросам на естественном языке. Полезны для быстрого прототипирования.  

- [Bolt.new](https://bolt.new/) — Быстрая генерация full-stack-приложений.  
- [Lovable.dev](https://lovable.dev/) — Создание приложений по запросам с упором на фронтенд и пользовательский интерфейс.  

<a id="4-agents"></a>
## 4. Агенты  

Агенты — автономные помощники программирования, которые объединяют LLM с инструментами чтения и записи файлов, запуска команд и управления проектами.  
Они лежат в основе многих ассистентов и генераторов заготовок проектов.  

- [Anthropic Computer Use](https://github.com/anthropics/anthropic-quickstarts/tree/main/computer-use-demo) — Демонстрация агентов, способных взаимодействовать с компьютерами и файлами.  
	```bash
	docker run \
		-e ANTHROPIC_API_KEY=$ANTHROPIC_API_KEY \
		-v $HOME/.anthropic:/home/computeruse/.anthropic \
		-p 5900:5900 \
		-p 8501:8501 \
		-p 6080:6080 \
		-p 8080:8080 \
		-it ghcr.io/anthropics/anthropic-quickstarts:computer-use-demo-latest
	```  
- [PR Agent](https://github.com/qodo-ai/pr-agent) — Автоматизирует ревью pull request и подготовку предложений.


<a id="homework"></a>
## Домашнее задание

- [Домашнее задание 2026](../../2026/homework/01-ai-native-workflow/homework.md)


<a id="community-notes"></a>
## Заметки сообщества

Вы делали заметки? Ими можно поделиться здесь

* [Заметки Jesus Oviedo](https://github.com/jesusoviedo/ai-dev-tools-zoomcamp/tree/main/week1#module-1--introduction-to-vibe-coding)
* Добавьте ссылку на свои заметки выше этой строки

> **Примечание к навигации:** в исходнике ссылка `../../2026/01-ai-native-workflow/homework.md` пропускает каталог `homework` и не существует в снимке `9b9527b`. Ссылка выше исправлена на проверенный путь `../../2026/homework/01-ai-native-workflow/homework.md`; содержание задания не изменялось.
