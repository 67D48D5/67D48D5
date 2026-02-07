<!-- markdownlint-disable MD033 -->

# Performance

> Performance is not just speed — it's **predictability**, **cost control**, and **operational stability**.

## What I Optimize For

- **Latency stability**
  - P95/P99 matters more than best-case speed
- **Throughput with guardrails**
  - Concurrency control and backpressure-aware design
- **Cost-aware scaling**
  - Spending should scale with value (serverless-first mindset)
- **Retry safety**
  - Performance includes failure behavior

## Common Tools

### Caching

- **Micro-cache** for high-frequency reads
- CDN-first distribution when applicable

### Data Pipeline Tuning

- Reduce redundant writes
- Use batching when it improves cost/latency
- Prefer read-optimized views (snapshots)

### Serverless-specific

- Cold-start minimization
- Keep dependencies tight
- Minimize init-time work, maximize handler efficiency

## Examples

- **uRing**
  - Snapshot-based reads for fast serving
  - Retry-safe crawling via idempotency
- **wBus**
  - Micro-cache stabilizes read latency under load
  - Linear interpolation improves perceived UX smoothness

---

<!-- Spacer -->
<br>

<!-- Navigation -->
⬅ Back to [README](../README.md)
