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
## Trouble shooting
