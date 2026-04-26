# gh — GitHub Actions & Workflows

## List workflows

```bash
# Available workflows in the repo
gh workflow list -R user/repo

# Details of a specific workflow
gh workflow view "Build and Push" -R user/repo
```

## List runs

```bash
# Latest runs
gh run list -R user/repo

# For a specific workflow
gh run list -R user/repo --workflow docker-publish.yml

# Only failed runs
gh run list -R user/repo --status failure

# JSON output
gh run list -R user/repo --json databaseId,status,conclusion,createdAt
```

## View a run

```bash
# Status and steps
gh run view 12345678 -R user/repo

# Full log
gh run view 12345678 -R user/repo --log

# Only failed logs
gh run view 12345678 -R user/repo --log-failed

# In the browser
gh run view 12345678 -R user/repo --web
```

## Wait for completion

```bash
# Waits and shows real-time progress
gh run watch 12345678 -R user/repo
```

## Trigger / Rerun

```bash
# Manually trigger a workflow (workflow_dispatch)
gh workflow run docker-publish.yml -R user/repo

# Rerun a failed run
gh run rerun 12345678 -R user/repo

# Rerun only failed jobs
gh run rerun 12345678 -R user/repo --failed
```

## Cancel a running run

```bash
gh run cancel 12345678 -R user/repo
```

## Download artifacts

```bash
# Download all artifacts from a run
gh run download 12345678 -R user/repo

# Download a specific artifact
gh run download 12345678 -R user/repo --name artifact-name
```
