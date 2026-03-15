# DTS Developer Challenge

This repository contains a full-stack task management application built for the HMCTS DTS developer assessment. It combines a Spring Boot backend API with a Node.js/Express frontend using the GOV.UK Design System, with Docker Compose provided to run the full stack together in a consistent local environment.

This application includes the current feature set:

- Task creation, viewing, editing, status updates, and deletion
- Backend validation and persistence with PostgreSQL
- GOV.UK-styled frontend focused on accessibility and clear task workflows
- Docker Compose setup for the frontend, backend, and database
- Swagger UI for quick API inspection and manual testing

## Project Structure

```text
dts-developer-challenge/
├── docker-compose.yml
├── hmcts-dev-test-backend/
└── hmcts-dev-test-frontend/
```

## Prerequisites

- Git
- Docker Desktop
- Docker Compose
- Java 21 if you want to run the backend locally
- Node.js `20.11.1` and Yarn `3.8.2` if you want to run the frontend locally

## Clone the repository

```bash
git clone https://github.com/Usman-Younas7/hmcts-dts-developer-challenge.git
cd hmcts-dts-developer-challenge
git submodule update --init --recursive
```

The submodule command is included because the frontend and backend will be used as sub-repositories in the parent repository.

## Run the full application

From the repository root:

```bash
docker compose up --build
```

To stop everything:

```bash
docker compose down
```

## Service endpoints

- Frontend: [http://localhost:3100](http://localhost:3100)
- Backend API: [http://localhost:4000](http://localhost:4000)
- Swagger UI: [http://localhost:4000/swagger-ui.html](http://localhost:4000/swagger-ui.html)

## Testing

### Frontend

Run from `hmcts-dev-test-frontend`:

```bash
yarn test:unit
yarn test:functional
yarn test:coverage
```

The frontend functional tests expect the application to be running, for example at `http://localhost:3100`.

### Backend

Run from `hmcts-dev-test-backend`:

```bash
./gradlew test
./gradlew functional
./gradlew jacocoTestReport
```

For service-specific local development, see the README files inside [hmcts-dev-test-frontend](/Users/nasim/Workspace/GeminiProjects/dts-developer-challenge/hmcts-dev-test-frontend/README.md) and [hmcts-dev-test-backend](/Users/nasim/Workspace/GeminiProjects/dts-developer-challenge/hmcts-dev-test-backend/README.md).
