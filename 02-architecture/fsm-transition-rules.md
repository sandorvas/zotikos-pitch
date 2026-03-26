# FSM Transition Rules

## Example Rule Set

### Drafted → Validated
Allowed when:
- required metadata exists
- package integrity check passed
- unit/integration validation passed

### Validated → Approved
Allowed when:
- validation evidence attached
- model card or equivalent documentation present
- review package submitted

### Approved → Deployed
Allowed when:
- named approver recorded
- deployment target authorized
- rollback target known
- release window allowed

### Deployed → Monitored
Allowed when:
- endpoint health is green
- smoke tests passed
- initial runtime telemetry available

### Monitored → RolledBack
Allowed when:
- drift threshold breached
- severe incident detected
- policy override issued
- performance degradation exceeds tolerance

### Monitored → Retired
Allowed when:
- replacement version exists
- business owner confirms retirement
- operational dependencies removed

## Design Principle

A transition should never be based on assumption.

It should be based on evidence, policy, or observed runtime signals.
