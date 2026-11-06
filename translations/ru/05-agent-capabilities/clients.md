<a id="configuration"></a>

# Настройка

[Оригинал материала](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/b47dff65161c878d095e288e9f9e5b907f5aa3c6/05-agent-capabilities/clients.md)

<a id="github-copilot"></a>

## GitHub Copilot

...

<a id="codex"></a>

## Codex
<a id="codex--mcp-setup-vs-code--linux"></a>

### Настройка CODEX + MCP (VS Code — Linux)

> Эти шаги рассчитаны на среду **Linux**. В Windows или macOS пути и команды могут отличаться.

<a id="1-install-codex-extension-and-sign-in"></a>

#### 1. Установите расширение Codex и войдите в аккаунт
- Установите **OpenAI Codex** из VS Code Marketplace
- Войдите в свой аккаунт OpenAI

<a id="2-install-the-codex-cli-required"></a>

#### 2. Установите Codex CLI (обязательно)
Выполните в терминале:
```bash
    npm install -g @openai/codex
    codex --version
```
Установка CLI инициализирует конфигурацию Codex и `config.toml`.

<a id="3-open-codex-mcp-settings"></a>

#### 3. Откройте настройки MCP в Codex
- Откройте вкладку **Codex** в VS Code
- Нажмите кнопку **Settings (⚙️)**
- Откроется файл `config.toml`, используемый Codex

<a id="4-configure-the-mcp-server-linux"></a>

#### 4. Настройте MCP-сервер (Linux)
Добавьте в `config.toml` следующее:
```toml
    [codex.mcp_servers.hw3-mcp]
    command = "uv"
    args = [
      "--directory",
      "/path/to/ai-dev-tools-zoomcamp/05-agent-capabilities",
      "run",
      "python",
      "main.py"
    ]
    startup_timeout_sec = 10
    tool_timeout_sec = 60
    enabled = true
```
**Примечание об имени сервера**
`hw3-mcp` — это просто метка в конфигурации. Её можно заменить любым понятным именем (например, `local-mcp` или `mcp-tools`). Имя должно быть уникальным, но не обязано совпадать с именем папки проекта или каким-либо обозначением в коде.

<a id="5-trust-the-project"></a>

### 5. Добавьте проект в доверенные
Также добавьте:
```TOML
    [projects."/path/to/ai-dev-tools-zoomcamp"]
    trust_level = "trusted"
```
<a id="6-expected-behavior"></a>

### 6. Ожидаемое поведение
- **Инструменты** MCP доступны в Codex
- Если сервер предоставляет только инструменты, Codex сообщит, что **ресурсов MCP нет** (это ожидаемое поведение)

<a id="cursor"></a>

## Cursor

...

<a id="antigravity"></a>

## Antigravity

<a id="prerequisites"></a>

### Необходимые условия

- ИИ-помощник Antigravity (Google Deepmind)
- Установленные Node.js и npm (для большинства MCP-серверов)
- API-ключи для сторонних MCP-серверов (если требуются)

<a id="configuration-file-location"></a>

### Расположение файла конфигурации

Antigravity читает конфигурации MCP-серверов из JSON-файла. Файл конфигурации должен называться `mcp.json` и находиться в каталоге вашего проекта.

<a id="basic-configuration-format"></a>

### Базовый формат конфигурации

Создайте файл `mcp.json` со следующей структурой:

```json
{
    "mcpServers": {
        "server-name": {
            "command": "command-to-run",
            "args": [
                "argument1",
                "argument2"
            ]
        }
    }
}
```

<a id="example-adding-context7-mcp-server"></a>

### Пример: добавление MCP-сервера Context7

Context7 предоставляет доступ к документации библиотек и возможности поиска по коду.

<a id="step-1-create-mcpjson"></a>

#### Шаг 1. Создайте mcp.json

```json
{
    "mcpServers": {
        "context7": {
            "command": "npx",
            "args": [
                "-y",
                "@upstash/context7-mcp@latest"
            ]
        }
    }
}
```

<a id="step-2-set-up-api-key-if-required"></a>

#### Шаг 2. Настройте API-ключ (если требуется)

Некоторые MCP-серверы, например Context7, требуют аутентификации:

**В Windows (PowerShell):**
```powershell
$env:CONTEXT7_API_KEY="your-api-key-here"
```

**В Linux/Mac:**
```bash
export CONTEXT7_API_KEY="your-api-key-here"
```

**Постоянная настройка (Windows):**
Добавьте настройку в свой профиль PowerShell или задайте системную переменную окружения.

<a id="step-3-restart-antigravity"></a>

#### Шаг 3. Перезапустите Antigravity

После добавления конфигурации MCP перезапустите Antigravity, чтобы загрузить новый MCP-сервер.

<a id="step-4-verify-mcp-server-connection"></a>

#### Шаг 4. Проверьте подключение к MCP-серверу

После перезапуска Antigravity проверьте, подключён ли MCP-сервер:

1. **В интерфейсе Antigravity:** нажмите меню с **тремя точками (⋮)**
2. **Найдите «MCP Servers»** или аналогичный пункт, показывающий подключённые серверы
3. В списке должны появиться настроенные вами серверы (например, «context7»)

> [!IMPORTANT]
> **Если ваш MCP-сервер не появился:**
> - Убедитесь, что файл `mcp.json` находится в правильном месте
> - Проверьте синтаксис JSON (используйте валидатор JSON)
> - Убедитесь, что Node.js и npm установлены и доступны из командной строки
> - Проверьте правильность имени пакета сервера (например, `@upstash/context7-mcp@latest`)
> - Просмотрите логи Antigravity на наличие сообщений об ошибках
> - Попробуйте вручную выполнить команду MCP в терминале, чтобы проверить её работу:
>   ```powershell
>   npx -y @upstash/context7-mcp@latest
>   ```

> [!TIP]
> Если после выполнения всех шагов Context7 или другой сервер не появился в списке MCP-серверов:
> 1. Ещё раз убедитесь, что синтаксис вашего `mcp.json` точно соответствует примерам
> 2. Проверьте, что у вас есть активное интернет-соединение (оно нужно `npx` для загрузки пакетов)
> 3. Полностью перезапустите Antigravity (закройте и снова откройте приложение)
> 4. Проверьте, нужно ли задать обязательные переменные окружения (например, `CONTEXT7_API_KEY`)

...
