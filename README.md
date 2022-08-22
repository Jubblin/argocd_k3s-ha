# argocd_k3s-ha

'''
helm repo add cilium https://helm.cilium.io/
helm repo update

helm upgrade cilium cilium/cilium --install \
  --version 1.12.1 \
  --namespace kube-system \
  -f cilium-values.yaml 
'''

'''
NAME=csi-driver-nfs NS=kube-system
echo $NAME $NS
helm upgrade ${NAME} ${NAME}/${NAME} \
    --install \
    --namespace=${NS} \
    --create-namespace

kubectl apply -f configs/nfs-sc.yaml
'''



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