# Vision and System Boundaries

## Vision

Tyler Prime is a local-first personal AI appliance intended to grow from a desktop assistant into a personal operational world model.

A conventional assistant answers a prompt. Tyler Prime is intended to understand a goal, assemble the relevant evidence, route bounded work, request approval when required, observe execution, and retain a durable account of the outcome.

The long-term goal is not an autonomous personality with unlimited access. It is a governed system that helps one person understand and operate across software, infrastructure, data, projects, and eventually richer real-world processes.

## What Tyler Prime is

- A desktop control plane for multiple local services
- A contract and routing layer between intent and execution
- A durable store of objects, relations, events, and receipts
- A model-routing system spanning local and remote capability
- An integration surface for automation and bounded agents
- An engineering experiment in personal operational intelligence

## What Tyler Prime is not

- A single large language model
- A chatbot wrapper
- One enormous Docker Compose file presented as an architecture
- An unrestricted autonomous agent
- A replacement for source control, databases, or observability systems
- A public self-hosting distribution in its current form

## Boundary model

Tyler Prime owns coordination, identity, task contracts, approvals, routing, and receipts. Specialized services retain specialized responsibilities:

| System | Owns | Does not own |
|---|---|---|
| OpenClaw | Conversation and person-facing interaction | Unbounded execution authority |
| Tyler Prime Kernel | Goals, contracts, permissions, routing, approvals | Every domain implementation |
| World Store | Durable operational objects and evidence links | Large binary asset storage |
| n8n | Schedules, webhooks, alerts, durable workflow edges | System identity or core reasoning |
| OpenHands | Bounded repository work | Global control of Tyler Prime |
| Model router | Capability and machine-aware model selection | Business authority |
| Grafana/Prometheus | Operational visibility | Primary system data |

## North-star behavior

A mature Tyler Prime should be able to answer:

- What is Tyler trying to accomplish?
- What facts and prior decisions support this task?
- Which system is allowed and able to perform the work?
- What requires approval?
- What happened during execution?
- What evidence proves the outcome?
- What should become durable state for future work?
