# 📊 Docker Monitoring Infrastructure

Проект разворачивает полноценную систему мониторинга с использованием Docker и Grafana.

## 🧱 Сервисы

- **NGINX** — веб-сервер с включённой статус-страницей `/status`
- **nginx-prometheus-exporter** — экспортирует метрики NGINX для Prometheus
- **Prometheus** — собирает метрики с экспортеров
- **Grafana** — визуализирует метрики и дашборды
- **Loki + Promtail** — сбор и просмотр логов из контейнеров
- **Node Exporter** — экспорт системных метрик хоста

## 📂 Структура

```bash
.
├── docker-compose.yml
├── nginx.conf
├── html/                 # HTML-страницы для NGINX
├── prometheus.yml        # Конфигурация Prometheus
├── grafana/
│   ├── dashboards/       # JSON-дэшборды Grafana
│   └── provisioning/     # Настройки автопровижена
├── loki-config.yaml
├── promtail-config.yaml
```

## 🚀 Запуск

```bash
docker compose up -d
```

## 📈 Доступ

- NGINX: http://localhost:8080
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000 (логин: `admin`, пароль: `admin`)
- Loki API: http://localhost:3100

---

Все метрики автоматически собираются, дашборды и источники данных в Grafana — провиженятся.