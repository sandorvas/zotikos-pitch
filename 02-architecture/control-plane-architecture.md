# Control-Plane Driven AI Architecture

## Design Goal

Create an AI operating model suitable for a regulated bank, where deployment, inference, monitoring, and governance are treated as parts of one controlled system.

## Core Principle

Separate:

- **Control Plane** → orchestration, policy, lifecycle, approval, audit
- **Serving Plane** → model hosting, inference, runtime execution

This separation reduces operational risk and improves traceability.

## Main Components

### 1. Business / Event Sources
These are the triggers that start the process:
- new model version
- data quality event
- scheduled retraining trigger
- approval decision
- risk/compliance intervention

### 2. Event Ingestion Layer
Events are received through a messaging layer so the system is:
- asynchronous
- decoupled
- resilient

### 3. Control Plane
The control plane is the brain of the system.

Responsibilities:
- evaluate incoming events
- determine current lifecycle state
- enforce transition rules
- trigger the next action
- prevent invalid transitions
- record all decisions

### 4. FSM Lifecycle Engine
A finite state machine governs legal movement between states such as:
- drafted
- validated
- approved
- deployed
- monitored
- rolled back
- retired

This ensures the system behaves predictably.

### 5. Audit / Decision Store
Every important action is written to an audit store.

Examples:
- who approved what
- which model version was deployed
- when rollback happened
- what event triggered the transition

### 6. Serving Plane
This is where the model runs in production.

Responsibilities:
- host model endpoints
- serve predictions
- expose health/readiness
- report runtime metrics

### 7. Monitoring and Feedback
The system continuously observes:
- serving health
- prediction failures
- drift indicators
- pipeline failures
- operational anomalies

This can trigger new control-plane events.

## Why This Matters in Banking

A bank does not only need predictions.

It needs:
- controlled deployment
- traceable decisions
- operational resilience
- clear rollback paths
- evidence for governance and audit

## Key Value

This architecture turns AI from an isolated experiment into a governed production capability.
