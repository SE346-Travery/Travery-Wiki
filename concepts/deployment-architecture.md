# Concept: Deployment Architecture

## Definition
The physical and logical layout of the [[Travery]] system's infrastructure, designed for scalability and observability.

## 2-Server Model
The system is divided into two distinct environments to optimize performance and security:
- **Server 1 (Production Hub)**: Handles business logic and user traffic.
  - [[Nginx]] (Reverse Proxy)
  - [[Spring-Boot]] (Application Server)
  - [[Postgres]] (Primary DB)
  - [[Redis]] (Cache/OTP)
  - [[Grafana-Alloy]] (Telemetry Collector)
- **Server 2 (Observability Hub)**: Dedicated to monitoring and logging.
  - [[Prometheus]] (Metrics DB)
  - [[Loki]] (Log Aggregation)
  - [[Grafana]] (Visualization Dashboard)

## Connectivity
- **Internal**: Components on Server 1 communicate via a private Docker bridge network using [[Docker DNS]].
- **Telemetry**: Server 1 "pushes" data to Server 2 via [[Grafana-Alloy]], ensuring that the production server doesn't need to expose internal metrics to the public internet.

## References
- [[deployment-guide]]
- [[monitoring-stack]]
