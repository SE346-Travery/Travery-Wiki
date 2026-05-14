# Source: Travery-Backend

## Summary
The backend service for the **Travery** platform, built using Java and Spring Boot. It handles core business logic, authentication, data management, and monitoring.

**Technical Stack**:
- **Framework**: Spring Boot 4.0.4, Java 25 (with **Virtual Threads** enabled).
- **Database**: PostgreSQL 17
- **Caching**: Redis 8
- **Search Engine**: **Hibernate Search 8.0.0.Final** with **Lucene** backend. Supports full-text search on [[Tour]] and [[TourInstance]] with indexed fields like name, description, and status.
- **Authentication**: JWT (JSON Web Tokens) with [[otp]] verification. Added `spring-boot-starter-security-oauth2-client` for future social login support.
- **Third-party Services**: Cloudinary (Image/Video storage), Gmail SMTP (Email notifications).
- **Code Quality**: **Spotless** (Google Java Format) and **SpotBugs** integrated into the Maven build.
- **Monitoring**: Grafana Alloy, Loki, Prometheus, and Grafana for log and metric collection.

**Infrastructure**:
- Dockerized using `Dockerfile` and `docker-compose`.
- Nginx used as a reverse proxy to block external access to actuator endpoints.

## Identified Entities
- **Organizations**: [[travery]]
- **Entities**: [[User]], [[Tour]], [[Destination]], [[TourInstance]], [[Hotel]], [[Coach]], [[ChatSession]]
- **Concepts**: [[otp]], JWT, Token Blacklist, Refresh Token Rotation, Full-text Search (Lucene)

## Update History
### [2026-05-14] Refactoring & Search Optimization
- **Entity Shift**: `min_participants` and `max_participants` moved from `TourInstance` to `Tour`.
- **New Fields**: Added `average_rating` and `duration_days` to [[Tour]].
- **Search**: Implemented `@Indexed` on `Tour` (name, description, destination) and `TourInstance` (start_date, status).
- **Schema**: `refund_policy_rules` changed from `hours_before_departure` to `days_before`.
