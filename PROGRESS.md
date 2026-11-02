# PROGRESS

## 2026-11-01 — first-time ROS adoption
- Adoption basis: no prior `.sot/bootstrap.yaml` and no `sot/bootstrap` ref existed in this public probe repository.
- Migration evidence: canonical `lcm1226/safe-opener` bootstrap at `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`.
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58` / tree `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`.
- Scope: repository operating metadata only; no workflow semantics changed by this adoption commit.
- External KVM_REFERENCE executions consumed by this adoption step: 0.
- Paid provider/payment changes: none.

## 2026-11-01 — ROS adoption merged
- PR #1 merged to canonical `main` as `c4260d3e5048238e8b52e1fb91a5aa7d234bffbc`.
- Canonical merge tree: `5d6e46ce8bff9f1c685dcb70cec48f2ca3030c4a`.
- First-time ROS adoption is complete; repository bootstrap discovery now resolves from canonical `main` with `sot/bootstrap` retained as discovery-only fallback.
- External KVM_REFERENCE execution count remains 0/1; incremental provider cost remains $0.

## 2026-11-02 — Track B reference execution surface merged
- PR #3 merged to canonical `main` as `11c5a4aed14bcf26651257440fa1c0e564c0d2e4` / tree `d2958b7f04f8eb82e251611bc2f8c1a89ad1b8c7`.
- Canonical `main` now contains `trackb-reference-observer.yml`, `trackb-reference-source.yml`, and `trackb-reference-controller.yml`.
- The controller resolves the previous cancel-request timing design blocker at the implementation level by recording the pre-force-cancel controller timestamp, requiring provider `202`, consuming the independent observer cut timestamp, verifying source terminal cancellation, and measuring replacement timing.
- The new Track B workflows have not yet been live-dispatched; their runtime behavior remains `UNVERIFIED` until the authorized reference execution.
- PR #3 merge triggered the pre-existing `kvm-capability-probe` push workflow at run `41325605068`; it completed successfully. This capability probe is not the Track B KVM_REFERENCE campaign and does not consume the one reference execution.
- External KVM_REFERENCE execution count remains 0/1; incremental provider cost remains $0; no paid provider/payment method change occurred.
- Next gate: rehydrate the execution-time Safe Opener canonical HEAD, produce/verify fresh same-commit attestation, exact-bind the probe `main` HEAD and run IDs, complete zero-cost off-host preflight, then obtain current authorization before the workflow-dispatch boundary.

## 2026-11-02 — authorized Track B KVM_REFERENCE consumed; blast pre-arm failed
- PR #5 merged the temporary one-shot bootstrap to canonical `main` as `4781b7c64bda21a6f44dcf6ecfb3bda766359383`, which automatically started the single authorized campaign `20261102587109`.
- Exact binding: Safe Opener `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`; fresh local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`; bootstrap run `41331112612`; observer run `41331122205`; source run `41331134357`.
- The source accepted and decrypted the exact-bound relay, passed its relay/hash/attestation checks, ran the real KVM base campaign, and published `trackb-ref-source-base-20261102587109.json` to `runtime-state`.
- The base observation records successful Firecracker boot/snapshot/restore, fresh-session separation, bounded packing, controlled stream readiness, and attempted real-worker egress/lifecycle release-gate observations. No canonical `TB-*`, R4/R5 composite row, or ADR-010 state is promoted from this partial evidence.
- The source then failed before `BLAST_ARMED` with `FATAL:blast_duration_invalid`: public workflow input `SO_TRACKB_BLAST_DURATION_SECONDS=1500` violated the exact canonical campaign hard bound `<=300` seconds. The observer therefore received no qualifying pulse sequence and ended without an established-flow record; the controller was never dispatched.
- External KVM_REFERENCE execution count is now 1/1 consumed. Incremental provider cost remains $0. No second KVM_REFERENCE execution is authorized by this convergence.
- PR #6 removed only the temporary one-shot bootstrap and merged as `c56b1ac3ecbd18046f2dd4b2fa2868f2d41f4ea1`; the merge-triggered pre-existing KVM capability probe `41333834817` succeeded and does not constitute another Track B campaign.
- Remediation updates only the canonical probe source workflow plus `CURRENT_STATE`/`PROGRESS`: resolve `bore.pub` to a global IPv4 candidate, require successful raw-TCP preflight to the exact observer port, pass the verified IPv4 to canonical blast-hold, constrain blast duration to `300`, and preserve hostname + selected IP provenance. The remediation is static-only and runtime `UNVERIFIED`; no workflow dispatch occurs in this step.
- Canonical reducer output for the partial base observation remains `UNVERIFIED`; do not hand-assemble or promote a PASS result.
