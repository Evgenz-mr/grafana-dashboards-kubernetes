# Kubernetes incident scenarios

## 1. Pod CrashLoopBackOff

**Signal:** restart rate increases and pods are unavailable.

**Investigate:** workload dashboard, pod events, previous container logs, probe failures, OOMKilled state and recent deployment changes.

**Mitigate:** rollback the bad release, fix configuration/secrets, adjust probes only when evidence shows they are incorrect, or correct memory limits when OOM is confirmed.

## 2. CPU saturation and HPA pressure

**Signal:** sustained CPU utilization near configured limits, latency growth and HPA scaling.

**Investigate:** pod CPU usage vs requests/limits, node saturation, throttling and replica count.

**Mitigate:** remove pathological load, scale replicas, tune requests/limits from measured usage and verify downstream dependencies are not the actual bottleneck.

## 3. Kubernetes API server latency

**Signal:** API request latency/error rate increases.

**Investigate:** API server dashboard, etcd latency, control-plane CPU/memory, admission webhook latency and request volume.

**Mitigate:** isolate noisy clients/controllers, restore control-plane capacity and fix slow/unavailable admission webhooks.

## 4. Node filesystem pressure

**Signal:** node reports DiskPressure or filesystem utilization crosses the warning threshold.

**Investigate:** node dashboard, image/container storage, logs, ephemeral volumes and inode usage.

**Mitigate:** clean unused images safely, fix runaway logs, increase capacity when justified and enforce retention/ephemeral-storage limits.

## 5. Certificate expiry

**Signal:** certificate expiry alert enters warning window.

**Investigate:** identify certificate owner, renewal controller/process, remaining lifetime and dependent ingress/service.

**Mitigate:** renew through the owning automation, validate trust chain, then verify clients before the old certificate expires.
