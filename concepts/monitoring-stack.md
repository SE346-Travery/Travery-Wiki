# Monitoring Stack

Travery utilizes the Grafana LGTM-like stack (Alloy, Prometheus, Loki, Grafana) for comprehensive system observability.

## Components
- **Alloy**: The primary telemetry collector.
  - Automatically discovers Docker containers via `unix:///var/run/docker.sock`.
  - Scrapes Spring Boot metrics from the `/actuator/prometheus` endpoint.
  - Collects host-level metrics using the `unix_metrics` exporter.
- **Prometheus**: Stores time-series metrics. Alloy pushes metrics to the Prometheus remote write endpoint.
- **Loki**: Centralized logging system. Alloy tails Docker logs, relabels them with container/service names, and pushes them to Loki.
- **Grafana**: The visualization layer used to query and display metrics and logs.

## Configuration Highlights (`alloy/config.yml`)
- **Metrics Scraping**: Targeted at `travery-app:8080` with a 30s interval.
- **Log Processing**: Uses a pipeline to parse JSON logs and extract stream labels before pushing to Loki.
- **Local Debugging**: Includes secondary scrape configurations for local development inspection.
