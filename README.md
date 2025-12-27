# Blog Platform with Spring Security

A full-stack blog platform with a Spring Boot backend (with Spring Security) and a separate frontend app. This repository contains a Maven-based Spring Boot application in the `blog/` folder and a frontend application in `blog-frontend/`.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Backend (Spring Boot) — `blog/`](#backend-spring-boot---blog)
  - [Run with Maven wrapper](#run-with-maven-wrapper)
  - [Build JAR](#build-jar)
  - [Run with Docker Compose](#run-with-docker-compose)
  - [Tests](#tests)
- [Frontend — `blog-frontend/`](#frontend---blog-frontend)
- [Configuration](#configuration)
- [Development Notes](#development-notes)
- [Contributing](#contributing)
- [License](#license)
- [Author / Contact](#author--contact)

---

## Project Overview

This project is a blog platform built with Spring Boot, secured using Spring Security. It typically provides CRUD operations for blog posts, user authentication/authorization, and a separate frontend client. The backend is located in `blog/` and appears to be a Maven project (includes `pom.xml`, Maven wrapper files and a `docker-compose.yml`). The frontend resides in `blog-frontend/`.

---

## Features

- Spring Boot backend with typical blog features (posts, users, roles).
- Spring Security-based authentication and authorization.
- Docker Compose support for quick local environment setup (see `blog/docker-compose.yml`).
- Separate frontend application in `blog-frontend/`.

---

## Tech Stack

- Backend
  - Java (Spring Boot)
  - Spring Security
  - Maven
- Frontend
  - (See `blog-frontend/` — likely Node-based such as React/Vue/Angular)
- Dev / DevOps
  - Docker & Docker Compose

---

## Repository Structure

- `.gitignore` — top-level gitignore
- `blog/` — Spring Boot backend
  - `.gitattributes`, `.gitignore`
  - `pom.xml`
  - `mvnw`, `mvnw.cmd`
  - `docker-compose.yml`
  - `src/` — application source and resources
- `blog-frontend/` — frontend application (details in the folder)

---

## Prerequisites

- Java 11+ (or the version required by the project)
- Maven (optional if using the included Maven wrapper)
- Node.js & npm/yarn (for frontend, if applicable)
- Docker & Docker Compose (optional, for containerized runs)
- Git

---

## Backend (Spring Boot) — `blog/`

Change into the backend directory:

```bash
cd blog
```

### Run with Maven wrapper

On Unix/macOS:

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

Or, if you have Maven installed:

```bash
mvn spring-boot:run
```

### Build JAR

```bash
./mvnw clean package
# Then run:
java -jar target/<artifact-name>.jar
```

Replace `<artifact-name>.jar` with the produced jar name shown in the `target/` directory after build.

### Run with Docker Compose

A `docker-compose.yml` exists at `blog/docker-compose.yml`. From the `blog` folder you can start the stack:

```bash
cd blog
docker-compose up --build
```

This will build and run services as defined (database, backend, etc.). Inspect `blog/docker-compose.yml` to confirm service names, ports, and environment variables.

### Tests

Run the test suite:

```bash
cd blog
./mvnw test
```

---

## Frontend — `blog-frontend/`

The `blog-frontend/` folder contains the frontend client. Typical steps:

1. Inspect `blog-frontend/package.json` to confirm package manager and scripts.
2. Install dependencies:

```bash
cd blog-frontend
npm install
# or
yarn install
```

3. Start dev server:

```bash
npm start
# or
yarn start
```

4. Build for production:

```bash
npm run build
# or
yarn build
```

Adjust commands according to the actual frontend framework and scripts defined in `package.json`.

---

## Configuration

Backend configuration typically lives in `src/main/resources/application.properties` or `application.yml`. Common settings:

- Database URL / credentials
- JWT or session/security settings
- Server port

If you use Docker Compose, many of these values may be set via environment variables in `blog/docker-compose.yml`.

Example environment variables you might need to set:

- SPRING_DATASOURCE_URL
- SPRING_DATASOURCE_USERNAME
- SPRING_DATASOURCE_PASSWORD
- SPRING_PROFILES_ACTIVE

---

## Development Notes

- Use the Maven wrapper included (`mvnw`) to ensure consistent Maven version across machines.
- Inspect `blog/src/main` for controllers, services, repositories, and security configuration to understand API endpoints and required request formats.
- Check `blog-frontend` for how it communicates with the backend (base API URL / proxy configuration).

---

## Contributing

If you'd like to contribute:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feat/your-feature`.
3. Make changes and add tests if applicable.
4. Commit with a descriptive message (example below).
5. Push to your fork and open a Pull Request against `main`.

Suggested commit message for adding this README:

```
docs: add project README with setup and run instructions
```

Suggested PR title and description:

Title:
```
docs: add README.md with setup and run instructions
```

Description:
```
Adds a README.md describing the repository layout, prerequisites, backend (Spring Boot) and frontend setup steps,
Docker Compose usage, and development notes.
```

---

## License

Add a LICENSE file if one is not present. Choose an appropriate open-source license (MIT, Apache-2.0, etc.) and reference it here.

---

## Author / Contact

Repository owner: srilathamaddineni

For questions about the project, open an issue in this repository or contact the maintainer.

---
