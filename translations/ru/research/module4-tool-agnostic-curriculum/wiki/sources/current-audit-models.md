> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/research/module4-tool-agnostic-curriculum/wiki/sources/current-audit-models.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

> **Исследовательский архив.** Это перевод рабочих исследовательских материалов, а не актуальная инструкция. Утверждения, статусы и сведения об инструментах отражают даты исходника и могут устареть; перед практическим использованием проверьте текущую документацию.

<a id="current-openai-and-anthropic-models-for-demanding-code-audit-work"></a>
# Актуальные модели OpenAI и Anthropic для сложного аудита кода

Основные источники:

- [FACT current-audit-models] https://developers.openai.com/api/docs/guides/latest-model
- [FACT current-audit-models] https://developers.openai.com/api/docs/models
- [FACT current-audit-models] https://platform.claude.com/docs/en/about-claude/models/introducing-claude-fable-5-and-claude-mythos-5
- [FACT current-audit-models] https://platform.claude.com/docs/en/manage-claude/api-and-data-retention

Кратко: названные пользователем семейства моделей актуальны, но необходимо различать интерфейсы продуктов, идентификаторы моделей, настройки рассуждения, отказы, стоимость и политики хранения данных.

- [FACT current-audit-models] Текущая флагманская модель OpenAI: `gpt-5.6-sol`; `gpt-5.6` является её псевдонимом, а уровни reasoning effort включают `max`. Поэтому «GPT-5.6 Sol Max» обозначает конфигурацию модели и уровня рассуждения, а не отдельный идентификатор модели.
- [FACT current-audit-models] OpenAI позиционирует GPT-5.6 Sol для сложных рассуждений и программирования и указывает, что защитная проверка кода, исследование уязвимостей, исправления, отладка и обучение безопасности остаются поддерживаемыми сценариями, несмотря на меры кибербезопасности.
- [FACT current-audit-models] Claude Fable 5 (`claude-fable-5`) является наиболее мощной общедоступной моделью Anthropic для сложных рассуждений и длительной агентной работы.
- [FACT current-audit-models] Claude Fable 5 включает классификаторы кибербезопасности и может отказывать в ответе; использование через API требует хранения данных в течение 30 дней и не допускает режима нулевого хранения данных.
- [INFERENCE current-audit-models] Поэтому для конфиденциального закрытого кода может потребоваться решение о провайдере и хранении данных, прежде чем разрешить Fable 5, а резервный процесс должен учитывать отказы по допустимым защитным запросам.
- [INFERENCE current-audit-models] ChatGPT является интерактивным продуктом; если в нём используется GPT-5.6, это не независимая третья модель для достижения консенсуса. Сравнение независимых проверяющих лучше формулировать как OpenAI GPT-5.6 Sol против Anthropic Claude Fable 5 (или другой актуальной модели Claude).

Ограничения: названия моделей, доступность, защитные меры, цены и хранение данных очень быстро меняются. Эти сведения необходимо обновить перед записью курса.

Связанные материалы: [регулярный аудит безопасности](../concepts/recurring-security-audit.md)

Дата обращения: 2026-08-02.
