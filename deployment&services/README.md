
# Deployment
```A Kubernetes deployment is a set of files defining how an application or microservices are deployed in a Kubernetes cluster. These files, known as deployment files, are used by developers and administrators to manage the application lifecycle within Kubernetes. They specify the desired state of the deployment, including pod replicas, container images, resource limits, and update strategies like rolling updates. In essence, Kubernetes deployments enable declarative application management, scaling, and rolling updates.```

### example -> deployment.yml
```
-apiVersion and Kind: Define the resource type
-metadata: Specify the details of deployment such as the name of the deployment and labels
-spec: Define the desired state of the deployment
-replicas: Specify the desired number of pods to maintain
-selector: Specifies on which pod the replica configuration should be applied with the help of the label of the pod
-templates: Describes the pod template and how deployment will use it to create new pods
-containers: List to containers to run within the pod
-name: Specifies the name oof container
-image: specifies the Docker Image name that will be used to run the container
```


# Service

