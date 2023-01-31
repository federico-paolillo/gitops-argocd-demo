# GitOps ArgoCD Demo

Configures ArgoCD and deploys a random demo app

# Overview

You need a Kubernetes cluster and you need to [install ArgoCD](https://argo-cd.readthedocs.io/en/stable/operator-manual/installation/#non-high-availability) on it under the namespace `argocd`.  
Once you have done that, you have to `k apply -f` the files `demo.project.yaml` and `demo.application.yaml` in the `argocd/` folder.  
To login to the ArgoCD UI you have to port-forward to `argocd-server` using `k port-forward svc/argocd-server 80:<whatever_you_like> -n argocd` as Argo is not exposed outside of the cluster.  

There is a `demoboy` user (along with `admin`) with some RBAC configured for it.  
To use `demoboy` you have to setup its password using `argocd account update-password --account demoboy --current-password <admin_user_password> --new-password <demoboy_password>` after loginning as `admin`.  

Recover the admin password by inspecting secret `argocd-initial-admin-secret` as explained [in the ArgoCD docs](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli).