<!-- markdownlint-disable MD033 MD041 -->

# Architecture

> I design systems like products: **clear boundaries**, **predictable behavior**, **easy operations**.

## Principles

- **Stateless by default**
  - Prefer stateless execution models (especially serverless)
- **Append-only > in-place mutation**
  - Makes retries safe and history auditable
- **Idempotency-first**
  - If a function can run twice, it must still be correct
- **Read-optimized views**
  - Keep write paths simple; build fast read models (snapshots / indexes)
- **Explicit contracts**
  - Schemas, versioning, and clear module boundaries

## Patterns I Use

### Atomic switching (Pointer Rotation)

- Update a “current pointer” instead of rewriting everything
- Enables safe deployment of new snapshots without partial states

### Snapshot-first storage

- Writes accumulate → snapshots provide fast reads
- Works well with S3 + CDN style distribution

### Cache as a shield (not a hack)

- Micro-cache hot paths
- Stabilize latency & reduce backend pressure

### Operational simplicity

- Prefer boring + obvious operations
- Minimize moving parts unless the complexity buys reliability

## Where It Shows Up

- **uRing:** snapshot-based pipeline + atomic pointer switching + idempotent crawler
- **wBus:** micro-caching + smooth interpolation + predictable API reads
- **Everest:** constrained infra ops + automation-first thinking

---

<!-- Spacer -->
<br>

<!-- Navigation -->
⬅ Back to [README](../README.md)
