---
title: TenfoldAI — document pipeline & infrastructure
summary: Led engineering—architecture reviews, design docs, AWS pipeline, CodePipeline, SSO, and Stripe subscriptions on an event-driven platform.
period: March 2025 — November 2025
order: 2
tech:
  - AWS CDK
  - Amazon S3
  - SNS / SQS
  - Amazon ECS (GPU)
  - AWS CodePipeline
  - SSO
  - Stripe (subscriptions)
links:
  - label: Overview
    url:
  - label: Repository
    url:
---
Led the engineering team and platform work at TenfoldAI, applying **AWS best practices** across infrastructure, delivery, and secure access for internal systems.

### Architecture & design leadership

Reviewed **team architectures** and **design documents**, and guided **technical decision-making**—trade-offs on reliability, cost, security, and delivery speed were documented so the team had a clear, shared rationale before build-out.

### Data pipeline & platform

Designed and shipped a scalable **document → Markdown** conversion service for heavy batch workloads. The architecture used CDK-managed infrastructure with S3 notifications, SNS/SQS, and **GPU-backed ECS** where CPU-only conversion was not enough.

### Billing & subscriptions (Stripe)

Integrated **Stripe** for **subscription-based payments**, wired through an **event-driven** architecture on AWS (webhooks, queues, and decoupled workers). The design prioritized **scalability**, **high availability**, and **operational resilience**—billing state changes propagate asynchronously so core services stay available under load and partial failures are isolated rather than cascading.

### CI/CD modernization

Migrated a **legacy deployment workflow** to a modern **AWS CodePipeline**–based CI/CD setup—improving repeatability, auditability, and release velocity for the team.

### Identity & internal access

Introduced **SSO** for the **internal website** and tooling, replacing long-lived credentials that had to be **refreshed on a fixed schedule** just to regain access. Engineers and operators sign in through SSO instead of managing rotating permanent keys.
