# UKCEH Helm Chart Repository
Making Helm charts available

## Using charts

In `Charts.yaml` add dependency

```yaml
dependencies:
  - name: metadata-catalogue
    version: 1.10.0
    repository: "https://nerc-ceh.github.io/charts"
```

```bash
helm dependency build
```

## Adding charts

### Packaging a chart
After a chart has been updated and the __version__ incremented in `Chart.yaml`

```bash
helm package directory/to/chart
```
creates a `.tgz` file to be added to repository

### Updating the index
The index needs updating to for the new version
```bash
helm repo index . --url https://nerc-ceh.github.io/charts
```

### Commit to Git

```bash
git status
git add -A
git commit
git push
```