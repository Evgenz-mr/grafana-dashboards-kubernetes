# Kubernetes Observability Portfolio Extension

This repository contains a Kubernetes Grafana dashboard collection and GitOps/Kustomize integration. The portfolio extension here focuses on operational use: alert rules, incident scenarios and runbooks rather than claiming authorship of the upstream dashboard JSON collection.

## Operational stack

```text
Kubernetes workloads
   |-- metrics --> Prometheus / VictoriaMetrics
   |-- events  --> alert rules
   `-- dashboards --> Grafana
                         |
                         v
                    investigation
                         |
                         v
                       runbook
```

## Senior-level focus

- dashboards as code
- GitOps delivery through Argo CD/Kustomize
- actionable alert definitions
- symptom -> dashboard -> query -> mitigation workflow
- capacity and saturation analysis
- Kubernetes workload and control-plane troubleshooting

See `docs/incident-scenarios.md` and `alerts/kubernetes-platform.rules.yml`.
