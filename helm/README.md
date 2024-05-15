# Helm & Helm Charts

HELM is a package manager for Kubernetes applications. It helps in defining, installing, and managing Kubernetes applications. HELM uses charts, which are packages of pre-configured Kubernetes resources. These charts can be easily shared and version-controlled.

Imagine you're managing an application that comprises frontend, backend, and database components to deploy on Kubernetes. Deploying each of these components individually can be cumbersome, especially considering the stateful nature of the application. You'd need to create separate YAML files for each component and manage their deployment, which could quickly become complex. Enter Helm, an open-source package manager designed to simplify the deployment process for Kubernetes applications. With Helm, you can automate the deployment of your application components in a straightforward manner, streamlining the entire process.

![alt text](/images/helmvsk8s.png "helm vs k8s")

### Utils commands
```sh
helm search hub wordpress                   # search on Atifact Hub and list a lor of Helm charts of diferent repositories
helm search repo garrijuan                  # search in a particular repository
helm create app                             # Create a folder with different files, you should update deployment, service, ingress, notes... with your preferences and updated the values in the values.yml file
helm install hello-world bitnami/wordpress  # From artifact Hub, Two arguments are needed: a release name of your choice and the name of the chart you want to install. --generate-name generates random name for realease
helm install app ./app                      # From Local,deploy the k8s manifest in a cluster
helm status hello-world                     # Following of realease status or to read the configuration information again

#Custom a chart before the intallation
helm show values bitnami/wordpress          #Show options to configure a chart
#you can updater these configuration in a yaml file and include this file in the installation
echo '{mariadb.auth.database: user0db, mariadb.auth.username: user0}' > values.yaml
helm install -f values.yaml bitnami/wordpress --generate-name

--set: Especifique sobreescrituras en la línea de comando
    --set servers[0].port=80,servers[0].host=example
    #in YAML format:
    servers:
    - port: 80
        host: example

helm template mychart ./apppython             # Show all deployment
helm package apppython/                       # Package me chart in a .tgz
helm upgrade apppython ./apppython-0.1.0.tgz  # Package a new version of the chart
helm repo index --url https://github.com/garrijuan/app-python-CICD/blob/main/HELM/apppython/charts/ . # Generate or update the index of repository


helm repo add argo https://argoproj.github.io/argo-helm  # Add a chart to local environment
helm pull argo/argo-cd --version 5.8.2                   # update the chart to the new version, for instance ArcoCD chart
helm list 
helm repo list                                           # list all chart downloaded

helm uninstall apppython                                 # delete chart of cluster
```
More installation method:

- A charts repositoy(helm install hello-world bitnami/wordpress)

- From a local file of chart (helm install foo foo-0.1.1.tgz)

- From a local chart directory unzipped (helm install foo path/to/foo)

- From URL (helm install foo https://example.com/charts/foo-1.2.3.tgz)





