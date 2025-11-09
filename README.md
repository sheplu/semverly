# Semverly

**Semverly** is an open-source CLI and API that helps you **analyze, monitor, and update your project dependencies** with full semantic-versioning awareness.  
Check outdated packages, compare your current stack with the latest versions, and upgrade safely — all from one simple command.

## Features

- **Semantic awareness** — detects and separates patch, minor, and major updates  
- **Multi-manager support** — works with `npm`, `yarn`, and `pnpm`  
- **Dependency status view** — see what’s up-to-date, outdated, or deprecated  
- **Selective upgrades** — update only patch/minor/major versions  
- **Interactive mode** — upgrade interactively or output JSON for CI/CD  
- **Safety checks** — warns about breaking changes before upgrades  
- **Report generation** — export dependency states to Markdown, JSON, or table view  

## Quick Start

### 1. Install

```bash
npm install -g semverly
```

### 2. Check your dependencies

```bash
semverly status
```

Displays a table of all dependencies with:

- current version
- latest patch/minor/major
- update availability

### 3. Upgrade selectively

```bash
# Upgrade only minor versions
semverly upgrade --minor

# Upgrade only major versions
semverly upgrade --major

# Upgrade everything safely
semverly upgrade --all
```

### 4. Interactive Mode

```bash
semverly interactive
```

Launch an interactive prompt to pick which dependencies to upgrade.

## Example Output

``` sql
semverly status

Dependency     Current   Latest   Type     Status
────────────── ───────── ──────── ──────── ─────────────
react          18.2.0    19.0.1   major    ⚠️  Outdated
typescript     5.6.3     5.7.1    minor    🟡  Minor update available
eslint         9.2.0     9.2.0    patch    ✅  Up to date
```

## CLI Commands

| Command | Description |
|----------|--------------|
| `semverly status` | Display current dependency versions and available updates |
| `semverly upgrade` | Upgrade dependencies with specific filters |
| `semverly interactive` | Run an interactive upgrade session |
| `semverly report` | Export a dependency status report to file |
| `semverly help` | Show all commands and options |

## Options

| Flag | Description |
|------|--------------|
| `--major` | Include major version upgrades |
| `--minor` | Include minor version upgrades |
| `--patch` | Include patch upgrades only |
| `--all` | Apply all available updates |
| `--json` | Output as JSON |
| `--output <file>` | Save report to file |
| `--dry-run` | Show what would change without applying updates |

## API (Planned)

Semverly will soon provide a programmatic API for integrating dependency intelligence into CI/CD pipelines and dashboards.

```js
import { getStatus, upgrade } from "semverly";

const report = await getStatus({ manager: "npm" });
await upgrade({ type: "minor" });
```

## Roadmap

- [ ] Support for monorepos (`workspaces`, `pnpm`, `nx`)  
- [ ] GitHub Action for automatic reports  
- [ ] AI-powered changelog summarization  
- [ ] HTML dashboard output  
- [ ] CI/CD safe-mode auto-approve pipeline  

## Why “Semverly”?

Semantic Versioning (SemVer) defines how software evolves safely.  
**Semverly** brings that principle to life — *versioning done clearly, safely, and smartly.*

## Contributing

Contributions, ideas, and issues are welcome!  

1. Fork the repo  
2. Create your feature branch  
3. Commit changes  
4. Submit a pull request  

## License

[MIT License](./LICENSE) © 2025
