# Source: Travery-Backend

## Summary
The backend service for the **Travery** platform, built using Java and Spring Boot. It handles core business logic, authentication, data management, and monitoring.

**Technical Stack**:
- **Framework**: Spring Boot 4.0.4, Java 25
- **Database**: PostgreSQL 17
- **Caching**: Redis 8
- **Authentication**: JWT (JSON Web Tokens) with [[otp]] verification.
- **Third-party Services**: Cloudinary (Image/Video storage), Gmail SMTP (Email notifications).
- **Monitoring**: Grafana Alloy, Loki, Prometheus, and Grafana for log and metric collection.

**Infrastructure**:
- Dockerized using `Dockerfile` and `docker-compose`.
- Nginx used as a reverse proxy to block external access to actuator endpoints.

## Identified Entities
- **Organizations**: [[travery]]
- **Concepts**: [[otp]], JWT, Token Blacklist, Refresh Token Rotation
