# gh — Pillole pratiche

Raccolta di guide rapide per usare **gh**, la CLI ufficiale di GitHub, direttamente dal terminale.  
Ogni pillola è un file Markdown indipendente con esempi pronti all'uso.

---

## Installazione

### Ubuntu / Debian

```bash
sudo apt update
sudo apt install gh
```

Se la versione nei repo è troppo vecchia, usa il repo ufficiale:

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

### Verifica installazione

```bash
gh --version
```

---

## Primo accesso

```bash
gh auth login
```

Segui le istruzioni: scegli **GitHub.com**, protocollo **SSH** (consigliato) e autenticati via browser.

Verifica che tutto funzioni:

```bash
gh auth status
```

---

## Indice delle pillole

| # | File | Argomento |
|---|------|-----------|
| 1 | [Login e Configurazione](01-login-configurazione.md) | Login, logout, stato autenticazione, configurazione editor e protocollo |
| 2 | [Repository](02-repository.md) | Elenco, visualizzazione, clone, creazione, fork, rinomina, eliminazione |
| 3 | [Issues](03-issues.md) | Elenco, creazione, commenti, chiusura, modifica, ricerca su tutti i repo |
| 4 | [Pull Request](04-pull-requests.md) | Elenco, creazione, commenti, review, checkout, merge, ricerca su repo altrui |
| 5 | [Actions e Workflow](05-actions-workflow.md) | Elenco run, log, watch, avvio manuale, riavvio, annullamento, artefatti |
| 6 | [Releases e Gist](06-releases-gist.md) | Creazione release con asset, pre-release, gist pubblici e privati |

---

## Comandi più usati in sintesi

```bash
# Autenticazione
gh auth login
gh auth status

# Repository
gh repo list --limit 50
gh repo clone utente/repo
gh repo create mio-progetto --public

# Issues
gh issue list -R utente/repo
gh issue create -R utente/repo --title "..." --body "..."
gh issue close 42 -R utente/repo --comment "Risolto"

# Pull Request
gh pr list -R utente/repo
gh pr create --title "..." --body "..."
gh pr merge 15 --squash --delete-branch

# Actions
gh run list -R utente/repo
gh run watch 12345678 -R utente/repo

# Cerca su tutto GitHub
gh search prs --author @me --state open
gh search issues --assignee @me --state open
```

---

## Risorse utili

- [Documentazione ufficiale gh](https://cli.github.com/manual/)
- [Repository gh su GitHub](https://github.com/cli/cli)
- `gh help` — aiuto inline per qualsiasi comando
- `gh <comando> --help` — aiuto specifico (es. `gh pr create --help`)
