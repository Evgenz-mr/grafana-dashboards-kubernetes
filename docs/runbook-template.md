# Runbook template

## Alert
Name and severity.

## Impact
User/system impact and affected scope.

## Signals
Dashboards, metrics, logs and events to inspect.

## Triage
1. Confirm the alert is real.
2. Identify affected namespace/workload/node.
3. Correlate with deployments/configuration changes.
4. Check dependencies and control-plane health.

## Mitigation
Prefer reversible actions. Document rollback conditions before making high-impact changes.

## Verification
Confirm service health, alert recovery and absence of secondary symptoms.

## Follow-up
Capture root cause, permanent corrective action and monitoring gaps.
