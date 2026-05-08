# Source: Travery-Backend

## Summary
The backend service for the **Travery** platform, built using Java and Spring Boot. It handles core business logic, authentication, data management, and monitoring.

**Technical Stack**:
- **Framework**: Spring Boot 4.0.4, Java 25 (with **Virtual Threads** enabled).
- **Database**: PostgreSQL 17
- **Caching**: Redis 8
- **Search Engine**: **Hibernate Search 8.0.0.Final** with **Lucene** backend for full-text search.
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
- **Concepts**: [[otp]], JWT, Token Blacklist, Refresh Token Rotation, Full-text Search
