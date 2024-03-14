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

Now for the configuration we need to connect Argocd with Azure Repos

  1- Need get secrets
  
![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/880a679f-dfc9-481e-9dd0-1d49dc4bd8c2)

  ```
  kubectl edit secret argocd-initial-admin-secret -n argocd
  ```

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/c8896d65-7830-498d-a38c-593ca5848f10)

 and we take off the secret and decode with the following command

  ```
  echo ZkpZNU5vaXZELTFQb2FkcQ== | base64 --decode
  ```
  2- now we have to access to ArgoCD on the UI, changing the type of argocd-server from ClusterIP to NodePort to get the port
  
![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/5d1544dc-e32f-4eb1-8205-6282d9c44d6e)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/fe360ece-eaf1-4d8c-af50-c47f0fef252e)

  and get the External IP to have all data for access (ExternalIP:Port)
  
  
