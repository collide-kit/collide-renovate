# ⚫ @collide-kit/collide-renovate

## 1.0.0 🚀

### Major Release

🎉 **Initial release of `@collide-kit/collide-renovate`**

The first stable release of **@collide-kit/collide-renovate** — a shareable [Renovate](https://docs.renovatebot.com/) configuration preset for the **@collide-kit** ecosystem.

### ✨ Features

- **`default.json`** — shareable Renovate configuration preset
  - 📅 Weekly update schedule (`schedule:weekly`) in `Europe/Zurich` timezone
  - 📦 All non-major updates grouped into a single PR (`group:allNonMajor`)
  - 🛡️ 3-day minimum release age to avoid yanked packages
  - ✅ Automerge for `devDependencies` patch updates (when CI passes)
  - 🏷️ `dependencies` label on all PRs; `major` label added for breaking-change PRs
  - 🔒 `peerDependencies` updates disabled
  - 🧹 `yarnDedupeHighest` runs after every update
  - ⬆️ `rangeStrategy: bump` keeps ranges in sync with installed versions
  - 💬 Commit messages formatted as `` `🧩 chore(deps): update <package>` ``
  - 📊 Dependency Dashboard with OSV vulnerability summary (unresolved only)
  - 🔄 Dashboard auto-closes when no open dependency PRs remain
