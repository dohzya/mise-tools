# mise Backend for dohzya/tools

mise backend for installing `md` (markdown-surgeon) and `wl` (worklog) tools as a bundle.

## Installation

```bash
# Direct installation
mise use https://github.com/dohzya/mise-tools@v0.5.0

# Or in .mise.toml
[tools]
"https://github.com/dohzya/mise-tools" = "0.5.0"
```

## What Gets Installed

This installs **both** tools together:
- `wl` - Worklog tool for tracking development progress
- `md` - Markdown-surgeon for surgical markdown manipulation

## Bundle Versions

Bundle releases (e.g., `v0.5.0`) contain specific versions of both tools:

- `v0.5.0` = `wl-0.4.4` + `md-0.4.0`

Check [dohzya/tools releases](https://github.com/dohzya/tools/releases) to see what's included in each bundle.

## Individual Tool Installation

If you need to install tools separately or use different versions, use homebrew:

```bash
brew install dohzya/tools/wl
brew install dohzya/tools/md
```

## How It Works

This is a custom mise backend that:

1. **list-all**: Fetches all GitHub release tags matching `v*` (bundle releases)
2. **download**: Downloads both `wl` and `md` binaries for your platform
3. **list-bin-paths**: Tells mise where the binaries are located

## Requirements

- `curl` - For downloading binaries
- `gh` - GitHub CLI for listing releases
- `jq` - For parsing JSON responses

## Updating

```bash
# Update to latest bundle
mise upgrade https-github-com-dohzya-mise-tools

# Or update version in .mise.toml and reinstall
mise install
```

## Uninstalling

```bash
mise uninstall https-github-com-dohzya-mise-tools
```

## More Information

- Main repo: [dohzya/tools](https://github.com/dohzya/tools)
- Homebrew tap: [dohzya/homebrew-tools](https://github.com/dohzya/homebrew-tools)
- Full documentation: [dohzya/tools - Installation Guide](https://github.com/dohzya/tools#installation)
