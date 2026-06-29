# PortfolioCoach

Domain pack — **source profile** playbook for E*TRADE datastore inventory and quality review.

Shipped tooling produces CSV indexes, metrics, report section fragments, and evaluation scaffolds. Narrative report sections are **agent responsibility** (`outputCompleteness: scaffold`). Canonical rebuild/merge scripts are **not** shipped — see `datastore-merge-and-validate` workflow scope.

## Try it

- *Run a source profile for May 2026.*
- *Profile my datastore without the evaluation overlay.*

When no period is specified, the playbook defaults to **full available range** (`defaultResolution.period: fullAvailableRange`).

## About

- **Version:** 1.0.0 (see [`pack.app.yaml`](pack.app.yaml))
- **Playbook:** `source-profile` — see [`layer3-playbooks/source-profile/source-profile.app.yaml`](layer3-playbooks/source-profile/source-profile.app.yaml)

Persistent data and reports belong under the bound `{userDatastore}` (see `contracts/user-datastore-layout.md`), not in this behavior repo.
