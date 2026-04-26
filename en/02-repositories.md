# gh — Repositories

## List repos

```bash
# Your repos (default max 30)
gh repo list

# Custom limit
gh repo list --limit 100

# Only public or private
gh repo list --visibility public
gh repo list --visibility private

# Another user's or organization's repos
gh repo list username
gh repo list orgname

# JSON output for filtering with jq
gh repo list --json name,description,updatedAt --jq '.[].name'
```

## View a repo

```bash
# Summary in terminal
gh repo view user/repo

# Open in browser
gh repo view user/repo --web
```

## Clone

```bash
# Basic clone (uses configured protocol)
gh repo clone user/repo

# Clone into a specific folder
gh repo clone user/repo ~/projects/repo
```

## Create a repo

```bash
# Public with description
gh repo create my-project --public --description "My project"

# Private
gh repo create my-project --private

# With initial README and gitignore
gh repo create my-project --public --add-readme --gitignore Python

# From an existing local folder
cd ~/projects/my-project
gh repo create --source=. --public --push
```

## Rename / Delete

```bash
# Rename
gh repo rename new-name -R user/old-name

# Delete (asks for confirmation)
gh repo delete user/my-project --yes
```

## Fork

```bash
# Fork someone else's repo into your account
gh repo fork user/repo

# Fork and immediately clone
gh repo fork user/repo --clone
```
