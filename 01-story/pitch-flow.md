# Pitch Flow

## 1. Opening (10–15 seconds)

Most AI initiatives in banking don’t fail because of poor models.

They fail because the systems around them are not designed for production, governance, or control.

---

## 2. Problem (30–40 seconds)

In a regulated bank environment:

- models are deployed without clear lifecycle control  
- approvals are manual and inconsistent  
- audit trails are incomplete  
- monitoring is disconnected from decision-making  

This creates operational risk and makes AI difficult to trust.

---

## 3. Insight (20–30 seconds)

The real problem is not AI.

The problem is the absence of a **controlled operating model** for AI.

Banks don’t need more models.

They need AI systems that behave like production infrastructure.

---

## 4. Solution (60 seconds)

We propose a **Control-Plane Driven AI Architecture**.

At the core:

- all actions are event-driven  
- lifecycle is governed by a finite state machine  
- every decision is recorded in an audit store  
- control and serving are separated  

The control plane decides *what should happen*.  
The serving plane executes *the model*.

---

## 5. How It Works (60–90 seconds)

- Business or system events trigger actions  
- Events are ingested asynchronously  
- The control plane evaluates the current state  
- FSM rules determine allowed transitions  
- Approved actions are executed (deploy, rollback, monitor)  
- Every step is logged for audit  

Monitoring feeds back into the system:
- drift  
- failures  
- performance issues  

These trigger new control-plane decisions.

---

## 6. Value (30–40 seconds)

This enables:

- governance by design  
- full traceability of decisions  
- safe and repeatable deployments  
- controlled rollback  
- visibility for risk and compliance  

AI becomes predictable and controllable.

---

## 7. Closing (10–15 seconds)

We are not building more models.

We are making AI safe to run in a bank.

---

## Optional One-Liner

Banks don’t need more models — they need controlled AI systems, and that’s what we build.
