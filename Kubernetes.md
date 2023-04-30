## Environment
- OS: Ubuntu 20.04

## Installation Guide 
Before installing Kubernetes, vitrual tools like Docker should be installed in advance.
The minimum specs are at least above the follows:
- 2 CPUs or more
- 2GB of free memory
- 20GB of free disk space
- Internet connection
- Container or virtual machine manages such as Docker, Hyperkit or VMWare

Under Windows, [`Virtualization Support`](https://support.bluestacks.com/hc/en-us/articles/360058102252-How-to-enable-Virtualization-VT-on-Windows-10-for-BlueStacks-5) should be supported.

## **1. Let's install Minikube**  
1) Download the latest version of Minikube using curl, type as:
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 
```

2) Install downloaed file to local directory, type as:
```bash
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

3) if you are successful to install minikbue, you can get the message with the command of `minikube --help`.
```bash
seungsab@seungsab:~$ minikube --help
minikube provisions and manages local Kubernetes clusters optimized for development workflows.

Basic Commands:
  start            Starts a local Kubernetes cluster
  status           Gets the status of a local Kubernetes cluster
  stop             Stops a running local Kubernetes cluster
  delete           Deletes a local Kubernetes cluster
  dashboard        Access the Kubernetes dashboard running within the minikube cluster
  pause            pause Kubernetes
  unpause          unpause Kubernetes

***

Use "minikube <command> --help" for more information about a given command.
seungsab@seungsab:~$ minikube version
minikube version: v1.30.1
commit: 08896fd1dc362c097c925146c4a0d0dac715ace0
```

## **2. Let's install Kubectl**  
kubectl is a command-line tool that allows you to run commands against Kubernetes clusters
1) Download the latest release with the command:
```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
2) Install downloaed file to local directory, type as:
```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
3) Check success of installation with command of "kubectl --help"
```bash
seungsab@seungsab:~$ kubectl --help
kubectl controls the Kubernetes cluster manager.

 Find more information at: https://kubernetes.io/docs/reference/kubectl/

Basic Commands (Beginner):
  create          Create a resource from a file or from stdin
  expose          Take a replication controller, service, deployment or pod and expose it as a new Kubernetes service
  run             Run a particular image on the cluster
  set             Set specific features on objects

***

Use "kubectl <command> --help" for more information about a given command.
Use "kubectl options" for a list of global command-line options (applies to all commands).
```

## **3. Let's start Minikube**  
1) Let's start with docker-driver for running Minikube, type as:
```bash
minikube start --driver=docker
```

If you are successful, you can get the messages as:
```bash
seungsab@seungsab:~$ minikube start --driver=docker
😄  minikube v1.30.1 on Ubuntu 20.04
✨  Using the docker driver based on user configuration
📌  Using Docker driver with root privileges
👍  Starting control plane node minikube in cluster minikube
🚜  Pulling base image ...
💾  Downloading Kubernetes v1.26.3 preload ...
    > preloaded-images-k8s-v18-v1...:  397.02 MiB / 397.02 MiB  100.00% 51.81 M
    > gcr.io/k8s-minikube/kicbase...:  373.53 MiB / 373.53 MiB  100.00% 18.21 M
🔥  Creating docker container (CPUs=2, Memory=12800MB) ...
🐳  Preparing Kubernetes v1.26.3 on Docker 23.0.2 ...
    ▪ Generating certificates and keys ...
    ▪ Booting up control plane ...
    ▪ Configuring RBAC rules ...
🔗  Configuring bridge CNI (Container Networking Interface) ...
    ▪ Using image gcr.io/k8s-minikube/storage-provisioner:v5
🔎  Verifying Kubernetes components...
🌟  Enabled addons: default-storageclass, storage-provisioner
🏄  Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default
```

2) Then, check status of minikube and kubectrl as:
```bash
minikube status
```
```bash
kubectl version
```
```bash
kubectl get pod -n kube-system
```

```bash
seungsab@seungsab:~$ minikube status
minikube
type: Control Plane
host: Running
kubelet: Running
apiserver: Running
kubeconfig: Configured

seungsab@seungsab:~$ kubectl version
WARNING: This version information is deprecated and will be replaced with the output from kubectl version --short.  Use --output=yaml|json to get the full version.
Client Version: version.Info{Major:"1", Minor:"27", GitVersion:"v1.27.1", GitCommit:"4c9411232e10168d7b050c49a1b59f6df9d7ea4b", GitTreeState:"clean", BuildDate:"2023-04-14T13:21:19Z", GoVersion:"go1.20.3", Compiler:"gc", Platform:"linux/amd64"}
Kustomize Version: v5.0.1
Server Version: version.Info{Major:"1", Minor:"26", GitVersion:"v1.26.3", GitCommit:"9e644106593f3f4aa98f8a84b23db5fa378900bd", GitTreeState:"clean", BuildDate:"2023-03-15T13:33:12Z", GoVersion:"go1.19.7", Compiler:"gc", Platform:"linux/amd64"}

seungsab@seungsab:~$ kubectl get pod -n kube-system
NAME                               READY   STATUS    RESTARTS      AGE
coredns-787d4945fb-zh5cv           1/1     Running   0             23m
etcd-minikube                      1/1     Running   0             23m
kube-apiserver-minikube            1/1     Running   0             23m
kube-controller-manager-minikube   1/1     Running   0             23m
kube-proxy-zvntv                   1/1     Running   0             23m
kube-scheduler-minikube            1/1     Running   0             23m
storage-provisioner                1/1     Running   1 (22m ago)   23m
```


## Trouble shooting
