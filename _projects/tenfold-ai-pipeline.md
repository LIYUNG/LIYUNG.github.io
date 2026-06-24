---
title: TenfoldAI — RAG retrieval platform & AI document pipeline
summary: Built the RAG retrieval infrastructure and the event-driven AWS pipeline, CI/CD, and observability behind TenfoldAI's AI document platform.
period: March 2025 — November 2025
order: 2
thumbnail: /assets/img/projects/tenfold-ai.svg
thumbnail_alt: TenfoldAI — AI platform for RAG retrieval and document processing
tech:
  - AWS CDK
  - Amazon OpenSearch
  - Vector search / RAG
  - Hybrid search
  - Amazon S3
  - SNS / SQS
  - Amazon ECS (GPU)
  - AWS Lambda
  - AWS CodePipeline
  - CloudWatch / X-Ray
  - SSO
  - Stripe (subscriptions)
links:
  - label: Overview
    url:
  - label: Repository
    url:
---
Worked on the AI platform team at TenfoldAI, applying **AWS best practices** across retrieval infrastructure, data pipelines, delivery, and secure access. The platform was built with a co-authoring team; the items below are the parts I designed and owned.

### RAG retrieval infrastructure

Sole author of the **retrieval infrastructure** (AWS CDK) for the platform's Retrieval-Augmented Generation (RAG), built on a **self-managed Amazon OpenSearch** store with **hybrid (semantic + keyword) search**.

The key contribution was a **build-vs-managed decision**: after investigating the use case, I chose a self-managed retrieval store over a fully-managed knowledge-base service so the team kept **control of the embedding model** and could **reuse its existing embeddings without a costly re-index** — a choice I backed with an architecture-decision document. Hardened the infrastructure with encryption, enforced HTTPS, Cognito-authenticated access, and infrastructure tests.

### AI document-ingestion pipeline

Primary author of the **AWS infrastructure** for an **event-driven document-ingestion pipeline** — documents flow through **S3 → SNS → SQS** (with dead-letter queues) into containerized **Lambda** workers behind a secured REST API, with **GPU-backed ECS** workers autoscaling for heavy batch processing. The embedding and retrieval logic was built by co-authors; I owned the infrastructure, multi-region delivery, **CodePipeline CI/CD**, observability (**CloudWatch alarms → Slack**, X-Ray tracing), and test coverage. Led a major pipeline upgrade that re-architected the event flow for scalability and resilience.

### Architecture & design leadership

Reviewed **team architectures** and **design documents**, and guided **technical decision-making** — trade-offs on reliability, cost, security, and delivery speed were documented so the team had a clear, shared rationale before build-out.

### Billing & subscriptions (Stripe)

Integrated **Stripe** for **subscription-based payments**, wired through an **event-driven** architecture on AWS (webhooks, queues, and decoupled workers). The design prioritized **scalability**, **high availability**, and **operational resilience**—billing state changes propagate asynchronously so core services stay available under load and partial failures are isolated rather than cascading.

### CI/CD modernization

Migrated a **legacy deployment workflow** to a modern **AWS CodePipeline**–based CI/CD setup—improving repeatability, auditability, and release velocity for the team.

### Identity & internal access

Introduced **SSO** for the **internal website** and tooling, replacing long-lived credentials that had to be **refreshed on a fixed schedule** just to regain access. Engineers and operators sign in through SSO instead of managing rotating permanent keys, and **internal tools and pages sit behind Amazon Cognito authentication**.

---

*Technical specifics are kept general here to respect TenfoldAI confidentiality. Happy to go deeper in conversation.*
