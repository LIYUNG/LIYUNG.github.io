---
title: TenfoldAI — document pipeline & infrastructure
summary: Large-scale document-to-Markdown service on AWS (CDK, S3, SNS, SQS, GPU ECS); Stripe-backed event billing.
period: March 2025 — November 2025
order: 2
tech:
  - AWS CDK
  - Amazon S3
  - SNS / SQS
  - Amazon ECS (GPU)
  - Stripe
links:
  - label: Overview
    url:
  - label: Repository
    url:
---
Designed and shipped a scalable **document → Markdown** conversion pipeline aimed at heavy batch workloads on AWS.

The design combined CDK-managed infrastructure with object storage notifications, queued workers, and **GPU-backed ECS** tasks where CPU-only conversion wasn’t viable. Stripe was integrated alongside an **event-driven** billing and usage path so downstream services could remain loosely coupled.
