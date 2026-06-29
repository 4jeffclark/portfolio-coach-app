# PortfolioCoach user datastore layout

Bind `userDatastore` to a host directory. Use this structure beneath it:

```text
{userDatastore}/
  data/
    raw/etrade/
    canonical/
  reports/
  inputs/
```

## Layout resolution

`pc-lib` resolves paths with this precedence:

1. **Standard** — `data/canonical/` and `data/raw/etrade/` when either exists
2. **Legacy** — `canonical/` and `raw/etrade/` at datastore root when standard paths are absent
3. **Default** — standard paths for new datastores

When both layouts exist, standard wins. Prefer migrating legacy layouts to the standard `data/` prefix.

## Raw data

`{userDatastore}/data/raw/etrade/` — immutable E*TRADE exports as provided by the user (or legacy `raw/etrade/`).

Supported export types: `balances`, `account_history`, `orders`, `portfolio_lot_level`.

## Canonical data

`{userDatastore}/data/canonical/` — normalized CSV tables derived from raw exports per [`datastore-contract.md`](datastore-contract.md).

## Reports

`{userDatastore}/reports/` — immutable run output folders per [`report-artifact-contract.md`](report-artifact-contract.md).

## Inputs

`{userDatastore}/inputs/` — optional session attachments pending merge.

## Knowledge (out of scope)

Some user datastores include a `knowledge/` tree (holdings, themes, theses, policies). **Source-profile playbook does not read or profile `knowledge/`** unless a future playbook explicitly adds it. Do not assume `data/knowledge/` — on-disk layout varies by user.

## Post-run verification

Self-verify report folders per [APP post-run checklist](https://github.com/4jeffclark/agent-playbook-pack/blob/main/standard/post-run-checklist.md).
