# ARGOCD

## Installation

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Exposing

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## Login 

```bash
argocd admin initial-password -n argocd
```

Use password on the following command:

```bash
argocd login localhost:8080 --insecure
```

## Creating apps

```bash
argocd app create all-apps -f root-argocd-app.yaml
```