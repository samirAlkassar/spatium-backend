# notes-backend

Spring Boot 3.5 · Java 21 · PostgreSQL · Flyway · modular monolith

## Run
Requirements: Java 21, Maven (or IntelliJ), Docker running.

    mvn spring-boot:run

Postgres starts automatically from docker-compose.yml.
Check: http://localhost:8080/actuator/health

## Structure
Package-by-feature: each module (auth, user, workspace, note) owns its own
entity, repository, service, and controller. Modules talk through services,
never through each other's repositories.

## Database
Schema changes go in src/main/resources/db/migration as new files
(V2__..., V3__...). Never edit a migration that has already run.
