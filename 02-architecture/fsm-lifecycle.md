# FSM Lifecycle

## Purpose

The finite state machine (FSM) defines the legal lifecycle of an AI asset inside a regulated banking environment.

Its purpose is to prevent uncontrolled deployment and to ensure every transition is:

- explicit
- traceable
- policy-checked
- auditable

## Why an FSM Matters

Without a lifecycle model, AI systems become unpredictable:

- models can be promoted too early
- rollback paths are unclear
- approvals are informal
- monitoring is disconnected from governance

An FSM solves this by making the system behave according to defined state transitions.

## Core States

### 1. Drafted
The model or AI asset has been created but is not yet trusted.

Typical activities:
- initial registration
- metadata capture
- ownership assignment

### 2. Validated
The asset has passed technical validation.

Typical checks:
- schema checks
- test execution
- performance threshold checks
- packaging checks

### 3. Approved
The asset has passed required human or policy approval.

Typical approvals:
- business owner
- model risk
- compliance
- architecture governance

### 4. Deployed
The asset has been promoted to the serving environment.

Typical activities:
- endpoint deployment
- traffic configuration
- version registration
- release event logging

### 5. Monitored
The asset is live and under continuous observation.

Typical signals:
- latency
- failure rate
- drift
- business KPI deviation
- policy exceptions

### 6. Rolled Back
The active version has been withdrawn and replaced by a safe prior version.

Typical triggers:
- incident
- degraded performance
- incorrect outputs
- compliance intervention

### 7. Retired
The asset is no longer active and is removed from operational use.

Typical reasons:
- replacement by newer version
- policy sunset
- model obsolescence
- business discontinuation

## Example Transition Logic

Allowed transitions may include:

- Drafted → Validated
- Validated → Approved
- Approved → Deployed
- Deployed → Monitored
- Monitored → Rolled Back
- Monitored → Retired
- Rolled Back → Monitored
- Approved → Retired

Disallowed examples:
- Drafted → Deployed
- Drafted → Monitored
- Validated → Deployed without approval

## Governance Rules

Each transition should enforce rules such as:

- required metadata present
- validation evidence attached
- approval recorded
- deployment target allowed
- rollback candidate exists
- audit entry written

## Auditability

Every state change should record:

- asset identifier
- version
- previous state
- new state
- timestamp
- triggering event
- decision source
- approver or policy identity
- correlation / trace id
- status and error details if failed

## Banking Relevance

In a bank, lifecycle ambiguity is risk.

The FSM creates:
- controlled promotion
- explainable operations
- safer rollback
- evidence for governance
- confidence that AI behaves like production infrastructure

## Key Message

The FSM is not just a technical mechanism.

It is the operational contract that makes AI governable.
