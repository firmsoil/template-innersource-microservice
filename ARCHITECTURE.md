# 🧩 Architecture Overview

## Domain Context
**Bounded Context:** Deployment Automation  
**Core Entities:** Pipeline, Artifact, DeploymentTarget  
**Integration Points:** CI Orchestrator, Artifact Store, Notification Bus

---

## High-Level Design
```
[ Developer ] --> [ CI Service ] --> [ Artifact Service ]
                              ↘︎
                              [ Deployment Automation Service (this) ]
```

- Exposes REST and event-driven APIs.
- Handles deployment requests, version tracking, and rollback operations.

---

## DDD Layers
| Layer | Responsibility | Example |
|--------|----------------|---------|
| **Domain** | Business logic | DeploymentAggregate |
| **Application** | Coordination | DeploymentService |
| **Infrastructure** | Integrations | ArtifactRepository |

---

## Observability
- Health endpoints
- Prometheus metrics
- OpenTelemetry tracing
- Contract tests for APIs
