# PROGRESS

## 2026-11-01 — first-time ROS adoption
- Adoption basis: no prior `.sot/bootstrap.yaml` and no `sot/bootstrap` ref existed in this public probe repository.
- Migration evidence: canonical `lcm1226/safe-opener` bootstrap at `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`.
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58` / tree `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`.
- Scope: repository operating metadata only; no workflow semantics changed by this adoption commit.
- External KVM_REFERENCE executions consumed by this adoption step: 0.
- Paid provider/payment changes: none.

## 2026-11-01 — Track B KVM_REFERENCE workflow preparation
- Prepared two local workflows on the ROS adoption branch: raw-TCP observer and exact-bound KVM source.
- Both workflow YAML files passed the SentinelX YAML validator.
- Pinned observer dependency: `bore` v0.6.0, x86_64 Linux musl SHA-256 `e484d1e3acba77169b773f31a5bfb34192d4b660f44a094a658a2522cd2270f7`.
- Canonical proof binding target: Safe Opener `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`; fresh local attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`.
- Automated controller workflow was not added because the available mutation surface rejected that controller implementation; no bypass was attempted.
- Remaining blocker before execution: trustworthy provider cancel-request timestamp sufficient for `revokeToCutMs` and rotation measurement.
- External KVM_REFERENCE execution count remains 0/1; cost remains $0.
