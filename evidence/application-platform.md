# Application Platform — Verified Project Evidence

**Status:** Ongoing development  
**Verification date:** 17 September 2026  
**Evidence source:** Live read-only inspection of the development project on the self-hosted server.

## Current project structure

The project is organised into separate areas for:

- backend
- frontend
- mobile
- reports
- reviews
- references

The currently inspectable mobile and backend areas contain real source, test and build configuration rather than placeholder documentation alone.

## Backend

The backend currently includes:

- **Java 21**
- **Spring Boot 3.3.x**
- Maven project configuration
- Spring Web dependency
- Spring Boot Actuator
- Docker Compose development definition
- dedicated data and log volumes
- `no-new-privileges` container security option

The current backend source tree contains **3 Java source files**, including the application entry point, a health controller and a category controller.

## Mobile application

The mobile application is a Flutter project described in its project metadata as a local-services marketplace with request-linked conversations.

Current source evidence includes:

- **47 Dart files** under `lib/`
- **7 Dart test files** under `test/`
- organised application, data, domain, theme, core and feature layers
- Android, iOS, Linux, macOS, Windows and web target scaffolding
- project architecture/migration documentation

## Development automation evidence

The project currently contains **6 generated report files** from automated development/review workflows. These reports provide a dated evidence trail of work and review activity without requiring publication of private runtime history.

## Accuracy note

This evidence page describes what is present in the current inspected project tree. It does not claim that every technology used historically remains present in the current build. In particular, the live backend Compose file inspected on 17 September 2026 does not define a PostgreSQL service, so PostgreSQL is not presented here as a verified dependency of this current snapshot.

## Publication policy

Source excerpts and screenshots will be added selectively after sanitisation. Credentials, private configuration, environment files and internal-only application data will not be published.
