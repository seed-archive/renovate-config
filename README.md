# renovate-config

Shared Renovate presets for Seed Archive repositories.

| Preset | For | `renovate.json` |
|---|---|---|
| `default.json` | a site or the portal (npm) | `{"extends": ["github>seed-archive/renovate-config"]}` |
| `generator.json` | a game's generator (Cargo and pip) | `{"extends": ["github>seed-archive/renovate-config:generator"]}` |

The generator preset updates `Cargo.toml`/`Cargo.lock` and `requirements.txt` once a week: minor and patch together in
one pull request, each major only after it is approved on the Dependency Dashboard, and the lock file refreshed in the
same weekly window. Nothing merges itself: a generator has no CI, so its session runs the tests on the branch and merges
on the owner's word.
