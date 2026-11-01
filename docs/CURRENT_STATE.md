# CURRENT_STATE

Status: ROS_ADOPTION_IN_PROGRESS

## Repository identity
- Repository: `lcm1226/safeopener-kvm-probe`
- Visibility: public
- Canonical branch: `main`
- Adoption base: `0f9fb9c3f84e55b6783e925d132d221cc13deb58`
- Adoption-base tree: `50b1de409a858bbb9a27eb82dfd1cbea60aa2c16`

## Role
This repository is a public supporting probe/execution surface for Safe Opener. Canonical Safe Opener semantics remain in `lcm1226/safe-opener`.

## Existing live surfaces at adoption base
- `.github/workflows/` contains KVM probe, external-control/external-flow, encrypted Track B host-local, and diagnostic workflows.
- `exchange/` contains runtime exchange material/history and is supporting evidence, not semantic authority.

## Active task gate
The current task may prepare zero-cost Track B KVM_REFERENCE supporting execution only after repository-first adoption and exact-binding preflight. No external KVM execution is established or promoted by this adoption commit.

## Safety / unresolved
- No paid provider or payment method is selected or authorized.
- No canonical Safe Opener proof acceptance or ADR promotion is authorized here.
- Fresh external execution still requires the task's exact preflight gates and current authorization.

## Track B KVM_REFERENCE preparation
- Work branch: `coord/ros-adoption-trackb-20261101`.
- Prepared implementation: `trackb-reference-observer.yml` and `trackb-reference-source.yml`; neither is present on canonical `main` yet.
- The observer is a zero-cost public GitHub-hosted runner using pinned `bore` v0.6.0 for a raw-TCP off-host endpoint and records established microVM pulse loss.
- The source exact-binds the canonical Safe Opener proof HEAD and generated local-attestation SHA-256, preserves host-local observation before arming canonical `blast-hold`, and publishes an exact run binding before any host-external cut.
- Automated provider-cancel controller is intentionally absent. The available tooling did not permit a compliant automated controller implementation.
- Critical unresolved gate: a manual provider-side cancel does not by itself provide a trustworthy cancel-request timestamp for canonical `externalCut.revokeToCutMs` / rotation timing. Do not consume the one authorized KVM_REFERENCE run until that measurement mechanism is resolved.
- External KVM_REFERENCE runs consumed: 0/1.
- Incremental provider cost: $0.
