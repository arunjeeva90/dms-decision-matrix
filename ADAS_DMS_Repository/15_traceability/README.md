# 15 — Traceability

## Traceability files

- [`traceability.csv`](traceability.csv): stakeholder, regulation, platform, safety and verification links.
- [`scenario_traceability.csv`](scenario_traceability.csv): all live scenarios `DMS-001` through `DMS-029` linked to normalized system requirements and verification cases.
- [`../03_system_requirements/scenario_requirement_mapping.csv`](../03_system_requirements/scenario_requirement_mapping.csv): engineering scenario disposition and primary requirement ownership.

## Required link types

- `satisfies`
- `derives`
- `allocated_to`
- `mitigates`
- `verified_by`
- `constrained_by`
- `conflicts_with`
- `supersedes`

## Bidirectional completeness rule

A system requirement is complete only when it has:

1. an approved source or parent;
2. architecture/subsystem allocation;
3. safety/SOTIF/regulatory links where applicable;
4. at least one objective verification method;
5. linked positive, negative, boundary, degraded and recovery coverage where relevant;
6. version and approval status.

Scenario coverage is not considered complete merely because a scenario name appears in a document. It must trace to atomic requirements and executable verification cases.
