# CURRENT_STATE

Status: ROS_ADOPTION_COMPLETE

## Repository identity
- Repository: `lcm1226/safeopener-kvm-probe`
- Visibility: public
- Canonical branch: `main`
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58`
- Adoption-base tree: `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`
- ROS adoption merge: PR #1, `c4260d3e5048238e8b52e1fb91a5aa7d234bffbc`
- ROS adoption canonical tree: `5d6e46ce8bff9f1c685dcb70cec48f2ca3030c4a`

## Role
This repository is a public supporting probe/execution surface for Safe Opener. Canonical Safe Opener semantics remain in `lcm1226/safe-opener`.

## Existing live surfaces
- `.github/workflows/` on canonical `main` contains the pre-existing KVM probe, external-control/external-flow, encrypted Track B host-local, and diagnostic workflows.
- `exchange/` contains runtime exchange material/history and is supporting evidence, not semantic authority.
- First-time ROS adoption is complete on canonical `main`.

## Active task gate
- The exact-binding Track B preparation remains noncanonical on `coord/ros-adoption-trackb-20261101@bc5df31d04d342f29cf0c68c69ebc56b6b480eca` and is not merged into `main`.
- That branch prepares `trackb-reference-observer.yml` and `trackb-reference-source.yml`; it does not establish proof acceptance.
- External KVM_REFERENCE executions consumed: 0/1.
- Critical unresolved gate: a trustworthy provider cancel-request timestamp is still required for canonical `externalCut.revokeToCutMs` and rotation timing. Do not consume the one authorized KVM_REFERENCE run until that measurement mechanism is resolved.

## Safety / unresolved
- No paid provider or payment method is selected or authorized; incremental provider cost remains $0.
- No canonical Safe Opener proof acceptance or ADR promotion is authorized here.
- Fresh external execution still requires the task's exact preflight gates, exact commit/run binding, and current authorization.
