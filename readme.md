# ⚫ @collide-kit/collide-renovate

[![CI](https://github.com/collide-kit/collide-renovate/actions/workflows/ci.yml/badge.svg)](https://github.com/collide-kit/collide-renovate/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Shareable [Renovate](https://docs.renovatebot.com/) configuration preset for **CollideKit** projects.

## 📦 Usage

Add to your `renovate.json` (or `renovate.json5`, `.renovaterc`):

```json
{
  "extends": ["github>collide-kit/collide-renovate"]
}
```

## ⚙️ What's included

| Setting                                      | Value                   | Description                                                |
| -------------------------------------------- | ----------------------- | ---------------------------------------------------------- |
| Base                                         | `config:recommended`    | Renovate recommended defaults                              |
| Schedule                                     | weekly                  | PRs created once a week                                    |
| Grouping                                     | `group:allNonMajor`     | All minor/patch updates in one PR                          |
| `minimumReleaseAge`                          | 3 days                  | Skips packages published less than 3 days ago              |
| `rangeStrategy`                              | `bump`                  | Bumps version inside the range (e.g. `^1.2.0` to `^1.3.0`) |
| `postUpdateOptions`                          | `yarnDedupeHighest`     | Runs `yarn dedupe --strategy highest` after updates        |
| Timezone                                     | `Europe/Zurich`         | Schedule runs in CET/CEST                                  |
| `labels`                                     | `dependencies`          | Applied to all dependency PRs                              |
| `commitMessagePrefix`                        | `` `🧩 chore(deps):` `` | Backtick-wrapped prefix for all commit messages            |
| `dependencyDashboardAutoclose`               | `true`                  | Closes the dashboard issue when no open PRs remain         |
| `dependencyDashboardOSVVulnerabilitySummary` | `unresolved`            | Shows only unresolved OSV vulnerabilities on the dashboard |
| `automergeStrategy`                          | `squash`                | Squash-merges automerged PRs into a single commit          |

### Package rules

- ✅ **`peerDependencies`** — disabled (not managed by Renovate)
- ✅ **`devDependencies` patch** — automerged when CI passes
- ✅ **major updates** — labeled with both `dependencies` and `major`

## 📄 License

MIT © 2026 CollideKit

---

**Made with ⚫ by [gratisv](https://github.com/gratisv)**
