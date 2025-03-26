# Sports 2020

## ArgoCD
How to use in the playground:

```bash
kubectl apply -f application.yaml
```

## Manual

For manual deployment of the Helm chart:

```bash
cd dev
helm upgrade --install -f values.yaml sports2020 .
```

## Debug

To check what kubernetes manifests will be generated add `--dry-run`

```bash
cd dev
helm upgrade --dry-run --install -f values.yaml sports2020 .
```

When ArgoCD already deployed the chart it will refuse to overwrite it, so just change the namespace so it will be a *new* install (which doesn't matter because a *dry run* won't actually install it).

```bash
cd dev
helm upgrade --dry-run --install -f values.yaml --create-namespace --namespace dummy sports2020 .
```
