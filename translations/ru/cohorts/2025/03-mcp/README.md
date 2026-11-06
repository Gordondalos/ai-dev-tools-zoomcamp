> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/cohorts/2025/03-mcp/README.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.
> **Архив курса 2025.** Исторические инструкции, даты и ссылки сохранены, включая встречающиеся в исходнике упоминания 2026 года.

<a id="module-3--mcp-deep-dive--agents-developer-centric-servers"></a>
# Модуль 3 — Подробно о MCP и агентах (серверы для разработчиков)

Видео:

* [▶️ Смотреть запись практикума](https://www.youtube.com/watch?v=0IhZdcjddo4&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)
* [Рабочая демонстрация](https://www.youtube.com/watch?v=HYHv_S141CU&list=PL3MmuxUbc_hLuyafXPyhTdbF4s_uNhc43)
* О настройке mcp-клиента читайте здесь: [clients.md](clients.md)

> Примечание: во время прямой трансляции возникли проблемы с демонстрацией. Рабочую версию смотрите в «Рабочей демонстрации».

<a id="overview"></a>
## Обзор

<a id="all-about-mcp"></a>
### Всё о MCP

- Что такое MCP и как он связывает ИИ-инструменты, серверы и клиенты
- Как использовать базовые сущности MCP: инструменты, ресурсы и промпты
- Сравнение способов обмена данными MCP: stdio и HTTPS

<a id="using-mcp-servers-for-developer-workflows"></a>
## MCP-серверы в рабочих процессах разработчика

- Использование Context 7 для актуальной документации и отладки (Airflow, Astro)
- Настройка VSCode с MCP-серверами
- Автоматизация исправления кода рабочих процессов по актуальной документации
- Генерация и публикация записей в блоге hashnode на ходу


<a id="demo-flow"></a>
## Ход демонстрации


<a id="part-1-intro-to-mcp"></a>
### Часть 1: введение в MCP

<a id="1-clone-the-demo-code-repo"></a>
#### 1. Клонируйте репозиторий с демонстрационным кодом

[Клонируйте этот репозиторий - https://github.com/thelearningdev/mcp-ai-dev-workflow](https://github.com/thelearningdev/mcp-ai-dev-workflow)

<a id="2-setting-up-python-environment"></a>
#### 2. Настройте окружение Python

Убедитесь, что установлен python 3.12+

```
cd code
uv sync
uv venv
source .venv/bin/activate
```

<a id="3-play-with-your-server"></a>
#### 3. Поэкспериментируйте с сервером

После активации виртуального окружения выполните...

```
cd 0-mcp-demo/stdio/
python stdio_server.py
```
В терминале появится `starting server` 

Теперь вставляйте запросы JSON-RPC по одной строке

1. Инициализируйте клиент

```
{"jsonrpc":"2.0","id":1,"method":"initialize","params":{"protocolVersion":"2024-11-05","capabilities":{},"clientInfo":{"name":"test-client","version":"1.0.0"}}}
```

2. Отправьте уведомление об инициализации

```
{"jsonrpc":"2.0","method":"notifications/initialized"}
```

> Примечание: JSON-ответа на этот шаг не будет

3. Получите список инструментов

```
{"jsonrpc":"2.0","id":2,"method":"tools/list"}
```

4. Вызовите инструмент получения погоды

```
{"jsonrpc":"2.0","id":3,"method":"tools/call","params":{"name":"get_weather","arguments":{"city":"London"}}}
```

Поздравляем 🎉 Вы успешно вызвали первый инструмент MCP в режиме stdio.

<a id="4-lets-visualize-these-features-in-mcp-inspector"></a>
#### 4. Посмотрим на эти возможности в MCP inspector

**1. Установите `mcp-inspector`**

```
npx @modelcontextprotocol/inspector
```

Если node не установлен, используйте установку через brew

```
brew install mcp-inspector
mcp-inspector
```

В MCP inspector, который откроется в браузере: `http://localhost:6274/?MCP_PROXY_AUTH_TOKEN=<some-token-here>`  


**2. Запишите две вещи**

- Путь к вашему окружению python  
    - Введите в терминале `which python`, чтобы получить ответ вида `<YOUR_BASE_PATH>/mcp-for-ai-dev-course/code/.venv/bin/python` 
- Путь к `stdio_server.py`
    - В vscode щёлкните правой кнопкой по `stdio_server.py` и скопируйте путь `<YOUR_BASE_PATH>/mcp-for-ai-dev-course/code/0-mcp-demo/stdio/stdio_client.py` 

> Замените `YOUR_BASE_PATH` правильным путём на вашем компьютере

**3. Добавьте эти значения в MCP inspector**

1. В поле command добавьте путь к python
2. В поле Arguments добавьте путь к файлу stdio_server.py

> Примечание: также можно выполнить

```
npx @modelcontextprotocol/inspector <command> <server_file_path>
```
---

```
npx @modelcontextprotocol/inspector \
  <YOUR_BASE_PATH>/mcp-for-ai-dev-course/code/.venv/bin/python \
  <YOUR_BASE_PATH>/mcp-for-ai-dev-course/code/0-mcp-demo/stdio/stdio_server.py
```

Можно также запустить сервер в режиме http и подключить его к инспектору

---

<a id="part-2-mcp-on-ai-dev-workflow"></a>
### Часть 2: MCP в рабочем процессе ИИ-разработки

> Для этой демонстрации нужны Vscode и github copilot (бесплатной версии должно хватить)

1. Создайте аккаунт в [context7](https://context7.com/), скопируйте API-ключ и сохраните его для дальнейших шагов

> Мы не связаны с context7: это просто хорошо работающий инструмент

![Скриншот](../../../../../images/mcp/context7-apikey.png)

2. На вкладке libraries в context7 выберите нужные библиотеки

![Скриншот](../../../../../images/mcp/context7-libraries.png)

3. В MCP inspector добавьте mcp url и изучите инструменты в режиме HTTP.

![Скриншот](../../../../../images/mcp/mcp-inspector-with-context7.png)

4. В VScode установите mcp-серверы через расширения или файл `mcp.json`

<a id="write-code"></a>
### Напишите код

1. Выберите библиотеку, которую хорошо знаете. В демонстрации я выбрал Airflow
2. С помощью [Airflow Quickstart](https://airflow.apache.org/docs/apache-airflow/3.0.6/start.html) можно быстро воспроизвести окружение из демонстрации
3. Отключите context7 и попросите ассистента написать код
4. Включите context7 и попросите ассистента исправить написанный код: `use the latest docs` (перевод: «используй самую свежую документацию»). 
5. Попробуйте другие MCP-серверы: github для создания PR, hashnode для публикации статьи, notion для записи заметок
6. Интересные [MCP-серверы можно найти в этом каталоге](https://github.com/mcp?utm_source=vscode-website&utm_campaign=mcp-registry-server-launch-2025)

<a id="relevant-links"></a>
## Полезные ссылки

- [Model Context Protocol — сайт](https://modelcontextprotocol.io/)
- [Анонс MCP от Anthropic](https://www.anthropic.com/news/model-context-protocol)
- [TheLearningDev — демонстрационный репозиторий](https://github.com/thelearningdev/mcp-ai-dev-workflow)
- [Использование MCP-серверов в VScode](https://code.visualstudio.com/docs/copilot/customization/mcp-servers)
