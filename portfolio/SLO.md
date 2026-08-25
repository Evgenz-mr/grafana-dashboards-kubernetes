# Kubernetes observability SLO examples

This portfolio extension connects dashboards and alerts to explicit service objectives instead of treating monitoring as a collection of charts.

## Example objectives

- API availability: 99.9% successful requests over 30 days.
- API latency: 95% of successful requests below 500 ms.
- Platform saturation: avoid sustained CPU throttling or memory pressure that impacts user-facing SLOs.

## Investigation model

```text
SLO / alert
   |
   v
Grafana overview
   |
   +-> workload metrics
   +-> Kubernetes resource pressure
   +-> deployment/change context
   |
   v
runbook -> mitigation -> post-incident follow-up
```

## Alert quality

Alerts should describe user impact or an actionable platform risk. Dashboard thresholds alone are not a paging strategy. Prefer multi-window burn-rate alerts for mature SLO implementations and keep warning signals separate from urgent pages.
