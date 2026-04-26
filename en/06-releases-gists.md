# gh — Releases & Gists

## Releases

### List

```bash
gh release list -R user/repo
```

### View a release

```bash
gh release view v1.0.0 -R user/repo
```

### Create a release

```bash
# From an existing tag
gh release create v1.2.0 -R user/repo \
  --title "v1.2.0" \
  --notes "Added EPUB support, fixed parser bug"

# With auto-generated notes from changelog
gh release create v1.2.0 -R user/repo \
  --title "v1.2.0" \
  --generate-notes

# Draft release
gh release create v1.2.0 -R user/repo --draft

# Pre-release
gh release create v2.0.0-beta -R user/repo --prerelease

# With attached assets
gh release create v1.2.0 -R user/repo \
  --title "v1.2.0" \
  --notes "Various fixes" \
  dist/app-linux.tar.gz dist/app-windows.zip
```

### Upload asset to existing release

```bash
gh release upload v1.2.0 dist/app-linux.tar.gz -R user/repo
```

### Delete a release

```bash
gh release delete v1.0.0 -R user/repo --yes
```

---

## Gists

### Create a gist

```bash
# From file, public
gh gist create script.sh --public --desc "Useful script"

# From file, private (default)
gh gist create config.json --desc "Sample configuration"

# From stdin
echo "Hello World" | gh gist create - --public --desc "Test"

# Multiple files in one gist
gh gist create file1.sh file2.py --public
```

### List gists

```bash
gh gist list

# JSON output
gh gist list --json id,description,public,updatedAt
```

### View a gist

```bash
gh gist view GIST_ID

# In the browser
gh gist view GIST_ID --web
```

### Edit a gist

```bash
gh gist edit GIST_ID
```

### Delete a gist

```bash
gh gist delete GIST_ID
```
