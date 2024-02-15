# Kubernetes-Architecture
This repo is about Kubernetes, use cases of Kubernetes and architecture of kubernetes.
## What is Kubernetes?
Basially Kubernetes is a container orchestration platform.
## What is container?
A container is a package of code and its dependencies so that the application runs quickly and reliably from one environment to another.
## Why kubernetes?
Containers are great as they are light weight and using which an application can be run quickly and securely but using containers alone has few problems 
which by using  Kuberentes resoves them. They are:
1. Docker runs on a single host, and uses the resources from the underlying host. So if a container uses lots of memory then the other container might not get required memory 
to start the container and it dies. This can be solved by Kubernetes, by default kubernetes is a cluster(group of nodes). Kuberenetes follows master/node architecture.

2. In case container is killed,the application running in it is down. So there should be someone who should be monitoring and start the container. Kubernetes controls and fixes the damage, whenever Kubernetes API server receives a signal that a container us going down it rolls out a new pod.

3. Auto scaling feature is missing in containers. Kubernetes has replica set. HPA(Horizontal Pod Autoscalar) using which whenever there is a load it spins up new pod.

4. Docker alone is not used in productionas it doesn't support enterprise level features. on the other hand kubernetes is a eneterprise level container orchestration platform which is used in production environments.

## Architecture of Kubernetes
Kubernetes is a cluster based architecture. In simple words kubernates operates on Master and worker nodes.
In Kubernetes Master node is called "control plane", where as worker node is called "data plane".
on a high level control plane is like a command center and all the application run on worker nodes i.e data plane. The requests go to worker nodes through control plane.

### Data plane
Data plane has three components, they are
1. kubelet: which is responsible for maintaing the pod.
2. container runtime: fundamental component which enables kubernetes to run containers effectively. Kuberenetes supports container runtimes like containerd, CRI-O etc.
3. kube-proxy: kube-proxy is responsible for networking like assign IP addresses to pods, allow network communication to your pods from both inside and outside of your cluster.

### Control plane



