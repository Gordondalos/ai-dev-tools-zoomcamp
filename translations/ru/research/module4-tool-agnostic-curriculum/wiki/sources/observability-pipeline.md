> **Русский перевод.** [Исходный файл](https://github.com/Gordondalos/ai-dev-tools-zoomcamp/blob/9b9527b61332f2b742c749c5f9c26272cf7a08bf/research/module4-tool-agnostic-curriculum/wiki/sources/observability-pipeline.md). Снимок: `9b9527b61332f2b742c749c5f9c26272cf7a08bf`.

> **Исследовательский архив.** Это перевод рабочих исследовательских материалов, а не актуальная инструкция. Утверждения, статусы и сведения об инструментах отражают даты исходника и могут устареть; перед практическим использованием проверьте текущую документацию.

<a id="opentelemetry-and-grafana-observability-pipeline-guidance"></a>
# Рекомендации OpenTelemetry и Grafana по конвейеру наблюдаемости

Основные источники:

- [FACT observability-pipeline] https://opentelemetry.io/docs/collector/deploy/
- [FACT observability-pipeline] https://opentelemetry.io/docs/languages/python/
- [FACT observability-pipeline] https://opentelemetry.io/docs/languages/js/getting-started/browser/
- [FACT observability-pipeline] https://prometheus.io/docs/guides/opentelemetry/
- [FACT observability-pipeline] https://grafana.com/docs/tempo/latest/set-up-for-tracing/
- [FACT observability-pipeline] https://grafana.com/docs/loki/latest/
- [FACT observability-pipeline] https://grafana.com/docs/grafana/latest/datasources/tempo/configure-tempo-data-source/

Кратко: конвейер телеметрии для рабочей эксплуатации разделяет инструментирование, сбор/обработку, хранение и визуализацию и связывает сигналы через согласованные атрибуты ресурсов и идентификаторы трасс.

- [FACT observability-pipeline] OpenTelemetry Collector поддерживает развёртывание в виде агента и шлюза и предоставляет независимую от поставщика границу OTLP между приложениями и системами хранения и обработки телеметрии.
- [FACT observability-pipeline] Между приложениями и хранилищем трасс рекомендуется размещать коллектор/конвейер, поскольку он обеспечивает пакетную отправку, повторные попытки и независимость от доступности системы хранения.
- [FACT observability-pipeline] Grafana может связывать трассы Tempo с логами Loki и метриками Prometheus; переход от трассы к логам требует общих идентификаторов, например идентификаторов трасс и имён сервисов.
- [FACT observability-pipeline] Prometheus поддерживает приём метрик OTLP, но по умолчанию отключает приёмник, поскольку приём без аутентификации может быть небезопасным.
- [FACT observability-pipeline] Трассы и метрики OpenTelemetry для Python стабильны, а сигнал логов ещё находится в разработке; инструментирование браузера экспериментальное и в основном не специфицировано.
- [FACT observability-pipeline] Loki рекомендует метки с низкой кардинальностью и структурированные метаданные для значений с высокой кардинальностью, например идентификаторов трасс, запросов и пользователей.
- [INFERENCE observability-pipeline] Для этого курса стабильное ядро составляют трассы и метрики бэкенда плюс структурированные логи stdout с добавленными идентификаторами трасс; трассировка браузера является полезным необязательным расширением.

Ограничения: документация Grafana естественным образом отдаёт предпочтение Grafana Alloy/Cloud. Исходный OpenTelemetry Collector является более переносимой учебной основой, а Alloy можно упомянуть как дистрибутив для рабочей эксплуатации.

Связанные материалы: [обновлённая архитектура модуля](../concepts/revised-module-architecture.md)

Дата обращения: 2026-08-02. Отдельные страницы постоянно обновляются.
