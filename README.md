# argocd_k3s-ha

'''
helm upgrade argo-cd charts/argo-cd/ \
  --install \
  --namespace=argo-cd \
  --create-namespace
'''

The default username is admin. The password is auto-generated and we can get it with:

'''
kubectl get secret argocd-initial-admin-secret -n argo-cd -o jsonpath="{.data.password}" | base64 -d
'''

'''
helm template apps/ | kubectl apply -n argo-cd -f -
'''