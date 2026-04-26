# gh — Login e Configurazione

## Login

```bash
# Login interattivo (apre il browser)
gh auth login

# Login con token (es. da CI o variabile d'ambiente)
gh auth login --with-token <<< "ghp_iltuotoken"

# Verifica stato autenticazione
gh auth status
```

Output atteso:
```
github.com
  ✓ Logged in to github.com account manzolo (keyring)
  - Active account: true
  - Git operations protocol: ssh
  - Token scopes: 'admin:public_key', 'read:org', 'repo'
```

## Logout

```bash
gh auth logout
```

## Configurazione

```bash
# Vedere la configurazione attuale
gh config list

# Impostare l'editor preferito
gh config set editor nano

# Impostare il protocollo git di default
gh config set git_protocol ssh

# Impostare il browser di default
gh config set browser firefox
```

## Aggiornare gh

```bash
# Verificare la versione installata
gh --version

# Aggiornare (Ubuntu/Debian)
sudo apt update && sudo apt upgrade gh
```
