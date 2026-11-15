# renovate-config

Shared Renovate presets for Seed Archive repositories.

| Preset | For | `renovate.json` |
|---|---|---|
| `default.json` | a site or the portal (npm) | `{"extends": ["github>seed-archive/renovate-config"]}` |
| `generator.json` | a game's generator (Cargo and pip) | `{"extends": ["github>seed-archive/renovate-config:generator"]}` |

Both extend Ethberry's rules (`github>ethberry/renovate-config:rules`): the schedule, the grouping, and the approval of majors are theirs. The generator preset adds only its managers, the lock file, and exact Python pins. It updates `Cargo.toml`/`Cargo.lock` and `requirements.txt` once a week: minor and patch together in
one pull request, each major only after it is approved on the Dependency Dashboard, and the lock file refreshed in the
same weekly window. Nothing merges itself: a generator has no CI, so its session runs the tests on the branch and merges
on the owner's word.
