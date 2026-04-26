# gh — Pull Requests

## List PRs

```bash
# Open PRs in the current repo
gh pr list

# Open PRs in a specific repo
gh pr list -R user/repo

# Closed or merged PRs
gh pr list --state closed
gh pr list --state merged

# PRs created by you
gh pr list --author youruser

# PRs awaiting your review
gh pr list --search "review-requested:youruser"

# JSON output
gh pr list --json number,title,state,createdAt,author
```

## View a PR

```bash
# In the terminal
gh pr view 15 -R user/repo

# In the browser
gh pr view 15 -R user/repo --web

# CI/checks status
gh pr checks 15 -R user/repo
```

## Create a PR

```bash
# Interactive (from current branch)
gh pr create

# With title and body
gh pr create --title "Fix PDF parser" --body "Fixes #42"

# Draft (not ready for review)
gh pr create --draft --title "WIP: new feature"

# Against a specific base branch
gh pr create --base develop --title "Feature X"

# With reviewer and label
gh pr create \
  --title "Critical bug fix" \
  --body "Fixes #99" \
  --reviewer colleague \
  --label bug
```

## Comment on a PR

```bash
# General comment
gh pr comment 15 -R user/repo --body "LGTM, great work!"

# Comment from file
gh pr comment 15 -R user/repo --body-file review.md
```

## Review

```bash
# Approve
gh pr review 15 --approve

# Request changes
gh pr review 15 --request-changes --body "Tests are needed"

# Comment only
gh pr review 15 --comment --body "Also check config.py"
```

## Local checkout of a PR

```bash
# Download the PR branch locally
gh pr checkout 15 -R user/repo
```

## Merge

```bash
# Classic merge
gh pr merge 15

# Squash merge
gh pr merge 15 --squash

# Rebase merge
gh pr merge 15 --rebase

# Merge and delete branch
gh pr merge 15 --squash --delete-branch
```

## Close / Reopen without merging

```bash
gh pr close 15 -R user/repo
gh pr reopen 15 -R user/repo
```

## Search PRs across all repos

```bash
# Open PRs created by you (including other people's repos)
gh search prs --author @me --state open

# PRs awaiting your review
gh search prs --review-requested @me --state open
```
