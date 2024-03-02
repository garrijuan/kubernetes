# Kubernetes Ingress
Ingress is your friend to managing external traffic to services within the cluster. Before we dive into the details, let’s recap what we’ve learned so far. Before Ingress, the Service provides a Load balancer, which is used to distribute the traffic between multiple applications or pods.

Features:

Ingress helps to expose the HTTP and HTTPS routes from outside of the cluster.

Ingress enables Path-based and Host-based routing.

Ingress supports Load balancing and SSL termination.

**Explanation**

kubernetes Ingress is like a cop for your applications that are running on your Kubernetes cluster. It redirects the incoming requests to the right services based on the Web URL or path in the address.

Ingress provides the encryption feature and helps to balance the load of the applications.

In our words, Ingress is like a receptionist who provides the correct path for the hotel
room to the visitor.

**Why do we use Ingress because the load balancer supports the same thing?**

Ingress is used to manage the external traffic to the services within the cluster which
provides features like host-based routing, path-based routing, SSL termination, and more.
Where a Load balancer is used to manage the traffic but the load balancer does not provide
the fine-grained access control like Ingress.

**There are two types of Routing in Ingress**

-_Path-based routing_: Path-based routing directs traffic to the different services
based on the path such as example.com/app1
![alt text](/images/pathrouting.png "path routing")
-_Host-based routing_: Host-based routing directs traffic to the different services
based on the Website’s URL such as garrijuan.example.com.
![alt text](/images/hostrouting.png "host routing")


# example ingress
```sh
minikube start
minikube minikube addons enable ingress
kubectl apply -f ingress.yml
kubectl describe ingress
```
![alt text](/images/ingress.png "ingress")

In the next step, we will perform a 2e2 test of a simple API to ensure that we have communication through the Ingress. But first, we need to make a small preliminary configuration.

When using Minikube to run a Kubernetes cluster locally, you may need to configure your /etc/hosts file to enable access to the services you deploy in your cluster.


The main reason is that Minikube uses a virtual machine to run the Kubernetes cluster in your local environment. By default, services deployed in the cluster are not directly accessible from your host operating system. By configuring your /etc/hosts file, you assign hostnames to IP addresses within the Minikube virtual machine, allowing your host operating system to resolve those hostnames and redirect requests to the Kubernetes cluster.

```sh
minikube ip
sudo nano /etc/host #add minikube ip to the list
sudo cat /etc/host
```

We have applied deployment, service, and Ingress. Everything is up and running and ready to work. We make the following curl request and verify that it is correct. We also check it from the browser. A GET request is made against an API that returns the message 'Hello World'.

```sh
curl http://apppython
```
![alt text](/images/testingress.png "test ingress")
