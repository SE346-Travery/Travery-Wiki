# Source: DEPLOYMENT_GUIDE.md

## Summary
A comprehensive guide detailing the infrastructure architecture, observability model, Git strategy, CI/CD pipelines, and configuration details for the Travery Backend system.

### Key Sections
- **System Architecture**: Distributed architecture isolating production execution (Server 1) from the observability hub (Server 2).
- **Component Analysis**: Details functions of Nginx, Spring Boot, PostgreSQL, Redis, Grafana Alloy, Prometheus, Loki, and Grafana.
- **Component Interactions**: Deep dives into JDBC, RESP, and the push-based observability model using Alloy.
- **Git Strategy**: Structured GitHub Flow with `main`, `test`, and `feature/*` branches.
- **CI/CD Pipelines**: Detailed workflows for Continuous Integration (Maven tests, formatting) and Continuous Deployment (SSH-based Docker updates).
- **Configuration**: Deep-dives into Docker Compose, Dockerfile, Nginx config, and Alloy configuration.
- **Provisioning & Troubleshooting**: Guides for initial setup and common pitfalls like OOM and SSH failures.

## Identified Entities
- **Organizations**: [[travery]]
- **Concepts**: [[deployment-architecture]], [[observability-model]], [[monitoring-stack]], [[ci-cd-pipeline]], [[git-strategy]], [[github-flow]], [[branch-protection-rules]], [[docker-dns]], [[reverse-proxy]]
- **Entities**: [[User]], [[Tour]], [[Hotel]], [[Postgres]], [[Redis]], [[Nginx]], [[Grafana-Alloy]], [[Prometheus]], [[Loki]], [[Grafana]]
