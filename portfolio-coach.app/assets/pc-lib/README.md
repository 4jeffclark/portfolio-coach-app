# PortfolioCoach Python library

Shared stdlib-only helpers for `layer1-skills/*/scripts/run.py`.

Skill scripts resolve this path:

```text
../../assets/pc-lib
```

(relative to `portfolio-coach.app/` instance root)

## Layout resolution

`pc_lib.canonical.resolve_layout()` selects datastore paths:

| Precedence | Canonical | Raw E*TRADE |
| --- | --- | --- |
| Standard (preferred) | `{userDatastore}/data/canonical/` | `{userDatastore}/data/raw/etrade/` |
| Legacy | `{userDatastore}/canonical/` | `{userDatastore}/raw/etrade/` |

When both exist, standard wins. `validate_layout()` fails fast with a clear error when no usable layout is found.

## Workspace

Skills write under `{agentWorkspace}/<skill-id>/`. The platform should pass the active per-run subdirectory as `--workspace` when available (see APP `app-execution.md`).

## Date columns

`CANONICAL_DATE_COLUMNS` maps each canonical table to contract-defined date fields (e.g. `orders.csv` uses `Date`, not `ExportedAtLocal`).
