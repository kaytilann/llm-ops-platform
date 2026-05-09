# Architecture

```mermaid
flowchart LR
  Apps[AI Applications] --> Gateway[App Gateway]
  Gateway --> Registry[Prompt Registry]
  Gateway --> Context[Context Builder]
  Context --> Vector[Vector Store]
  Registry --> Policy[Policy Engine]
  Context --> Policy
  Policy --> Router[Routing Engine]
  Router --> ModelGateway[Model Gateway]
  ModelGateway --> Providers[Model Providers]
  Providers --> Eval[Online Evaluation]
  Eval --> Observability[Observability + Cost Analytics]
  Policy --> Audit[Audit Log]
  Observability --> Dashboard[SignalForge UI]
  Audit --> Dashboard
```

## Core components
- App Gateway
- Prompt Registry
- Context Builder
- Policy Engine
- Routing Engine
- Model Gateway
- Eval Harness
- Observability Layer
- Audit Log

## Guardrails
- PII redaction before model calls
- Prompt injection checks
- Sensitive topic detection
- Human review for high-risk workflows
- Model promotion gates
- Canary releases for model changes
- Rollback support
