---
title: MeritonAI — custom implant generation & order platform
summary: Full-stack platform where doctors upload a patient skeleton scan to generate a custom implant and place an order — built the React frontend and Node.js backend, designed the event-driven implant-generation pipeline on AWS, mentored a junior engineer, and coordinated the outsourced 3D work.
period: March 2025 — Present
order: 3
thumbnail: /assets/img/projects/meriton-ai.svg
thumbnail_alt: MeritonAI — custom implant generation and order platform
tech:
  - React
  - TypeScript
  - Material UI
  - TanStack Query
  - Vite
  - Vitest
  - Node.js
  - Express
  - MongoDB
  - AWS CDK
  - Amazon S3
  - SNS / SQS
  - Amazon ECS
  - AWS Lambda
links:
  - label: Overview
    url:
  - label: Repository
    url:
---
A full-stack platform for **generating and ordering custom medical implants**. A doctor uploads a **patient skeleton scan**, which kicks off an automated pipeline that **generates a patient-specific implant**; the doctor then reviews and adjusts it in an **interactive 3D viewer** and places an order that moves through a tracked fulfillment workflow. I led the design and build of the web platform end-to-end, **designed the implant-generation pipeline infrastructure**, and **coordinated the outsourced 3D work** the platform is built around.

### Implant-generation pipeline

Designed the **event-driven AWS infrastructure** (AWS CDK) behind implant generation: a doctor's **skeleton-scan upload to Amazon S3** triggers the pipeline through **SNS/SQS** (with dead-letter queues) into containerized **Amazon ECS** workers that run the generation job, with a **Lambda** notification handler signalling completion back to the platform. The design decouples the long-running generation work from the request path so the app stays responsive and partial failures are isolated rather than cascading.

### Full-stack platform

- **Frontend** — a React + TypeScript single-page app (Material UI, TanStack Query) spanning the full workflow: catalogs, orders, organizations, accounts, users, a design/configuration surface, in-app messaging, and task tracking. Multi-tenant by organization, internationalized, tooled with Vite and covered by a Vitest suite.
- **Backend** — REST APIs on Node.js / Express + MongoDB with authentication, role- and organization-scoped access, order and organization management, secure scan/file upload and handling on **Amazon S3**, and the API that initiates implant generation and tracks its result.

### Team & delivery leadership

Worked alongside a **junior engineer**, guiding them through the delivery of **new features** — breaking work into achievable pieces, reviewing their code, and unblocking them as they ramped up on the codebase.

### Coordinating the outsourced 3D work

The 3D part assets and the **interactive 3D viewer** (real-time rendering and deformation of parts in the browser) were produced by an **external vendor**. I owned that collaboration on the engineering side — **translating product needs into clear requirements**, defining the expected deliverables, formats, and integration points so the work dropped cleanly into the platform, **setting and tracking delivery expectations**, and **reviewing each delivery** for quality and fit-for-purpose before it shipped. This kept the outsourced work aligned with what the application actually needed and avoided costly rework downstream.

---

*Details are kept general here to respect confidentiality. Happy to go deeper in conversation.*
