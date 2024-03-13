# AzureDevOpsCI-Proyect

First of all we have to create a new proyect

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/0a8e45c7-89a7-4e1a-bd9c-7b0f05fc9472)

Lets click on "Create Proyect"

Now we'll have to import all required files from a Voting App extern repository into Azure Repos

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/8f0c10c8-321b-465c-87d3-8264471de358)

Lets click on "Import" and paste the URL of the external repository

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/5da5f63c-4974-4d9e-87de-55de1f7e74c6)

Now you can see the Repository that we have imported

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/2dfb802e-fc26-4282-b4cd-87bec4a5c6aa)

Once imported , lets go to the Pipelines, and create a New Pipeline

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/755c67a1-5bc6-4cf3-aa7c-395669bbad02)

Now lets click on "Azure Repos Git" and choose the repository that was created before

![image](https://github.com/JooeeL98/AzureDevOps-Proyect/assets/145325906/dfe9c729-dce2-4bd2-adb4-32d25424267f)

On the configure step select the second option Docker, because we have to work with the container registry of Microsoft Azure, follow the image below

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/5a5034aa-8aea-4f14-98aa-1ae0ce385a86)

Once established connection with your microsoft azure acount, select the container registry and click on "Validate and configure"

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/f4efe44a-7240-41cb-8e73-c111a576fa9b)

In the Review section, we have to change the trigger and change also the file name, like the image below (This case for Result)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/45585b42-6fb0-4f82-baa3-af07720056ad)

Now you have to modified your yaml file depeds of your CI stages, the mines are attaches in this repository

then click on "Save and Run"

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/12fcfd6c-4be2-47e8-9a4c-df64a9d54f03)


Now if we have to trait with agent pools, we have to configure that like images below

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/344685ce-7a28-4f1d-b992-db5ff978173e)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/8c5b2f14-7609-44c3-aa54-08ef9dd5c54c)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/e4ce904c-e202-4519-bb7a-3cdb5b98f559)

you have to follow this 

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/db9711e4-69c2-475a-8ad6-220f151e4098)

also you can follow this site https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/linux-agent?view=azure-devops

Once we have a agent pool running we have to rerun the pipeline(if we haved this error)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/5a4cd224-d158-4872-915a-29b273e4570c)

if u had this error 

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/dede25a9-0e26-45f8-bfec-6daa61d3ba8a)

just restart the agent on CLI

And then, we have to do the same steps for each services, (vote and worker)

![image](https://github.com/JooeeL98/AzureDevOps-ArgoCD-Proyect/assets/145325906/36bfded1-4ce0-4e96-acc9-c1293527f538)

