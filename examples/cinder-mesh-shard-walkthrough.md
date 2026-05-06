# Cinder Mesh Shard Pipe Walkthrough

This note is the quickest way to read the extra review model in `cinder-mesh-shard-pipe`.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | quorum health | 133 | watch |
| stress | lease drift | 245 | ship |
| edge | replica lag | 197 | ship |
| recovery | membership churn | 144 | ship |
| stale | quorum health | 139 | watch |

Start with `stress` and `baseline`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

If `baseline` becomes less cautious without a clear reason, I would inspect the drag input first.
