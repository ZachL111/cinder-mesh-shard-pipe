# cinder-mesh-shard-pipe

`cinder-mesh-shard-pipe` is a compact SQL repository for distributed systems, centered on this goal: Implement an SQL distributed systems project for shard simulation kernel, using seeded input scenarios and deterministic summary checks.

## Project Rationale

I want this repository to be useful as a quick reading exercise: fixtures first, implementation second, verifier last.

## Cinder Mesh Shard Pipe Review Notes

The first comparison I would make is `lease drift` against `quorum health` because it shows where the rule is most opinionated.

## Feature Set

- `fixtures/domain_review.csv` adds cases for quorum health and lease drift.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/cinder-mesh-shard-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `lease drift` and `quorum health`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Architecture

The implementation keeps the scoring rule plain: reward signal and confidence, preserve slack, penalize drag, then classify the result into a review lane.

The SQL checks add a separate view over the domain review fixture.

## Usage

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Test Command

The same command runs the local verification path. The highest-scoring domain case is `stress` at 245, which lands in `ship`. The most cautious case is `baseline` at 133, which lands in `watch`.

## Next Improvements

This remains a local project with deterministic fixtures. It does not depend on credentials, hosted services, or live data. Future work should add richer malformed inputs before widening the public API.
