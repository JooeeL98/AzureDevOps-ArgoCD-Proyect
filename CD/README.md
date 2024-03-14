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
  
And You can Access and get an interface like this

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/e9d70557-e5d0-493d-a9fe-c69807bcd2d7)

we login with username: admin and password: "pass that you decoded above steps"

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/1f0064e1-6c96-47b4-8de7-45cc109295b9)

Now we have to connect argocd with our Repos, for that we need to create a token and complete the connection with the repo in ArgoCD like that

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/f679e8c8-c610-4278-87c1-b7cf2d26ef10)

The We have to create a new aplication with the following data and click on the "Create" button

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/de1c5a89-816a-4bce-addd-11645904c2c6)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/3960fca4-8e9d-4075-8023-0d7e54d38240)

You can see the argo cd are deploying all manifest on the k8s

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/8f87b28e-07d4-4b52-abf9-f32e01613969)

Now we have to edit the pipelines yaml(file attached in this repository)




And dont forget have the script for update k8s(file attached in this repository)




