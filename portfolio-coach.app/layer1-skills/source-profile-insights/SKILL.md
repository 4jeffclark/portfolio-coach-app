---
name: source-profile-insights
compatibility: Requires Python 3.11+ when running bundled scripts
outputCompleteness: scaffold
description: Synthesize datastore insights, scorecard, and coverage readiness for source-profile evaluation overlay.
metadata:
  packId: portfolio-coach
  layer: '1'
---

## Procedure

1. Run `scripts/run.py` after `datastore-inventory` completes
2. Read `SourceProfileScorecard.md` and merge into `Report.md` Evaluation section
3. Add agent reflection on export gaps and coverage (scorecard provides quantitative baseline)

## Scripts

Run from this skill directory. Paths are relative to the skill root per [agentskills.io](https://agentskills.io/specification).

| Script | Purpose |
| --- | --- |
| `scripts/run.py` | Execute skill logic; writes workspace artifacts and `skill-result.json` |

```bash
python scripts/run.py --datastore "$USER_DATASTORE" --workspace "$AGENT_WORKSPACE" --evaluation true
```

```powershell
python scripts/run.py --datastore $env:USER_DATASTORE --workspace $env:AGENT_WORKSPACE --evaluation true
```

## References

None.

## Outputs

- `SourceProfileScorecard.md` — quantitative baseline; agent extends reflection narrative

## Used by

- `layer3-playbooks/source-profile` (evaluation overlay only)
