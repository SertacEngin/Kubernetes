# Kubernetes
Kubernetes is the future. We need to understand Docker first to understand Kubernetes.
Kubernetes is a container orchestration platform.
Containers are ephemeral in nature. They have a short life cycle and then can revive anytime.
1- A problem with containers is that they have 1 single host. If a container uses to much resources, another container might not start just because of this.
2- Another problem is that if somenome kills one of our containers, the app running inside won’t be accessible. We can use auto healing. It is the automatic settings that starts the container without manual intervention. There are many reasons why a container can go down. We cannot do “docker ps” when we have 10,000 containers.
3- Another problem is auto scaling. The number of currently active user of our application can spike very quickly. Our app should adapt for this. Our load balancer takes care of this. It equally splits the traffic between our containers.
4. Antoher problem is that Docker is a minimalistic platform. Docker doesn’t provide any enterprise level support. For example Docker doesn’t support an application load balancer or a firewall. But for our application we need a load balancer, firewall, auto scaling, auto healing, and API gateway etc. These are Enterprise level standards. But docker doesn’t support these by default. 

We use Kubernetes to solve these problems. 
By default, Kubernetes is a cluster (a group of nodes).
Kubernetes is installed as a cluster. For example for our problem number 1, if a particular container is affected because some other container is consuming too much resource, Kubernetes will move this container to another node. Or if there is faulty node, Kubernetes will place the containers there in a different node. So Kubernetes works as a cluster in its nature.

Kubernetes is also good for auto scaling. It splits the traffic to healthy containers equally. We set this in YAML files. Kubernetes works with those files.

And for the health problem, Kubernetes controls or fixes the damage. If a container goes down, Kubernetes will start a new container. 

Docker is never used in production because it is not an enterprise level solution. Google created Kubernetes for enterprise level solutions and it is open source.
 We install it with the command “kops”.

Cluster = Collection of Nodes (servers or virtual machines).
Pod is the smallest level of deployment in Kubernetes.
Nodes run Pods, and Pods contain Containers.
Kubernetes controls which node gets which Pods.

Master Node (Control Plane)	Brain of Kubernetes, manages scheduling, scaling, health checks
Worker Node	Where containers run
Pod	Smallest unit, holds containers
Service	Exposes Pods to the network
Ingress	Manages external HTTP/HTTPS access
ConfigMap	Stores non-sensitive config data
Secret	Stores sensitive data (passwords, API keys)


