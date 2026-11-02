# CURRENT_STATE

Status: TRACKB_REFERENCE_EXECUTION_FAILED

## Repository identity
- Repository: `lcm1226/safeopener-kvm-probe`
- Visibility: public
- Canonical branch: `main`
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58`
- Adoption-base tree: `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`
- ROS adoption merge: PR #1, `c4260d3e5048238e8b52e1fb91a5aa7d234bffbc`
- Track B execution-surface merge: PR #3, `11c5a4aed14bcf26651257440fa1c0e564c0d2e4`
- One-shot campaign merge: PR #5, `4781b7c64bda21a6f44dcf6ecfb3bda766359383`
- One-shot bootstrap cleanup merge: PR #6, `c56b1ac3ecbd18046f2dd4b2fa2868f2d41f4ea1`

## Role
This repository is a public supporting probe/execution surface for Safe Opener. Canonical Safe Opener semantics remain in `lcm1226/safe-opener`.

## Existing live surfaces
- `.github/workflows/` on canonical `main` contains the pre-existing KVM probe, external-control/external-flow, encrypted Track B host-local, diagnostic workflows, and the Track B reference observer/source/controller workflows merged by PR #3.
- The temporary one-shot bootstrap workflow used for campaign `20261102587109` was removed by PR #6 after the authorized attempt was consumed.
- `exchange/` and the `runtime-state` branch contain supporting runtime evidence/history and are not semantic authority.
- First-time ROS adoption is complete on canonical `main`.

## Consumed Track B reference execution
- External KVM_REFERENCE executions consumed: 1/1. No second KVM_REFERENCE execution is authorized by the current task.
- Exact execution binding: campaign `20261102587109`; Safe Opener proof HEAD `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`; local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`; probe execution HEAD `4781b7c64bda21a6f44dcf6ecfb3bda766359383`; bootstrap run `41331112612`; observer run `41331122205`; source run `41331134357`.
- The encrypted relay exact-binding checks passed and the source published a host-local base observation. That base observation records successful Firecracker boot/snapshot/restore, fresh-session separation, bounded packing, controlled stream readiness, and attempted external R4/R5 release-gate observations. These supporting observations are not canonical proof promotion.
- The source then failed before `BLAST_ARMED` with `FATAL:blast_duration_invalid`: the public source workflow requested `SO_TRACKB_BLAST_DURATION_SECONDS=1500`, while the exact canonical campaign permits at most `300` seconds.
- Because the blast flow never armed, the observer received no qualifying pulse sequence and ended without an established-flow record; the controller was never dispatched. Host-external cut, host quarantine/replacement, blast-radius completion, and worker-rotation evidence therefore remain unproven for this consumed attempt.
- Canonical reducer output for the partial base observation remains `UNVERIFIED`; do not hand-promote any `TB-*`, R4/R5 composite row, or ADR-010 state from the partial observation.

## Remediation state
- Canonical probe source workflow now resolves the `bore.pub` observer hostname to a global IPv4 candidate, requires a successful raw-TCP preflight to the exact observer port, passes only that verified IPv4 into canonical `SO_TRACKB_BLAST_OBSERVER_IP`, and constrains blast duration to `300` seconds.
- The original `bore.pub` hostname remains preserved for provenance/controller binding, while the selected observer IPv4 is recorded separately in the source armed-state payload.
- This remediation has not been live-dispatched. Its runtime behavior remains `UNVERIFIED`; remediation does not restore or create authorization for a second KVM_REFERENCE run.

## Safety / unresolved
- No paid provider or payment method is selected or authorized; incremental provider cost remains $0.
- No canonical Safe Opener proof acceptance or ADR promotion is authorized here.
- Historical runs and exchange/runtime-state material must not be reused as a new current execution.
- Any further KVM_REFERENCE execution, proof promotion, ADR acceptance, provider/payment mutation, branch deletion, or other new external mutation requires separate fresh authorization.
