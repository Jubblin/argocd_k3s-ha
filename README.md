# Self Managed Argo CD - App of Everything

Installation:

```bash
cd argocd-install
helm dep update ./argo-helm/charts/argo-cd/
helm install argocd ./argo-helm/charts/argo-cd/ \
    --namespace=argocd \
    --create-namespace \
    -f values-override.yaml
```

