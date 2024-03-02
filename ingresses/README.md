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


