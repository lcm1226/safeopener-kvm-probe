# SOT_INDEX

| Fact domain | Canonical owner | Authority | Lifecycle |
|---|---|---|---|
| Repository discovery | `.sot/bootstrap.yaml` | discovery | stable |
| SoT map | `.sot/manifest.yaml` | machine-readable index | stable |
| Procedure / safety | `AGENTS.md` | procedural | stable |
| Document authority | `docs/SOT_INDEX.md` | index | stable |
| Current probe state | `docs/CURRENT_STATE.md` | live state | volatile |
| Future probe work | `docs/ROADMAP.md` | plan | evolving |
| Work log | `PROGRESS.md` | worklog | volatile |
| Workflow implementation | `.github/workflows/` | implementation | active |
| Runtime exchange artifacts | `exchange/` | supporting runtime evidence | volatile |

## External authority boundary
Safe Opener product/security/ADR/contracts/acceptance semantics are owned by `lcm1226/safe-opener`. This public probe repository may implement and collect supporting evidence but must not redefine or promote canonical proof semantics.
