First of all we have to create a kubernetes cluster, in this case we have to create in Azure with AKS.
and we have to login into AKS via CLI with the following commands:

az aks get-credentials --name <aksclustername> --overwrite-existing --resource-group <resourcegroupname>

The following step that we have to do is the install and configuration ArgoCD

> you can follow the quickstart and install in this URL doc: https://argo-cd.readthedocs.io/en/stable/getting_started/

Commands:

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
once time installed you can see the pods with 

```
kubectl get pods -n argocd
```

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/fcb30388-64f7-45f0-ab97-32885d6a5ec7)

