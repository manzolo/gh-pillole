# gh — Quick Reference

A collection of practical guides for using **gh**, GitHub's official CLI, directly from the terminal.  
Each pill is a standalone Markdown file with ready-to-use examples.

---

## Installation

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install gh
```

If the version in the repositories is too old, use the official repo:

```bash
(type -p wget >/dev/null || sudo apt install wget -y) \
  && sudo mkdir -p -m 755 /etc/apt/keyrings \
  && out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
  && cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
  && sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
  && sudo apt update \
  && sudo apt install gh -y
```

### Fedora / RHEL / CentOS

```bash
sudo dnf install gh
```

### Arch Linux

```bash
sudo pacman -S github-cli
```

### macOS

```bash
brew install gh
```

### Verify installation

```bash
gh --version
```

---

## First login

```bash
gh auth login
```

Follow the prompts: choose **GitHub.com**, protocol **SSH** (recommended) and authenticate via browser.

Verify everything works:

```bash
gh auth status
```

---

## Index

| # | File | Topic |
|---|------|-------|
| 1 | [Login & Configuration](01-login-configuration.md) | Login, logout, auth status, editor and protocol settings |
| 2 | [Repositories](02-repositories.md) | List, view, clone, create, fork, rename, delete |
| 3 | [Issues](03-issues.md) | List, create, comment, close, edit, search across repos |
| 4 | [Pull Requests](04-pull-requests.md) | List, create, comment, review, checkout, merge, search across repos |
| 5 | [Actions & Workflows](05-actions-workflows.md) | List runs, logs, watch, manual trigger, rerun, cancel, artifacts |
| 6 | [Releases & Gists](06-releases-gists.md) | Create releases with assets, pre-releases, public and private gists |

---

## Most used commands at a glance

```bash
# Authentication
gh auth login
gh auth status

# Repositories
gh repo list --limit 50
gh repo clone user/repo
gh repo create my-project --public

# Issues
gh issue list -R user/repo
gh issue create -R user/repo --title "..." --body "..."
gh issue close 42 -R user/repo --comment "Fixed"

# Pull Requests
gh pr list -R user/repo
gh pr create --title "..." --body "..."
gh pr merge 15 --squash --delete-branch

# Actions
gh run list -R user/repo
gh run watch 12345678 -R user/repo

# Search across GitHub
gh search prs --author @me --state open
gh search issues --assignee @me --state open
```

---

## Useful resources

- [Official gh documentation](https://cli.github.com/manual/)
- [gh repository on GitHub](https://github.com/cli/cli)
- `gh help` — inline help for any command
- `gh <command> --help` — specific help (e.g. `gh pr create --help`)
