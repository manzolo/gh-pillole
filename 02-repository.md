# gh — Repository

## Elenco repo

```bash
# I tuoi repo (max 30 di default)
gh repo list

# Con limite personalizzato
gh repo list --limit 100

# Solo pubblici o privati
gh repo list --visibility public
gh repo list --visibility private

# Di un altro utente o organizzazione
gh repo list nomeutente
gh repo list nomeorg

# Output JSON per filtrare con jq
gh repo list --json name,description,updatedAt --jq '.[].name'
```

## Visualizzare un repo

```bash
# Info sintetiche
gh repo view manzolo/ollapdf

# Apre nel browser
gh repo view manzolo/ollapdf --web
```

## Clonare

```bash
# Clone base (usa il protocollo configurato)
gh repo clone manzolo/ollapdf

# Clone in una cartella specifica
gh repo clone manzolo/ollapdf ~/progetti/ollapdf
```

## Creare un repo

```bash
# Pubblico con descrizione
gh repo create mio-progetto --public --description "Il mio progetto"

# Privato
gh repo create mio-progetto --private

# Con README e gitignore iniziali
gh repo create mio-progetto --public --add-readme --gitignore Python

# Partendo da una cartella locale già esistente
cd ~/progetti/mio-progetto
gh repo create --source=. --public --push
```

## Rinominare / Eliminare

```bash
# Rinominare
gh repo rename nuovo-nome -R manzolo/vecchio-nome

# Eliminare (chiede conferma)
gh repo delete manzolo/mio-progetto --yes
```

## Fork

```bash
# Fork di un repo altrui nel tuo account
gh repo fork utente/repo

# Fork e clone immediato
gh repo fork utente/repo --clone
```
