# CURRENT_STATE

Status: TRACKB_REFERENCE_EXECUTION_PREPARED

## Repository identity
- Repository: `lcm1226/safeopener-kvm-probe`
- Visibility: public
- Canonical branch: `main`
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58`
- Adoption-base tree: `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`
- ROS adoption merge: PR #1, `c4260d3e5048238e8b52e1fb91a5aa7d234bffbc`
- Track B execution-surface merge: PR #3, `11c5a4aed14bcf26651257440fa1c0e564c0d2e4`

## Role
This repository is a public supporting probe/execution surface for Safe Opener. Canonical Safe Opener semantics remain in `lcm1226/safe-opener`.

## Existing live surfaces
- `.github/workflows/` on canonical `main` contains the pre-existing KVM probe, external-control/external-flow, encrypted Track B host-local, diagnostic workflows, and the Track B reference observer/source/controller workflows merged by PR #3.
- `exchange/` contains runtime exchange material/history and is supporting evidence, not semantic authority.
- First-time ROS adoption is complete on canonical `main`.
- PR #3 merge triggered the pre-existing `kvm-capability-probe` push workflow once at run `41325605068`; it completed successfully and is not a Track B KVM_REFERENCE campaign execution.

## Active task gate
- The previous cancel-request timing design blocker is resolved at the implementation level: the canonical controller records its pre-force-cancel request timestamp, verifies provider `202` acceptance, compares it with the independent observer cut timestamp, verifies source terminal cancellation, and measures replacement timing.
- Runtime behavior of the new Track B reference observer/source/controller workflows remains `UNVERIFIED` until an authorized live dispatch is performed.
- External KVM_REFERENCE executions consumed: 0/1.
- Before consuming the one reference execution, rehydrate the canonical Safe Opener HEAD, generate/verify a fresh same-commit local attestation, bind the exact probe `main` HEAD and run IDs, and complete all zero-cost/off-host preflight gates.

## Safety / unresolved
- No paid provider or payment method is selected or authorized; incremental provider cost remains $0.
- No canonical Safe Opener proof acceptance or ADR promotion is authorized here.
- Historical runs and exchange material must not be reused as current proof.
- Fresh external execution requires a current authorization at the workflow-dispatch boundary.
