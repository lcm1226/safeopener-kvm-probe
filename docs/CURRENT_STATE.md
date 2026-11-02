# CURRENT_STATE

Status: TRACKB_REFERENCE_COMPLETE_SUPPORTING_EVIDENCE

## 2026-11-02 — third exact-head Track B reference campaign completed successfully
- A third and final execution authorized by the active bounded transaction completed as campaign `20261102162500` on public probe `main@80543b367c1cd4c58eba4d197462f84b970d4219`, bound to canonical Safe Opener proof head `d11d2881324e3c7f0b5714c90580129ca88ddaa2` and local-attestation SHA-256 `a75e6e95d55f4eef520ada8be2f2912f2b50cef14a480767a5a941e7f11533c5`.
- Exact-main KVM capability run `41406289774` passed before bootstrap dispatch. Bootstrap `41406289723`, observer `41406312148`, source `41406328470`, controller `41407138359`, and replacement KVM run `41407170369` are exact-bound supporting execution evidence.
- The source produced a real KVM base observation with Firecracker boot/snapshot/restore, real-browser fresh-session separation, bounded packing/BOM, controlled stream-ready timing, and the real-worker R4/R5 external matrix. The observer independently recorded an established flow and later the host-external cut.
- Controller evidence records `revokeToCutMs=4850`, source terminal cancellation, observer success, replacement KVM health, `rotationMs=22566`, and measured incremental rotation cost `$0` with provenance `github-public-standard-runner-zero-charge`. A final exact-bound combined observation was written to `runtime-state`.
- Canonical private reduction/review is owned by `lcm1226/safe-opener`; this public repository does not promote proof rows or ADR status. No fourth KVM_REFERENCE execution is authorized. Historical runtime/exchange evidence remains supporting audit evidence and must not be reused as a fresh run.

## Repository identity
- Repository: `lcm1226/safeopener-kvm-probe`
- Visibility: public
- Canonical branch: `main`
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58`
- Adoption-base tree: `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`
- ROS adoption merge: PR #1, `c4260d3e5048238e8b52e1fb91a5aa7d234bffbc`
- Track B execution-surface merge: PR #3, `11c5a4aed14bcf26651257440fa1c0e564c0d2e4`
- First one-shot campaign merge: PR #5, `4781b7c64bda21a6f44dcf6ecfb3bda766359383`
- First one-shot bootstrap cleanup merge: PR #6, `c56b1ac3ecbd18046f2dd4b2fa2868f2d41f4ea1`
- Source-remediation merge: PR #7, `568f30176d60e3e6fe7b84354e812bb66a5f90b4`
- Corrective-continuation merge: PR #8, `668a32734abd5febe8ffd7c86ad166a87c489cb0`

## Role
This repository is a public supporting probe/execution surface for Safe Opener. Canonical Safe Opener semantics remain in `lcm1226/safe-opener`.

## Existing live surfaces
- `.github/workflows/` on canonical `main` contains the pre-existing KVM probe, external-control/external-flow, encrypted Track B host-local, diagnostic workflows, and the Track B reference observer/source/controller workflows merged by PR #3.
- The temporary continuation bootstrap/source/controller workflows introduced by PR #8 are removed by the current failure-convergence cleanup; they are not a standing execution surface.
- `exchange/` and the `runtime-state` branch contain supporting runtime evidence/history and are not semantic authority.
- Historical runtime/exchange material is preserved for audit and must not be reused as a fresh execution.

## First consumed Track B reference execution
- Campaign `20261102587109` used Safe Opener proof HEAD `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`, local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`, probe execution HEAD `4781b7c64bda21a6f44dcf6ecfb3bda766359383`, bootstrap run `41331112612`, observer run `41331122205`, and source run `41331134357`.
- Exact relay/hash/attestation binding passed and the source published a real KVM base observation. The preserved observation records successful Firecracker boot/snapshot/restore, fresh-session separation, bounded packing, controlled stream readiness, and real-worker R4/R5 release-gate observations.
- The source then failed before `BLAST_ARMED` with `FATAL:blast_duration_invalid`: the public workflow requested `1500` seconds while the canonical campaign permits at most `300` seconds.
- Host-external cut, host quarantine/replacement, blast-radius completion, and worker-rotation evidence were therefore not produced. No canonical proof or ADR state was promoted.

## Corrective continuation attempt
- PR #8 merged the bounded blast-only continuation to exact probe `main@668a32734abd5febe8ffd7c86ad166a87c489cb0` for campaign `20261102991701`, reusing the preserved base observation only after exact binding.
- The exact-main automatic KVM capability probe run `41394324360` completed successfully before continuation dispatch.
- Exact continuation binding: base campaign `20261102587109`; base source run `41331134357`; Safe Opener proof HEAD `ed865d3bb49bac3157ca4eb0523c69ae83753d5f`; local-attestation SHA-256 `b5d41c8c86586c80114abef7a50d1a30946a4e49bccd63e03c56b4b1b7c10766`; bootstrap run `41394324377`; observer run `41394341794`; continuation source run `41394356630`.
- Bootstrap preflight passed, the observer published `trackb-ref-observer-ready-20261102991701.json` for `bore.pub:27005`, and the continuation source independently resolved/preflighted global IPv4 `159.223.110.159:27005`.
- The continuation source generated and uploaded its one-time public relay key, but the required encrypted relay ciphertext was never published to `runtime-state/exchange/41394356630/`. The source observed repeated HTTP 404 responses and terminated with `RELAY_WAIT_TIMEOUT` / exit `70` after the bounded wait.
- Because relay decryption never occurred, no `trackb-ref-continuation-base`, `trackb-ref-continuation-armed`, controller result, or combined observation state exists. Canonical `blast-hold` did not start and the continuation controller was never dispatched.
- The bootstrap therefore failed closed with `SOURCE_PREARM_CONCLUSION=failure` / exit `111`.
- Observer run `41394341794` completed with conclusion `failure` and exit `25` after its 30-minute bounded established-flow wait expired without two qualifying pulses. Its job cleanup then terminated the observer/bore orphan processes. No observer-established or observer-cut state was emitted.
- The separately authorized corrective KVM_REFERENCE attempt is consumed. Together with the first attempt, two external Track B execution attempts have occurred. No third KVM_REFERENCE attempt is authorized by the current task.

## Proof / acceptance state
- The preserved first-attempt base observation remains supporting evidence only.
- `TB-HOST-EXTERNAL-CUT`, `TB-HOST-QUARANTINE-REPLACE`, `TB-BLAST-RADIUS`, and `TB-WORKER-ROTATION` remain unproven because no host-external controller phase completed.
- Canonical reducer/ADR-010 readiness cannot be promoted from the available evidence. Do not hand-assemble PASS rows from partial or cross-run state.
- ADR-010 remains `proposed` in canonical Safe Opener; no proof promotion, architecture acceptance, provider selection, or production rollout is established here.

## Safety / unresolved
- Incremental provider cost remains `$0`; no paid provider, larger paid runner, or payment-method change was used.
- No known-malicious target or production workload was executed.
- Any third KVM_REFERENCE execution, proof promotion, ADR acceptance, provider/payment mutation, or branch deletion requires separate fresh authorization.
- The next technical execution blocker is no longer KVM capability or the corrected blast bounds; it is a complete, exact-bound relay delivery/orchestration path that must be statically verified before any separately authorized future run.
