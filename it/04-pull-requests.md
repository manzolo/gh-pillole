# gh — Pull Request

## Elenco PR

```bash
# PR aperte nel repo corrente
gh pr list

# PR aperte in un repo specifico
gh pr list -R manzolo/ollapdf

# PR chiuse o merged
gh pr list --state closed
gh pr list --state merged

# PR create da te
gh pr list --author manzolo

# PR assegnate a te per review
gh pr list --search "review-requested:manzolo"

# Output JSON
gh pr list --json number,title,state,createdAt,author
```

## Visualizzare una PR

```bash
# Nel terminale
gh pr view 15 -R manzolo/ollapdf

# Nel browser
gh pr view 15 -R manzolo/ollapdf --web

# Stato check/CI
gh pr checks 15 -R manzolo/ollapdf
```

## Creare una PR

```bash
# Interattiva (da branch corrente)
gh pr create

# Con titolo e corpo
gh pr create --title "Fix parser PDF" --body "Risolve #42"

# Draft (bozza, non pronta per review)
gh pr create --draft --title "WIP: nuova feature"

# Verso un branch base specifico
gh pr create --base develop --title "Feature X"

# Con reviewer e label
gh pr create \
  --title "Fix bug critico" \
  --body "Fixes #99" \
  --reviewer collega \
  --label bug
```

## Commentare una PR

```bash
# Commento generale
gh pr comment 15 -R manzolo/ollapdf --body "LGTM, ottimo lavoro!"

# Commento da file
gh pr comment 15 -R manzolo/ollapdf --body-file review.md
```

## Review

```bash
# Approvare
gh pr review 15 --approve

# Richiedere modifiche
gh pr review 15 --request-changes --body "Serve aggiungere i test"

# Solo commento
gh pr review 15 --comment --body "Guarda anche il file config.py"
```

## Checkout locale di una PR

```bash
# Scarica il branch della PR in locale
gh pr checkout 15 -R manzolo/ollapdf
```

## Merge

```bash
# Merge classico
gh pr merge 15

# Squash merge
gh pr merge 15 --squash

# Rebase merge
gh pr merge 15 --rebase

# Merge con delete del branch
gh pr merge 15 --squash --delete-branch
```

## Chiudere / Riaprire senza merge

```bash
gh pr close 15 -R manzolo/ollapdf
gh pr reopen 15 -R manzolo/ollapdf
```

## Cerca PR su tutti i tuoi repo

```bash
# PR aperte create da te (anche su repo altrui)
gh search prs --author manzolo --state open

# PR in attesa di tua review
gh search prs --review-requested manzolo --state open
```
