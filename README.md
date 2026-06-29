# PortfolioCoach APP

Published **APP distribution repo** for PortfolioCoach — E*TRADE datastore inventory and quality profiling.

Shipped scripts produce CSV indexes, metrics, and report section **scaffolds**. Agents synthesize narrative report sections and complete evaluation reflection. Full canonical rebuild tooling is **not** shipped in this version.

| Pack | Description |
| --- | --- |
| [`portfolio-coach.app/`](portfolio-coach.app/) | Source profile playbook — datastore inventory and quality profile |

## Layout

```text
portfolio-coach-app/
  README.md                 ← this file (pack index)
  portfolio-coach.app/      ← pack instance
```

Pack entry: [`portfolio-coach.app/pack.app.yaml`](portfolio-coach.app/pack.app.yaml).

## APP standard (execution agents)

Read in order from the [APP Standards Workbench](https://github.com/4jeffclark/agent-playbook-pack):

1. [Authoring standard](https://github.com/4jeffclark/agent-playbook-pack/blob/main/standard/app-authoring.md)
2. [Execution guide](https://github.com/4jeffclark/agent-playbook-pack/blob/main/standard/app-execution.md)
3. [Post-run checklist](https://github.com/4jeffclark/agent-playbook-pack/blob/main/standard/post-run-checklist.md)

Then consume this repo's pack manifests and referenced layer artifacts. Pack `README.md` files are user welcome only — not execution authority.

## Try it

- *Run a source profile for May 2026.*
- *Profile my datastore without the evaluation overlay.*

Persistent data and reports belong under the bound `{userDatastore}` (see `portfolio-coach.app/contracts/user-datastore-layout.md`), not in this behavior repo.
