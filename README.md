# Microservice-SMTP

![alt text](image/a1.png)
## Use Argo CD to deploy Microservice manifests
1. install Argo CD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/core-install.yaml
```
Check installed seccussful
```bash
kubectl get pod -n argocd
kubectl get svc -n argocd
```
access to Argo CD UI
```bash
kubectl port-forward -n argocd svc/argocd-server 8080:443
```
get pwd for Argo CD login
```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
echo <your-password> | base64 --decode
```
2. Configure ArgoCD with "Application" CRD





## Manually deploy Microservice manifests
```bash
kubectl apply -f kube-manifests/
