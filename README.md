# UKCEH Helm Chart Repository
Making Helm charts publicly available e.g., for use in Datalabs

## Using charts

### As a dependency in another chart

In another charts `Charts.yaml` add the dependency section

```yaml
dependencies:
  - name: metadata-catalogue
    version: 1.13.5
    repository: "https://nerc-ceh.github.io/charts"
```
Then install the dependency using `helm`
```bash
helm dependency build
```

## Making charts publicly available

### Packaging a chart
After a chart has been updated and the __version__ incremented in `Chart.yaml`

```bash
helm package directory/to/chart
```
creates a `.tgz` file to be added to repository

### Updating the index
The index (index.yaml) needs updating with the new version
```bash
helm repo index . --url https://nerc-ceh.github.io/charts
```

### Commit changes to GitHub

```bash
git status
git add -A
git commit
git push
```
