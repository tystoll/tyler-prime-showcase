# Status and Roadmap

Status labels in this repository are intentionally conservative.

## Implemented foundations

- Electron-based Tyler Prime desktop and shared React interface
- Local OpenClaw workspace and person-facing configuration
- SQLite-based World Store foundations
- n8n service for durable automation edges
- Local model operation through Ollama
- Prometheus and Grafana infrastructure monitoring
- Separate Market Lab data system with TimescaleDB and external market adapters

## Active integration

- Consolidating the existing server-operations repository into Tyler Prime's private source tree
- Modeling the homelab as machines, services, storage, networks, workloads, and evidence in the World Store
- Extending the System surface from local runtime health into multi-machine homelab visibility
- Embedding multiple service views behind one desktop control plane
- Clear contracts between OpenClaw, the kernel, and execution services
- OpenHands as a bounded software-engineering worker
- Machine-profile-aware local and remote model routing
- Unified receipts and operational evidence
- Domain boundaries between Tyler Prime and Market Lab

## Planned

- Controlled homelab actions with explicit scope, approval, verification, and receipts
- Backup, storage, service-dependency, and machine-capability views
- Stronger approval and permission enforcement
- Context retrieval across code, sessions, and durable memory
- Memory-librarian behavior derived from immutable evidence
- Model and tool tracing
- Evaluation with repeatable task suites
- Versioned asset/object relationships for generative media workflows
- A fuller operational world model spanning projects, infrastructure, and data

## Publication roadmap

The public showcase will add material only after it can be sanitized and verified:

1. Architecture diagrams
2. Desktop screenshots with private data removed
3. Task-contract and receipt examples
4. Short end-to-end workflow demonstrations
5. Design-decision records
6. Build journal entries describing failures, changes, and validation

## Completion standard for published capabilities

A capability moves to **implemented** only when it has:

- a working path through the intended system boundary;
- observable success and failure behavior;
- restart or recovery expectations;
- evidence or tests appropriate to the risk;
- documentation that matches the running system.
