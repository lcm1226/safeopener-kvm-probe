# AGENTS.md

## Repository role
This repository is a public supporting execution/probe surface for Safe Opener. It does not own Safe Opener product, security, ADR, contract, or acceptance semantics; those remain in `lcm1226/safe-opener`.

## Authority and safety
- Rehydrate from `.sot/bootstrap.yaml` and the files it declares before substantive mutation.
- Live GitHub owns exact refs, workflow runs, checks, and review state.
- `.github/workflows/` owns probe workflow implementation; `exchange/` is supporting runtime evidence only.
- Never place private Safe Opener source, credentials, tokens, private keys, or secrets in this public repository.
- Do not infer proof acceptance from a successful probe run. Acceptance/promotion belongs to the canonical Safe Opener repository.
- Manual Actions runs, provider-side mutations, source writeback, merge, branch deletion, or other external mutations require fresh task authorization.
- Prefer public GitHub-hosted runners and zero-incremental-cost mechanisms. Do not add paid-provider or payment-method requirements without explicit authorization.
- Exact-binding evidence must identify the canonical Safe Opener commit and the relevant probe workflow/run identifiers.
- Stop on moved lease, ambiguous authority, unverifiable dependency, or scope expansion.
