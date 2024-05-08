# «‎Подготовка стенда нагрузочного тестирования: Grafana, Telegraf, InfluxDB, Node Exporter, Prometheus»
## Решения
### Задание 1
* Отредактированный <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/InfluxDB/Dashboards/windows_system.yml">дашборд для InfluxDB</a>, с оф. сайта.
* Отредактированный <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/telegraf.conf">telegraf.conf</a>, с оф. сайта.
* Отредактированный <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/Grafana/Dashboards/Windows%20System%20Metrics-My%20Config.json">дашборд для Grafana</a>,
  с оф. сайта.
* <a href="https://github.com/Nephedov/Performance-test/blob/main/ScreenshotsMetrics%20Grafana%2BTelegraf%2BInfluxDb/FullSizeScreenshotMetrics.png">Скриншот</a> собранных метрик, в течении 15 минут.

<a href="https://github.com/Nephedov/Performance-test/tree/main/Grafana%2BTelegraf%2BInfluxDB%20Windows">Репозиторий</a> с конфигурациями Grafana + Telegraf + InfluxDB.


### Задание 2
* <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/docker-compose.yml">docker-compose.yml</a> - c node-exporter, prometheus, grafana.
* <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/prometheus/prometheus.yml">prometheus/prometheus.yml</a> - c инструкцией сбора метрик node-exporter.
* <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning/datasources/prometheus.yml">datasources/prometheus.yml</a> -
  с инструкциями подключения prometheus к grafana.
* <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/dashboards/Node%20Exporter%20Without%20NoData%20on%20Windows.json">Node Exporter Without NoData on Windows.json</a> - дашборд отображения метрик в Grafana.
* <a href="https://github.com/Nephedov/Performance-test/blob/main/ScreenshotsMetrics%20Grafana%2BNodeExporter%2BPrometheus/FullSizeScreenshotMetrics.png">Скриншот</a> собранных метрик, в течении 15 минут.


<a href="https://github.com/Nephedov/Performance-test/tree/main/Grafana%2BNodeExporter%2BPrometheus%20Windows">Репозиторий</a> с конфигурациями Grafana + Node-exporter + Prometheus.
## Что было сделано
### Задание 1
* Установлены локально и первично настроены инструменты для снятия, хранения и отображения аппаратных метрик сервера (компьютера):
  * Telegraf.
  * InfluxDb.
  * Grafana.
* Настроен, скачанный с оф сайта, <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/InfluxDB/Dashboards/windows_system.yml">дашборд для InfluxDB</a>,
  на отображение метрик Windows. 
* Отредактирован, созданный автоматически, <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/telegraf.conf">telegraf.conf</a>, для сбора метрик с сервера
  (компьютера):
  * Сбором всех аппаратных метрик.
  * Отправкой метрик в InfluxDB_v2.
  * Интервалом опрашивания 5 сек.
  * Интервалом отправки метрик 60 сек.
* Настроен, скачанный с оф сайта,
  <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BTelegraf%2BInfluxDB%20Windows/Grafana/Dashboards/Windows%20System%20Metrics-My%20Config.json">дашборд для Grafana</a>:
  * Сбор метрик InfluxDB.
  * Отображение метрик Windows, с добавленной метрикой SWAP.
* Зафиксировано отображение собираемых метрик сервера, в течении 15 минут -
  <a href="https://github.com/Nephedov/Performance-test/blob/main/ScreenshotsMetrics%20Grafana%2BTelegraf%2BInfluxDb/FullSizeScreenshotMetrics.png">Скриншот</a>.

### Задание 2
* Создан <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/docker-compose.yml">docker-compose.yml</a>, разворачивающий последние версии:
  * Node-exporter.
  * Prometheus.
  * Grafana.
* Сконфигурирован <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/prometheus/prometheus.yml">prometheus.yml</a>, для сбора метрик Node-exporter.
* Создан репозиторий <a href="https://github.com/Nephedov/Performance-test/tree/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning">provisioning</a> с конфигурационными файлами для Grafana,
  в котором:
  * Сконфигурирован <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning/datasources/prometheus.yml">prometheus.yml</a>,
    в репозитории <a href="https://github.com/Nephedov/Performance-test/tree/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning/datasources">provisioning/datasources</a>,
    для подключения Prometheus к Grafana.
  * Скофигурирован файл <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning/dashboards/all.yml">all.yml</a>,
    в репозитории <a href="https://github.com/Nephedov/Performance-test/tree/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/provisioning/dashboards">provisioning/dashboards</a>,
    в котором указан путь расположения дашборда.
* Сконфигурирован дабшорд отображения метрик -
  <a href="https://github.com/Nephedov/Performance-test/blob/main/Grafana%2BNodeExporter%2BPrometheus%20Windows/grafana/dashboards/Node%20Exporter%20Without%20NoData%20on%20Windows.json">Node Exporter Without NoData on Windows.json</a>.
* Зафиксировано отображение собираемых метрик сервера, в течении 15 минут -
  <a href="https://github.com/Nephedov/Performance-test/blob/main/ScreenshotsMetrics%20Grafana%2BNodeExporter%2BPrometheus/FullSizeScreenshotMetrics.png">Скриншот</a>.


## Описание Задания 1
1. Развернуть систему мониторинга на базе `telegraf` + `influxDB`.
2. Для отображения использовать дашборды `grafana`.
3. Настроить мониторинг на отображение всех аппаратных метрик вашего сервера (компьютера).
4. Cделать частоту отправки метрик каждые 60 секунд, подключить метрики оперативной памяти и swap, жёсткого диска и сети.
5. Сделать скриншоты состояния метрик системы в покое длительностью минимум 15 минут.

## Описание Задания 2
1. Развернуть систему мониторинга на базе  `node-exporter` + `prometheus`.
2. Для отображения использовать дашборды `grafana`.
3. Cделать частоту отправки метрик каждые 36 секунд.
4. Настроить мониторинг на отображение всех аппаратных метрик вашего сервера (компьютера).
5. Сделать скриншоты состояния метрик системы в покое длительностью минимум 15 минут.
