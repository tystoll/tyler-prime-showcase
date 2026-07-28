# Architecture

## Control plane and service plane

Tyler Prime separates the user-facing control plane from the services that perform specialized work.

The Electron desktop provides one operational surface. It can host or link views for conversation, workflows, dashboards, data tools, and service controls without pretending those systems are all the same application.

The kernel sits behind that surface and is responsible for translating goals into controlled work.

## Main layers

### 1. Interaction

OpenClaw provides the person-facing conversational layer. Its job is to communicate with Tyler, maintain the appropriate active context, and send structured intent into the kernel.

### 2. Governance and routing

The Tyler Prime Kernel defines:

- goals and task contracts;
- scope and completion criteria;
- permissions and approval gates;
- model and tool routing;
- fallback and rollback expectations;
- execution receipts.

This layer prevents the conversational interface from becoming the execution authority.

### 3. Execution

Specialized systems perform bounded work:

- n8n handles schedules, webhooks, supervision, and outside-service workflows;
- OpenHands handles repository-scoped software-engineering tasks;
- MCP-compatible tools expose narrowly defined capabilities;
- domain systems such as Market Lab own their own collectors and databases.

### 4. Durable world data

The World Store records structured objects, relations, events, receipts, and routing information. Historical evidence should remain immutable or versioned; active context can be rebuilt from that evidence.

Large generated assets belong in appropriate object or file storage. The World Store records identity, relationships, versions, provenance, and locations rather than becoming a binary warehouse.

### 5. Models

Local and remote models are selected through machine and capability profiles. Routing can account for privacy, latency, cost, context requirements, and available hardware.

### 6. Observability

Prometheus and Grafana expose infrastructure and service health. Model and tool tracing adds visibility into requests, latency, failures, routing, and execution outcomes.

## Why adapters matter

OpenClaw, OpenHands, n8n, Ollama, and individual MCP servers may change. Tyler Prime therefore treats them as replaceable adapters around stable internal contracts.

The durable concepts are:

- goal;
- object;
- relation;
- event;
- task contract;
- permission;
- approval;
- receipt;
- evidence;
- model route.

That keeps the architecture centered on operational behavior rather than a temporary list of products.
