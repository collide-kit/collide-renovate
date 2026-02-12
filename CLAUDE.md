# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

`@collide-kit/collide-renovate` is a shareable [Renovate](https://docs.renovatebot.com/) configuration preset for CollideKit projects. The sole published artifact is [default.json](default.json).

Consumers extend it via:

```json
{ "extends": ["github>collide-kit/collide-renovate"] }
```

## Commands

Package manager: **Yarn 4.12.0** (`yarn` — not `npm` or `pnpm`).

```bash
yarn install          # install dependencies

yarn test             # validate default.json with renovate-config-validator

yarn fmt:check        # check formatting (no-cache)
yarn fmt:fix          # auto-fix formatting (no-cache)
yarn fmt:check:cache  # check formatting with cache
yarn fmt:fix:cache    # auto-fix formatting with cache
```

CI runs `format` + `test` jobs on every PR and push to `main`.

## Architecture

This repo has almost no source code — it is purely configuration:

- **[default.json](default.json)** — the Renovate preset (the only published file). All changes to dependency-update behaviour live here.
- **[renovate.json](renovate.json)** — self-applies the preset to keep this repo's own dependencies up to date.
- **[prettier.config.ts](prettier.config.ts)** — shared Prettier config using `@prettier/plugin-oxc`, `prettier-plugin-packagejson`, `prettier-plugin-sort-json`, and `prettier-plugin-multiline-arrays`. JSON files use 2-space indent; everything else uses tabs (width 4).

## Key preset behaviour (default.json)

| Setting                 | Value                                                          |
| ----------------------- | -------------------------------------------------------------- |
| Base                    | `config:recommended` + `schedule:weekly` + `group:allNonMajor` |
| `minimumReleaseAge`     | 3 days                                                         |
| `rangeStrategy`         | `bump`                                                         |
| `postUpdateOptions`     | `yarnDedupeHighest`                                            |
| Timezone                | `Europe/Zurich`                                                |
| `peerDependencies`      | disabled                                                       |
| `devDependencies` patch | automerged when CI passes                                      |
| Major updates           | labeled `dependencies` + `major`                               |
