# Montauto Platform — Private-Code Case Study

> **Private project, public case study.** The production application's source repository is private. This repository documents the product, architecture, workflows, and technologies at a non-sensitive level. No application source code, credentials, internal configuration, or real volunteer or organization data is published here.

## At a glance

Montauto is a conservation and heritage platform that connects public information about preservation work with the people coordinating and carrying it out. The application combines a public-facing experience with authenticated volunteer workflows and role-aware dashboards.

**My role:** Volunteer full-stack developer  
**Application shape:** Angular web client → Spring Boot REST API → relational database  
**Project status:** Ongoing

## The problem it addresses

Conservation initiatives need to communicate the importance and state of heritage work while coordinating people doing practical tasks. When project information, task assignments, and progress updates are scattered across separate channels, it becomes harder for volunteers and coordinators to know what needs attention and what has been completed.

Montauto brings those activities into one platform: visitors can learn about the work, while authenticated users use task and progress workflows appropriate to their role.

## People and access

The platform has a public experience and authenticated areas. Access to protected operations is controlled by backend authentication and role-based authorization.

- **Public visitors** can access public conservation and heritage information.
- **Volunteers** work with assigned tasks and report progress through authenticated workflows.
- **Coordinators or administrators** use role-appropriate dashboards and management capabilities.

The public case study intentionally describes roles by responsibility rather than exposing organization-specific account or permission details.

## End-to-end product flow

1. **Discover the work.** A visitor opens the public site and reads information about conservation and heritage initiatives.
2. **Authenticate for protected work.** A volunteer signs in before accessing non-public task workflows. The backend validates the request and applies authorization rules.
3. **Coordinate tasks.** Authenticated users see task information and progress relevant to their permissions. Coordinators can use role-aware dashboard capabilities to oversee work.
4. **Record progress.** Volunteers update task progress through the application. The Angular client sends those actions to the REST API; the backend validates and processes them before persistence.
5. **Review the current state.** The application reads the stored task and progress data back through the API so permitted users can follow the work.
6. **Maintain the system safely.** Database schema changes are versioned with Flyway. H2 supports local and testing scenarios, while MySQL configuration is supported for the relational data layer.

This is a high-level description of the implemented project. It omits private business rules, endpoint names, deployment topology, and operational data.

## System overview

```text
Public visitor / Volunteer / Coordinator
                    │
                    ▼
       Angular application
       TypeScript · Angular Material
                    │ HTTPS-style REST integration
                    ▼
       Spring Boot application
       Authentication · authorization
       Workflow rules · REST endpoints
                    │
                    ▼
       Relational persistence
       JPA · Flyway · H2 / MySQL
```

The frontend and backend are separate application layers. The client presents role-appropriate screens and calls the API. The Spring Boot service is responsible for validating protected actions, enforcing access rules, coordinating application logic, and persisting approved changes.

## Architecture and engineering

### Frontend

The Angular application provides the public information experience and the authenticated task/dashboard flows. TypeScript structures client-side behavior, and Angular Material supplies interface components. The project also includes server-side rendering support.

### Backend API

Spring Boot exposes REST capabilities for the web client. Spring Security and JWT support authentication and protected access. Authorization is enforced in the backend so that access decisions do not depend only on hiding or showing frontend controls. Spring Data JPA connects application workflows to relational persistence.

### Data and schema changes

The data layer uses relational storage. Flyway tracks schema evolution as ordered migrations so that database changes can be applied consistently across environments. H2 is available for development and testing; MySQL configuration is supported for the application.

### Quality and delivery

The project uses the Maven Wrapper and npm-based frontend tooling. Git supports source-control workflows. Testing and deployment work are part of my full-stack contribution; private pipeline details and environment configuration are not included in this public write-up.

## My contribution

As a volunteer full-stack developer, I contribute across the Angular client and Java backend, including:

- Building and integrating frontend workflows with REST APIs
- Implementing backend capabilities with Spring Boot
- Designing and refining relational persistence
- Working on authentication and role-aware access
- Testing application behavior across layers
- Supporting deployment-related work

## Technology

- **Languages:** Java, TypeScript, HTML, CSS
- **Frontend:** Angular, Angular Material, server-side rendering
- **Backend:** Spring Boot, Spring Security, Spring Data JPA
- **API and access:** REST, JWT, role-based authorization
- **Database:** H2 for local/testing scenarios; MySQL configuration
- **Schema management:** Flyway
- **Build and collaboration:** Maven Wrapper, npm, Git, automated tests

## Screenshots

Screenshots will be added later. They will use synthetic or anonymized data and will be reviewed to avoid exposing private operational information.

## Privacy boundary

The original source repository is private. This public case study is a product and engineering overview, not a copy of that repository. It excludes source files, secrets, private endpoints, deployment configuration, real volunteer records, and internal organization data.
