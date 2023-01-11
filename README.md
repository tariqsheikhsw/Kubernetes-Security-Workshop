# Kubernetes-Security-Workshop

# SealedSecrets 



Command-line installer for windows 

```
https://scoop.sh/

scoop install kubectl

scoop install helm
scoop update helm

scoop search kubeseal

scoop info kubeseal

scoop install kubeseal
```

Check Versions

```
kubectl version --client 
```

```
$env:KUBECONFIG = "kubeconfig.yaml"

helm repo add sealed-secrets https://bitnami-labs.github.io/sealed-secrets

helm search repo sealed --versions 

helm install my-sealed-secrets -n kube-system --set-string fullnameOverride=sealed-secrets-controller sealed-secrets/sealed-secrets
```

GitHub
```
https://github.com/bitnami-labs/sealed-secrets
```

```
echo -n bar | kubectl create secret generic mysecret --dry-run=client --from-file=foo=/dev/stdin -o json >mysecret.json

kubectl logs deployment/sealed-secrets-controller -n kube-system 

kubectl edit deployment/sealed-secrets-controller -n kube-system
// under spec,containers,args 
// - --key-renew-period=45h

```






