> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/cohorts/2025/03-mcp/clients.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.
> **Архив курса 2025.** Исторические инструкции, даты и ссылки сохранены, включая встречающиеся в исходнике упоминания 2026 года.

<a id="configuration"></a>
# Настройка 

<a id="github-copilot"></a>
## GitHub Copilot 

...

<a id="codex"></a>
## Codex
<a id="codex--mcp-setup-vs-code--linux"></a>
### Настройка CODEX + MCP (VS Code — Linux)

> Эти шаги рассчитаны на **Linux**. В Windows или macOS пути и команды могут отличаться.

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
- Нажмите кнопку **Settings (⚙️)** («Настройки»)  
- Откроется файл `config.toml`, используемый Codex

<a id="4-configure-the-mcp-server-linux"></a>
#### 4. Настройте MCP-сервер (Linux)
Добавьте в `config.toml` следующее:
```toml
    [codex.mcp_servers.hw3-mcp]
    command = "uv"
    args = [
      "--directory",
      "/path/to/ai-dev-tools-zoomcamp/03-mcp",
      "run",
      "python",
      "main.py"
    ]
    startup_timeout_sec = 10
    tool_timeout_sec = 60
    enabled = true
```
**О названии сервера**  
`hw3-mcp` — всего лишь метка конфигурации. Её можно заменить любым понятным названием, например `local-mcp` или `mcp-tools`. Название должно быть уникальным, но не обязано совпадать с папкой проекта или каким-либо именем в коде.

<a id="5-trust-the-project"></a>
### 5. Добавьте проект в доверенные
Также добавьте:
```TOML
    [projects."/path/to/ai-dev-tools-zoomcamp"]
    trust_level = "trusted"
```
<a id="6-expected-behavior"></a>
### 6. Ожидаемое поведение
- Codex доступны **инструменты** MCP  
- Если сервер предоставляет только инструменты, Codex сообщит, что **ресурсов MCP нет** (это ожидаемо)


<a id="cursor"></a>
## Cursor 

...

<a id="antigravity"></a>
## Antigravity 


...
