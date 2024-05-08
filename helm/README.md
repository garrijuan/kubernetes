# Helm & Helm Charts

HELM is a package manager for Kubernetes applications. It helps in defining, installing, and managing Kubernetes applications. HELM uses charts, which are packages of pre-configured Kubernetes resources. These charts can be easily shared and version-controlled.

Imagine you're managing an application that comprises frontend, backend, and database components to deploy on Kubernetes. Deploying each of these components individually can be cumbersome, especially considering the stateful nature of the application. You'd need to create separate YAML files for each component and manage their deployment, which could quickly become complex. Enter Helm, an open-source package manager designed to simplify the deployment process for Kubernetes applications. With Helm, you can automate the deployment of your application components in a straightforward manner, streamlining the entire process.

![alt text](/images/helmvsk8s.png "helm vs k8s")

### Utils commands
```sh

helm create app # create a folder with different files, you should update deployment, service, ingress, notes... with your preferences and updated the values in the values.yml file

helm install app ./app # deploy the k8s manifest in a cluster 

helm template mychart ./apppython             # Show all deployment
helm package apppython/                       # Pakage me chart in a .tgz
helm upgrade apppython ./apppython-0.1.0.tgz  # Deploy the new package chart
helm repo index --url https://github.com/garrijuan/app-python-CICD/blob/main/HELM/apppython/charts/ . # Upload Chart on the artifactory repository


helm repo add argo https://argoproj.github.io/argo-helm  # Add a chart to local environment
helm pull argo/argo-cd --version 5.8.2                   # update the chart to the new version, for instance ArcoCD chart
helm list 
helm repo list # list all chart downloaded

helm uninstall apppython # delete chart of cluster
```