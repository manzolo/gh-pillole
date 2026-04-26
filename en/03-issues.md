# gh — Issues

## List issues

```bash
# Open issues in the current repo
gh issue list

# Open issues in a specific repo
gh issue list -R user/repo

# Closed issues
gh issue list --state closed

# All (open + closed)
gh issue list --state all

# Filter by label
gh issue list --label bug

# Assigned to you
gh issue list --assignee @me

# JSON output
gh issue list --json number,title,state,createdAt
```

## View an issue

```bash
# In the terminal
gh issue view 42 -R user/repo

# In the browser
gh issue view 42 -R user/repo --web
```

## Create an issue

```bash
# Interactive (opens editor)
gh issue create -R user/repo

# With inline title and body
gh issue create -R user/repo \
  --title "Bug in PDF parser" \
  --body "Parser crashes with files >10MB"

# With label and assignee
gh issue create -R user/repo \
  --title "Add EPUB support" \
  --label enhancement \
  --assignee youruser
```

## Comment on an issue

```bash
# Inline comment
gh issue comment 42 -R user/repo --body "Confirmed, investigating."

# Comment from file
gh issue comment 42 -R user/repo --body-file comment.md
```

## Close / Reopen

```bash
# Close
gh issue close 42 -R user/repo

# Close with comment
gh issue close 42 -R user/repo --comment "Fixed in v1.2.0"

# Reopen
gh issue reopen 42 -R user/repo
```

## Edit an issue

```bash
# Change title
gh issue edit 42 -R user/repo --title "New title"

# Add labels
gh issue edit 42 -R user/repo --add-label bug,priority

# Remove a label
gh issue edit 42 -R user/repo --remove-label wontfix

# Assign
gh issue edit 42 -R user/repo --add-assignee youruser
```

## Search issues across all your repos

```bash
# Open issues created by you
gh search issues --author @me --state open

# Open issues assigned to you
gh search issues --assignee @me --state open
```
