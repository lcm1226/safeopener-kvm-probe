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
- PR #5 merged the temporary one-shot bootstrap to canonical `main` as `4781b7c64bda21a6f44dcf6ecfb3bda766359383`, which automatically started campaign `20261102587109`.
- Exact binding: Safe Opener `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`; fresh local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`; bootstrap run `41331112612`; observer run `41331122205`; source run `41331134357`.
- The source accepted and decrypted the exact-bound relay, passed its relay/hash/attestation checks, ran the real KVM base campaign, and published `trackb-ref-source-base-20261102587109.json` to `runtime-state`.
- The base observation records successful Firecracker boot/snapshot/restore, fresh-session separation, bounded packing, controlled stream readiness, and attempted real-worker egress/lifecycle release-gate observations. No canonical `TB-*`, R4/R5 composite row, or ADR-010 state is promoted from this partial evidence.
- The source then failed before `BLAST_ARMED` with `FATAL:blast_duration_invalid`: public workflow input `SO_TRACKB_BLAST_DURATION_SECONDS=1500` violated the exact canonical campaign hard bound `<=300` seconds. The observer therefore received no qualifying pulse sequence and ended without an established-flow record; the controller was never dispatched.
- External KVM_REFERENCE execution count became 1 consumed. Incremental provider cost remained $0.
- PR #6 removed only the temporary one-shot bootstrap and merged as `c56b1ac3ecbd18046f2dd4b2fa2868f2d41f4ea1`; the merge-triggered pre-existing KVM capability probe `41333834817` succeeded and does not constitute another Track B campaign.
- PR #7 merged source remediation as `568f30176d60e3e6fe7b84354e812bb66a5f90b4`: resolve `bore.pub` to a global IPv4 candidate, require successful raw-TCP preflight to the exact observer port, pass the verified IPv4 to canonical blast-hold, constrain blast duration to `300`, and preserve hostname + selected-IP provenance.
- Canonical reducer output for the partial base observation remained unpromoted; no ADR acceptance followed.

## 2026-11-02 — corrective continuation consumed; relay delivery timed out
- A fresh broad authorization allowed exactly one additional corrective KVM_REFERENCE attempt plus failure/success convergence, with no automatic third attempt.
- PR #8 merged the bounded blast-only corrective continuation to `main` as `668a32734abd5febe8ffd7c86ad166a87c489cb0` for campaign `20261102991701`.
- Exact-main automatic KVM capability probe `41394324360` completed successfully. Bootstrap `41394324377` then dispatched observer `41394341794` and continuation source `41394356630` with exact Safe Opener proof head `ed865d3bb49bac3157ca4eb0523c69ae83753d5f` and local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`.
- Observer readiness succeeded at `bore.pub:27005`. The continuation source independently resolved and TCP-preflighted global IPv4 `159.223.110.159:27005`, generated a one-time RSA relay key, and uploaded the public-key artifact.
- The encrypted relay ciphertext was never written to `runtime-state/exchange/41394356630/`; the source observed repeated HTTP `404` responses and exited `70` with `RELAY_WAIT_TIMEOUT` after the bounded 900-second wait.
- Because relay decryption never began, the source never published `trackb-ref-continuation-base` or `trackb-ref-continuation-armed`, canonical `blast-hold` never started, and the continuation controller was never dispatched. Runtime state contains only the exact continuation bootstrap-dispatch record and observer-ready record for this campaign; no controller result or combined observation exists.
- Bootstrap failed closed with `SOURCE_PREARM_CONCLUSION=failure` / exit `111` after the source terminated.
- Observer run `41394341794` then completed `failure` / exit `25` after its 30-minute bounded wait expired without two qualifying pulses; job cleanup terminated the observer/bore processes. No observer-established or observer-cut state was emitted.
- This separately authorized corrective attempt is treated as consumed. Two external Track B execution attempts have now occurred in total; no third KVM_REFERENCE attempt is authorized.
- No Track B proof row, composite R4/R5 row, ADR-010 acceptance, provider selection, or production rollout is promoted. Incremental provider cost remains `$0` and no paid-provider/payment mutation occurred.
- The temporary continuation bootstrap/source/controller workflows are removed by the failure-convergence cleanup. The historical `runtime-state` records remain preserved as audit evidence and must not be reused as a fresh run.
- During cleanup coordination, two accidental empty-file add/revert pairs briefly advanced public `main`; both were immediately reverted without force-push/amend. The resulting canonical tree returned exactly to PR #8 tree `07f73b244d351d14651d443a5e719bccc3610268`, so no lasting file-content or workflow-semantic delta remained from those incidents.

## 2026-11-02 — third exact-head Track B reference campaign completed
- Campaign `20261102162500` executed on public probe `main@80543b367c1cd4c58eba4d197462f84b970d4219`, bound to Safe Opener `d11d2881324e3c7f0b5714c90580129ca88ddaa2` and attestation SHA-256 `a75e6e95d55f4eef520ada8be2f2912f2b50cef14a480767a5a941e7f11533c5`.
- Relay-only preflight had already proved deterministic encrypted delivery before this KVM run. The third source relay was published to exact source run `41406328470` without moving public `main`; source decryption/exact binding succeeded.
- Base observation completed with boot-to-ready 2204 ms, restore-to-ready 374 ms, real-browser residue absent, stream-ready 5754 ms, packing cap 1 on 4 vCPU / 15983 MiB with measured headroom, full bounded R4 egress observations, and bounded R5 lifecycle observations.
- Observer established two qualifying pulses before controller action and later recorded the established-flow cut. Controller `41407138359` succeeded with revoke-to-cut 4850 ms, source terminal cancellation, observer success, replacement KVM health, rotation 22566 ms, and measured incremental rotation cost `$0`.
- Bootstrap `41406289723` mechanically assembled `trackb-ref-combined-observation-20261102162500.json` and completed successfully.
- Three external Track B attempts are now consumed in total. No fourth KVM_REFERENCE attempt is authorized. No proof/ADR promotion, provider/payment mutation, production rollout, or runtime-evidence deletion occurred in this public repository.
