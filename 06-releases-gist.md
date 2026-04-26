# gh — Releases e Gist

## Releases

### Elenco

```bash
gh release list -R manzolo/ollapdf
```

### Visualizzare una release

```bash
gh release view v1.0.0 -R manzolo/ollapdf
```

### Creare una release

```bash
# Dalla tag esistente
gh release create v1.2.0 -R manzolo/ollapdf \
  --title "v1.2.0" \
  --notes "Aggiunto supporto EPUB, fix bug parser"

# Con generazione automatica delle note dal changelog
gh release create v1.2.0 -R manzolo/ollapdf \
  --title "v1.2.0" \
  --generate-notes

# Release draft (bozza)
gh release create v1.2.0 -R manzolo/ollapdf --draft

# Pre-release
gh release create v2.0.0-beta -R manzolo/ollapdf --prerelease

# Con allegati (asset)
gh release create v1.2.0 -R manzolo/ollapdf \
  --title "v1.2.0" \
  --notes "Fix vari" \
  dist/app-linux.tar.gz dist/app-windows.zip
```

### Caricare asset su release esistente

```bash
gh release upload v1.2.0 dist/app-linux.tar.gz -R manzolo/ollapdf
```

### Eliminare una release

```bash
gh release delete v1.0.0 -R manzolo/ollapdf --yes
```

---

## Gist

### Creare un gist

```bash
# Da file, pubblico
gh gist create script.sh --public --desc "Script utile"

# Da file, privato (default)
gh gist create config.json --desc "Configurazione di esempio"

# Da stdin
echo "Hello World" | gh gist create - --public --desc "Test"

# Più file in un gist
gh gist create file1.sh file2.py --public
```

### Elenco gist

```bash
gh gist list

# Output JSON
gh gist list --json id,description,public,updatedAt
```

### Visualizzare un gist

```bash
gh gist view ID_GIST

# Nel browser
gh gist view ID_GIST --web
```

### Modificare un gist

```bash
gh gist edit ID_GIST
```

### Eliminare un gist

```bash
gh gist delete ID_GIST
```
