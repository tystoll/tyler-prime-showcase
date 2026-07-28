# Homelab Integration

## Direction

Tyler Prime is expanding from a personal AI appliance into the control plane for the homelab that supplies its compute, storage, automation, data, and observability.

The existing server repository contains real operational work: machine profiles, service inventories, monitoring, backup procedures, Docker deployments, administrative scripts, and build history. That material belongs inside the private Tyler Prime system because it describes the physical and software environment Tyler Prime operates across.

The public showcase will document the engineering model and verified outcomes. It will not publish a deployable copy of the homelab or a map of its attack surface.

## The ownership boundary

Tyler Prime should understand and coordinate the homelab without replacing the systems that already perform specialized work.

| Layer | Responsibility |
|---|---|
| Tyler Prime Desktop | One surface for machine, service, storage, workflow, and data views |
| Tyler Prime Kernel | Goals, permissions, approvals, routing, and task contracts |
| World Store | Machine, service, dependency, event, evidence, and receipt records |
| Server operations domain | Configuration, runbooks, health checks, backup operations, and deployment procedures |
| Prometheus/Grafana | Metrics collection, dashboards, and alert visibility |
| n8n | Schedules, notifications, supervision, and outside-service workflow edges |
| Docker hosts | Runtime for containerized services |
| Domain systems | Own their collectors, databases, models, and business-specific behavior |

## Homelab world model

The World Store can represent the homelab through stable objects and relationships rather than hard-coded dashboard pages.

### Objects

- machines and machine profiles;
- GPUs and other compute capabilities;
- services and containers;
- repositories and deployments;
- storage pools, volumes, and backup targets;
- databases and data collectors;
- dashboards, alerts, and runbooks;
- network zones and logical connections;
- maintenance tasks and incidents.

### Relationships

- service **runs on** machine;
- service **depends on** database;
- collector **writes to** data store;
- dashboard **observes** service;
- backup job **protects** volume;
- machine **provides** model capability;
- repository **deploys** service;
- incident **affects** object;
- receipt **proves** action.

Operational addresses, credentials, and raw configuration remain in private configuration or secret stores. The World Store records identity, relationships, state, provenance, and evidence references.

## Server-repository migration

The server repository should not simply be dropped into the Electron application. It becomes a private operations domain with a deliberate boundary.

### Phase 1 — Audit

- Inventory files, scripts, documentation, Compose projects, machine profiles, and secrets.
- Separate current truth from historical notes and abandoned experiments.
- Identify anything that must never enter source control.
- Preserve useful Git history before moving content.

### Phase 2 — Establish ownership

- Tyler Prime owns goals, objects, permissions, routing, approvals, and receipts.
- The server-operations domain owns runbooks, host checks, backup procedures, and deployment definitions.
- Monitoring systems own metric collection and visualization.
- Individual services retain their own application data and configuration boundaries.

### Phase 3 — Move the private source

- Place the audited operations domain under the canonical private Tyler Prime source tree.
- Preserve history through an appropriate Git migration instead of copying an unexplained snapshot.
- Move durable configuration, logs, backups, and runtime data outside the packaged desktop application.
- Replace embedded machine facts with machine-profile and environment configuration.

### Phase 4 — Register the homelab

- Seed machines, services, storage, databases, repositories, and dependencies as World Store objects.
- Link health checks and dashboards to the objects they observe.
- Record changes and maintenance work as events and receipts.
- Expose read-only status in the Tyler Prime System surface first.

### Phase 5 — Add governed operations

- Turn proven runbooks into bounded task contracts.
- Require approval for restarts, configuration changes, deployments, network changes, and destructive storage actions.
- Capture before-state, action, verification, and rollback evidence.
- Add automation only after the corresponding manual workflow is understood and observable.

## First usable milestone

The first homelab milestone is intentionally read-only:

1. Tyler Prime lists known machines and services.
2. Each object shows current health, last observation, dependencies, and evidence source.
3. Existing Grafana views remain the detailed metric interface.
4. Tyler Prime can explain where a service runs and what it depends on.
5. No infrastructure mutation is available from the UI.

That milestone proves the inventory and information model before adding operational authority.

## Public evidence

Safe public demonstrations can include:

- sanitized topology and responsibility diagrams;
- the System view with identifiers and addresses removed;
- fictional machine/service records;
- service-health and dependency examples;
- a read-only incident investigation;
- a receipt showing approval, execution, and verification with operational details redacted.

The private repository remains the source of operational truth. This showcase remains the public record of the architecture, engineering decisions, and validated results.
