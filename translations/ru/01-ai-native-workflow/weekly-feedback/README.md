> **Пример из исходного репозитория.** Команды выполняйте в исходной папке `01-ai-native-workflow/weekly-feedback`, а не в `translations/ru/`. Этот перевод не содержит копии программы.

> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/01-ai-native-workflow/weekly-feedback/README.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

<a id="weekly-feedback"></a>
# weekly-feedback

Небольшой инструмент командной строки для еженедельного отслеживания состояния проектов.
Зарегистрируйте нужные проекты, каждую неделю добавляйте короткую запись по каждому
(статус, достижения, проблемы, блокирующие факторы, следующие шаги) и получайте сводку,
которую можно вставить в еженедельный отчёт, а также список тех, кто ещё не отчитался.

Нет зависимостей за пределами стандартной библиотеки Python. Данные хранятся
в одном читаемом JSON-файле, для которого можно просматривать изменения и создавать коммиты.

<a id="install"></a>
## Установка

```bash
pip install -e .          # provides `weekly-feedback` and the short alias `wfb`
```

Или запустите прямо из дерева исходников, без установки:

```bash
PYTHONPATH=src python3 -m weekly_feedback --help
```

<a id="quick-start"></a>
## Быстрый старт

```bash
# 1. register the projects you want to track
wfb project add api --name "Billing API" --owner alexey --path ~/code/api --tag core
wfb project add web --name "Web app" --owner sam --tag core

# 2. log the week
wfb add api -s red --score 2 \
    -H "refunds endpoint live" \
    -i "flaky integration tests" \
    -b "vendor sandbox is down" \
    -n "retry the migration"

# ...or just answer the prompts
wfb add web

# 3. read the week
wfb report
wfb pending          # exits 1 if anyone is missing — handy in a cron job
```

`wfb report` выводит:

```markdown
# Weekly feedback - 2026-W30 (Jul 20-26, 2026)

**2/3 projects reported** · 🟢 1 on track · 🔴 1 off track · avg score 3.5/5

## Blockers
- **Billing API**: vendor sandbox is down

## 🔴 Billing API - 2/5
_alexey_

**Highlights**
- refunds endpoint live

**Issues**
- flaky integration tests
...

## No feedback this week
- Docs site (`docs`)
```

Перевод показанного отчёта (сам вывод программы выше сохранён без изменений):

- Еженедельная обратная связь: `2026-W30` (`Jul 20-26, 2026`).
- Отчёт есть по 2/3 проектов: 🟢 1 идёт по плану, 🔴 1 отклонился от плана; средняя оценка 3.5/5.
- Блокирующий фактор для **Billing API**: тестовая среда поставщика недоступна.
- **Billing API**: 🔴 2/5, ответственный _alexey_.
- Достижения: эндпоинт возвратов запущен.
- Проблемы: нестабильные интеграционные тесты.
- На этой неделе нет обратной связи по сайту документации (`docs`).

Блокирующие факторы выносятся в начало, а проекты с красным статусом идут первыми.
Поэтому то, что требует внимания, не затеряется среди благополучных проектов.

<a id="filling-an-entry-from-git"></a>
## Заполнение записи из git

Если для проекта указан `--path`, инструмент может прочитать коммиты за неделю:

```bash
wfb draft api                 # preview what happened, as commit subjects + diffstat
wfb add api --from-git        # record those commits as highlights
wfb add api --from-git -b "still waiting on the vendor"   # combine with your own notes
```

Коммиты слияния, `wip`, `fixup!` и обновления версий зависимостей отфильтровываются.

<a id="commands"></a>
## Команды

| Команда | Назначение |
| --- | --- |
| `project add/list/edit/archive/unarchive/remove` | управление отслеживаемыми проектами |
| `add <key>` | запись или дополнение еженедельной обратной связи по проекту |
| `delete <key>` | удаление одной записи |
| `draft <key>` | предварительный просмотр активности проекта в git за неделю |
| `report` | еженедельная сводка по всем проектам (`--format md\|json`) |
| `show <key>` | динамика и история одного проекта (`--weeks N`) |
| `pending` | проекты без обратной связи; код завершения 1, если есть хотя бы один такой проект |
| `export` | все записи в формате `json` или `csv` |

Полезные флаги: `--week/-w` принимает `2026-W30`, любую дату внутри недели
(`2026-07-22`), `current`, `last` или смещение, например `-2`. `--plain` заменяет
эмодзи статуса на `[G]`/`[Y]`/`[R]`. `--tag` ограничивает `report` и `pending`
одной группой проектов. `-o/--output` записывает результат в файл.

`wfb show api --weeks 8` включает строку динамики, где `⬜` обозначает неделю
без записи:

```
Trend: ⬜⬜🟢🟢🟡🟢🟢🔴  (2026-W23 -> 2026-W30)
```

<a id="where-the-data-lives"></a>
## Где хранятся данные

Путь определяется в следующем порядке:

1. `--file PATH`
2. `$WEEKLY_FEEDBACK_FILE`
3. `./weekly-feedback.json`, если файл существует, чтобы у репозитория мог быть свой файл данных
4. `~/.weekly-feedback/feedback.json`

Повторные вызовы `add` для одного проекта и одной недели по умолчанию **объединяют** данные
(элементы списков добавляются, дубликаты пропускаются, статус и оценка обновляются).
Передайте `--replace`, чтобы вместо этого перезаписать запись. Записи выполняются атомарно.

<a id="development"></a>
## Разработка

```bash
uv run --with pytest python -m pytest      # 62 tests, no network, no fixtures on disk
```

Структура: `weeks.py` (разбор ISO-недель), `models.py` (`Project`, `Entry`,
валидация), `storage.py` (JSON-хранилище), `gitlog.py` (git → черновик записи),
`report.py` (формирование отчётов), `cli.py` (настройка argparse).
