# Kubernetes-Architecture
This repo is about Kubernetes, use cases of Kubernetes and architecture of kubernetes.
## What is Kubernetes?
Basially Kubernetes is a container orchestration platform.
## What is container?
A container is a package of code and its dependencies so that the application runs quickly and reliably from one environment to another.
## Why kubernetes?
Containers are great as they are light weight and using which an application can be run quickly and securely but using containers alone has few problems 
which by using  Kuberentes resoves them. They are:
1. Docker runs on a single host, and uses the resources from the underlying host. So if a container uses lots of memory then the other container might not get required memory to start the container and it dies. This can be solved by Kubernetes, by default kubernetes is a cluster(group of nodes). Kuberenetes follows master/node architecture.

2. In case container is killed,the application running inside is down. So there should be someone who should be monitoring and start the container. Kubernetes controls and fixes the damage, whenever Kubernetes API server receives a signal that a container ss going down it rolls out a new pod.

3. Auto scaling feature is missing in containers. Kubernetes has replica set. HPA(Horizontal Pod Autoscalar) using which whenever there is a load it spins up new pod.

4. Docker alone is not used in productionas it doesn't support enterprise level features. on the other hand kubernetes is a eneterprise level container orchestration platform which is used in production environments.

## Architecture of Kubernetes
Kubernetes is a cluster based architecture. In simple words kubernetes operates on Master and worker nodes.
In Kubernetes Master node is called "control plane", where as worker node is called "data plane".
on a high level control plane is like a command center and all the application run on worker nodes i.e data plane. Any requests to the worker nodes fo through control plane.

### Data plane
Data plane has three components, they are
1. kubelet: which is responsible for maintaing the pod.
2. container runtime: fundamental component which enables kubernetes to run containers effectively. Kuberenetes supports container runtimes like containerd, CRI-O etc.
3. kube-proxy: kube-proxy maintains network rules on pods, allow network communication to your pods from both inside and outside of your cluster.

### Control plane
1. kube-apiserver: The API server is a component of kubernetes control plane that exposes the kubernetes API. The API server is the front end for the kubernetes control plane.
2. kube-scheduler: control plane component that looks for newly created pods with no assigned node, and select a node for them to run on.
3. etcd: brain of the kubernetes cluster, used to backup all the cluster data in a key value store.
4. kube-controller-manager: control plane component that runs controller process.
   eg: Node controller: responsible for noticing and responding when node goes down
5. cloud-controller-manager: A kubernetes control plane component that embeds cloud-specific control logic.
   The cloud control manager only runs controllers that are specific to your cloud providers.

