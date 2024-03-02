
# Deployment
```
A Kubernetes deployment is a set of files defining how an application or microservices are deployed in a Kubernetes cluster. These files, known as deployment files, are used by developers and administrators to manage the application lifecycle within Kubernetes. They specify the desired state of the deployment, including pod replicas, container images, resource limits, and update strategies like rolling updates. In essence, Kubernetes deployments enable declarative application management, scaling, and rolling updates.
```

## example -> deployment.yml
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
```
A Kubernetes service is a configuration file that contains networking information. It defines how networking will be managed within the cluster, including enabling load balancing for applications, which is a premium feature of Kubernetes. The service file specifies the service's name, type (such as ClusterIP, NodePort, LoadBalancer), and selectors to route traffic to pods. Developers and administrators use service files to expose and connect applications within the Kubernetes cluster
```
## example -> service.yml
```
-apiVersion and Kind: Define the resource type
-metadata:: Specify the name of the service
-spec: Specify the desired state of the Service
-selector: Specifies on which pod the configurations will be invoked. If the pod labe matches by app value then it will apply the configuration on that pod
-port->protocol: Specifies the network protocol such as TCP, UDP, etc.
-ports: Specifies on which port the service listens for the incoming traffic from the external sources
-targetports: Specify on which port the pod is listening
```

### type
```
ClusterIP:
    -Purpose: This type of service exposes the service on an internal IP address, accessible only from within the cluster.
    -Operation: It allows communication between different components within the cluster but does not expose the service externally.
    -Usage: It's useful when you need to access the service only from other components within the cluster.

NodePort:
    -Purpose: This type of service exposes the service on a specific port of each node in the cluster.
    -Operation: It allows access to the service from outside the cluster using the node's IP address and the assigned port.
    -Usage: It's used when direct external access to the service is needed, but it's not ideal for production applications due to potential security and scalability issues.

LoadBalancer:
    -Purpose: This type of service exposes the service through an external load balancer that distributes traffic among various nodes in the cluster.
    -Operation: It provides a single external IP address that directs traffic to the service, distributing it among the cluster nodes to maintain high availability and scalability.
    -Usage: It's ideal for production applications requiring external access with high availability and automatic scalability.

In summary, each type of service in Kubernetes serves a specific purpose and provides different levels of access and exposure for services within the cluster.
```