# Workflow — datastore-merge-and-validate

## Workflow Id

`datastore-merge-and-validate`

## Layer

0 — infrastructure

## Workflow kind

**Agent-only procedure** — no canonical rebuild tooling is shipped in this pack. Minimum gate evidence: existing canonical state validated (or session attachments copied when present); datastore range summary noted for input discovery.

## Purpose

Validate the bound datastore layout, handle optional session attachments, and report available date range for input discovery. **Does not** perform a full canonical rebuild unless a future merge skill is added.

## Scope (honest)

| Shipped | Not shipped |
| --- | --- |
| Layout resolution via `pc-lib` (standard and legacy paths) | Full canonical rebuild from all raw files |
| Validate existing canonical tables are readable | Automated dedup rebuild |
| Copy new files from `{userDatastore}/inputs/` when present | Hash-indexed merge pipeline as full script |

For merge/rebuild semantics, see [`contracts/datastore-contract.md`](../contracts/datastore-contract.md). This workflow validates and prepares; agents inspect canonical state when no rebuild tooling runs.

## Procedure

1. Resolve layout per [`contracts/user-datastore-layout.md`](../contracts/user-datastore-layout.md) (`pc-lib` resolves standard `data/` and legacy root layouts)
2. If `{userDatastore}/inputs/` contains new attachments, copy them to the appropriate `raw/etrade/` subfolder per contract naming — do **not** rebuild canonical in this pack version
3. Validate existing canonical tables are present and readable; note layout warnings from `pc-lib`
4. Summarize available date range from `ingestion_manifest.csv` or canonical date columns for structured input discovery
5. Clear the `datastore-merge-complete` gate (self-attested)

## Outputs

- Datastore range summary for structured input discovery
- Cleared `datastore-merge-complete` gate (self-attested)
