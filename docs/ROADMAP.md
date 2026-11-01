# ROADMAP

1. Complete first-time ROS adoption on a dedicated branch without changing probe semantics.
2. Reconcile live probe workflows against canonical Safe Opener Track B requirements.
3. Add the minimum exact-binding workflow/controller changes needed for zero-cost KVM_REFERENCE execution.
4. Preflight off-host raw-TCP observer availability and established-flow visibility before dispatching the KVM source worker.
5. Execute exactly one externally authorized KVM_REFERENCE run only if every preflight gate is green.
6. Return evidence to the canonical Safe Opener repository for separate review. Do not promote ADR/proof acceptance in this repository.

## Stop conditions
Stop on moved refs, bootstrap/authority conflict, unverifiable observer topology, non-zero incremental cost, credential/payment requirement, scope expansion, or loss of exact commit/run binding.
