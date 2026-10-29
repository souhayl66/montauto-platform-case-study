# Montauto Platform — Private-Code Case Study

> **Public case study for a private project.** The application's source repository is private. This repository contains project information and approved screenshots only; it does not contain application source code, credentials, or internal configuration.

## Project overview

Montauto Platform is a conservation and heritage project designed to present information about sites and coordinate volunteer work. It brings together public-facing information, volunteer tasks, progress tracking, and role-based dashboards.

## My role

I contribute as a volunteer full-stack developer. My work spans the Java/Spring Boot backend and Angular frontend, including REST API design and integration, database design and optimization, testing, and deployment work.

## How it works

At a high level, the Angular application communicates with a Spring Boot REST API. The backend applies authentication and role-based authorization, handles platform workflows, and persists application data through a relational database. Flyway is used for versioned database changes. The repository uses H2 for local/testing scenarios and supports MySQL configuration.

## Main capabilities

- Public information about conservation and heritage work
- Volunteer task coordination and progress tracking
- Role-based dashboards and access
- Backend/frontend integration through REST APIs

## Technology and tools

- **Languages:** Java, TypeScript, HTML, CSS
- **Backend:** Spring Boot, Spring Security, Spring Data JPA, JWT, Flyway
- **Frontend:** Angular, Angular Material, server-side rendering
- **Data:** H2 for local/testing, MySQL configuration
- **Tools and delivery:** Maven Wrapper, npm, Git, REST APIs, automated tests, deployment workflow

## Engineering approach

The project separates the web client from the backend API. Authentication and authorization are enforced on the backend, database changes are versioned, and the client integrates through defined REST endpoints. Work includes testing across application layers and deployment configuration.

## Screenshots

Screenshots will be added in a later update using synthetic or anonymized data.

## Source code and confidentiality

The original source repository is private. This public case study describes the project at a high level and excludes source files, credentials, private deployment details, and real volunteer or organization data.
