# GitOps ArgoCD Demo

Configures ArgoCD and deploys a random demo app

# Overview

You need a Kubernetes cluster and you need to install ArgoCD on it under the namespace `argocd`.  
Once you have done that, you have to `k apply -f` all the files in the `argocd/` folder.  
To login to the ArgoCD UI you have to port-forward to `argocd-server` using `k port-forward svc/argocd-server 80:<whatever_you_like> -n argocd`  