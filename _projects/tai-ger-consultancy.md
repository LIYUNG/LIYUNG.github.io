---
title: TaiGer Consultancy — study-abroad application platform
summary: Full-stack SaaS platform that guides students through the entire German/European university application journey — led design, development, and operations.
period: April 2021 — April 2024
order: 1
thumbnail: /assets/img/projects/taiger.svg
thumbnail_alt: TaiGer Consultancy — study-abroad application platform
tech:
  - React
  - TypeScript
  - Material UI
  - TanStack Query
  - Redux
  - i18next
  - Node.js
  - Express
  - MongoDB
  - AWS Lambda
  - Amazon S3
  - Amazon ECS
  - AWS CDK
  - AWS CloudFormation
  - Vite
  - Vitest
links:
  - label: Demo
    url:
  - label: Repository
    url:
---
A full-stack SaaS platform that takes students applying to German and European universities through the **entire application journey** — onboarding and profiling, document drafting, program selection, application and deadline tracking, all the way to final submission. It serves three roles in one system: students, advising agents, and document editors. As the lead engineer, I drove its design, development, and operations end-to-end.

### What I built

- **Frontend** — a large React + TypeScript single-page app (Material UI, TanStack Query, Redux, React Router) spanning roughly 40 feature modules, with complete **English / 繁體中文 / 简体中文** internationalization. Tooled with Vite and covered by a Vitest test suite.
- **Backend** — REST APIs on Node.js / Express + MongoDB, decomposed into multiple services (core API, transactional email, AWS Lambda jobs) that share a **versioned domain-model npm package**, keeping types and business rules consistent across the system.
- **Collaboration core** — document-revision threads for CVs, motivation letters, and recommendation letters, with versioning, status, and inline feedback. This replaced scattered email and file exchange between applicants, agents, and editors with a single source of truth.
- **Student tooling** — application and deadline tracking, university portal-credential management, the German Uni-Assist / VPD workflow, real-time chat with file attachments, and secure document handling on **Amazon S3** with role-based, multi-tenant access.
- **DevOps** — infrastructure-as-code with **AWS CDK** and CloudFormation, CI/CD pipelines, and CloudFront delivery.

### Outcome

The platform consolidated state, documents, and approvals that previously lived across email threads and shared drives into one workflow — cutting redundant exchange between applicants, agents, and editors, and giving students a clear, guided path from first profile to submitted application.
