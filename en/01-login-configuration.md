# gh — Login & Configuration

## Login

```bash
# Interactive login (opens browser)
gh auth login

# Login with token (e.g. from CI or environment variable)
gh auth login --with-token <<< "ghp_yourtoken"

# Check authentication status
gh auth status
```

Expected output:
```
github.com
  ✓ Logged in to github.com account youruser (keyring)
  - Active account: true
  - Git operations protocol: ssh
  - Token scopes: 'admin:public_key', 'read:org', 'repo'
```

## Logout

```bash
gh auth logout
```

## Configuration

```bash
# View current configuration
gh config list

# Set preferred editor
gh config set editor nano

# Set default git protocol
gh config set git_protocol ssh

# Set default browser
gh config set browser firefox
```

## Update gh

```bash
# Check installed version
gh --version

# Update (Ubuntu/Debian)
sudo apt update && sudo apt upgrade gh
```
