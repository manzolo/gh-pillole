# gh — GitHub Actions e Workflow

## Elenco workflow

```bash
# Workflow disponibili nel repo
gh workflow list -R manzolo/ollapdf

# Dettaglio di un workflow
gh workflow view "Build and Push" -R manzolo/ollapdf
```

## Elenco run

```bash
# Ultime run
gh run list -R manzolo/ollapdf

# Di un workflow specifico
gh run list -R manzolo/ollapdf --workflow docker-publish.yml

# Solo quelle fallite
gh run list -R manzolo/ollapdf --status failure

# Output JSON
gh run list -R manzolo/ollapdf --json databaseId,status,conclusion,createdAt
```

## Visualizzare una run

```bash
# Stato e step
gh run view 12345678 -R manzolo/ollapdf

# Log completo
gh run view 12345678 -R manzolo/ollapdf --log

# Solo i log falliti
gh run view 12345678 -R manzolo/ollapdf --log-failed

# Nel browser
gh run view 12345678 -R manzolo/ollapdf --web
```

## Aspettare il completamento

```bash
# Attende e mostra progresso in tempo reale
gh run watch 12345678 -R manzolo/ollapdf
```

## Avviare / Riavviare

```bash
# Avviare manualmente un workflow (workflow_dispatch)
gh workflow run docker-publish.yml -R manzolo/ollapdf

# Riavviare una run fallita
gh run rerun 12345678 -R manzolo/ollapdf

# Riavviare solo i job falliti
gh run rerun 12345678 -R manzolo/ollapdf --failed
```

## Annullare una run in corso

```bash
gh run cancel 12345678 -R manzolo/ollapdf
```

## Download artefatti

```bash
# Scarica tutti gli artefatti di una run
gh run download 12345678 -R manzolo/ollapdf

# Scarica un artefatto specifico
gh run download 12345678 -R manzolo/ollapdf --name nome-artefatto
```
