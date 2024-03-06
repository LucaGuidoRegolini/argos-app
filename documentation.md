# How Create a CD pipeline with ArgoCd

project based in the video [Deploy Contínuo com GitOps e ArgoCD](https://www.youtube.com/watch?v=4xmaOVul5Ww)

For te project is necessary the kind Kubernetes

--------------------
**For the Kind install**
> go install **sigs.k8s.io/kind@v0.22.0**

**For the Kustomize install**
> choco install kustomize

**Init Argo**
> kubectl create namespace argocd
>
> kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml


## Commands

> kind create cluster --name=argocd
>
> kubectl cluster-info --context kind-argocd
>
> docker build -t lucagregolini/argocd-fullcycle:lastest .
>
> docker push lucagregolini/argocd-fullcycle:lastest 
>
> docker run --rm -p 8080:8080 lucagregolini/argocd-fullcycle:lastest
>
> kubectl apply -f k8s/deployment.yaml
>
>  kubectl apply -f k8s/service.yaml
>
> kustomize build **in folder k8s**
>
> kubectl port-forward svc/argocd-server -n argocd 8080:443
>
> argocd admin initial-password -n argocd



The name of image is **lucagregolini**/argocd-fullcycle

is necessary create a token in docker hub and add in github secrets


### Utils

> kubectl get nodes
List nodes in the cluster selected by **kubectl cluster-info --context _context-name_**

> kubectl get pods
List the pods in the cluster

> kubectl port-forward svc/go-argos-app 8080:8080
Explain the ports map
