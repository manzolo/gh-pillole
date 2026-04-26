# gh — Issues

## Elenco issue

```bash
# Issue aperte nel repo corrente
gh issue list

# Issue aperte in un repo specifico
gh issue list -R manzolo/ollapdf

# Issue chiuse
gh issue list --state closed

# Tutte (aperte + chiuse)
gh issue list --state all

# Filtro per label
gh issue list --label bug

# Assegnate a te
gh issue list --assignee @me

# Output JSON
gh issue list --json number,title,state,createdAt
```

## Visualizzare una issue

```bash
# Nel terminale
gh issue view 42 -R manzolo/ollapdf

# Nel browser
gh issue view 42 -R manzolo/ollapdf --web
```

## Creare una issue

```bash
# Interattivo (apre editor)
gh issue create -R manzolo/ollapdf

# Con titolo e corpo inline
gh issue create -R manzolo/ollapdf \
  --title "Bug nel parser PDF" \
  --body "Il parser crasha con file >10MB"

# Con label e assegnatario
gh issue create -R manzolo/ollapdf \
  --title "Aggiungere supporto EPUB" \
  --label enhancement \
  --assignee manzolo
```

## Commentare una issue

```bash
# Commento inline
gh issue comment 42 -R manzolo/ollapdf --body "Confermato, sto investigando."

# Commento da file
gh issue comment 42 -R manzolo/ollapdf --body-file commento.md
```

## Chiudere / Riaprire

```bash
# Chiudere
gh issue close 42 -R manzolo/ollapdf

# Chiudere con commento
gh issue close 42 -R manzolo/ollapdf --comment "Risolto in v1.2.0"

# Riaprire
gh issue reopen 42 -R manzolo/ollapdf
```

## Modificare una issue

```bash
# Cambiare titolo
gh issue edit 42 -R manzolo/ollapdf --title "Nuovo titolo"

# Aggiungere label
gh issue edit 42 -R manzolo/ollapdf --add-label bug,priority

# Rimuovere label
gh issue edit 42 -R manzolo/ollapdf --remove-label wontfix

# Assegnare
gh issue edit 42 -R manzolo/ollapdf --add-assignee manzolo
```

## Cerca issue su tutti i tuoi repo

```bash
# Issue aperte create da te
gh search issues --author manzolo --state open

# Issue aperte che ti riguardano
gh search issues --assignee manzolo --state open
```
