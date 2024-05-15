# App of apps pattern

## Prereauisities

`brew install argocd`

## Usage

`argocd app create guestbook --repo https://github.com/argoproj/argocd-example-apps.git --path guestbook --dest-server https://kubernetes.default.svc --dest-namespace default`

## Services

### Wave 0: Core

* Vault

### Wave 1: Services

* CNPG Cluster
* Authentik
* Cert-manager

### Wave 2 (Application)

* n8n
* kube-prometheus-stack
* Kubernetes Dashboard
* Gitlab runners
