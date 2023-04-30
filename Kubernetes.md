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
1) Get latest version of Minikube using curl, type as
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 
```

2) Install downloaed file to local directory, type as
```bash
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

3) if you are successful to install minikbue, you can get the message as below by typing `minikube --help`.
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

Images Commands:
  docker-env       Provides instructions to point your terminal's docker-cli to the Docker Engine inside minikube.
(Useful for building docker images directly inside minikube)
  podman-env       Configure environment to use minikube's Podman service
  cache            Manage cache for images
  image            Manage images

Configuration and Management Commands:
  addons           Enable or disable a minikube addon
  config           Modify persistent configuration values
  profile          Get or list the current profiles (clusters)
  update-context   Update kubeconfig in case of an IP or port change

Networking and Connectivity Commands:
  service          Returns a URL to connect to a service
  tunnel           Connect to LoadBalancer services

Advanced Commands:
  mount            Mounts the specified directory into minikube
  ssh              Log into the minikube environment (for debugging)
  kubectl          Run a kubectl binary matching the cluster version
  node             Add, remove, or list additional nodes
  cp               Copy the specified file into minikube

Troubleshooting Commands:
  ssh-key          Retrieve the ssh identity key path of the specified node
  ssh-host         Retrieve the ssh host key of the specified node
  ip               Retrieves the IP address of the specified node
  logs             Returns logs to debug a local Kubernetes cluster
  update-check     Print current and latest version number
  version          Print the version of minikube
  options          Show a list of global command-line options (applies to all commands).

Other Commands:
  completion       Generate command completion for a shell
  license          Outputs the licenses of dependencies to a directory

Use "minikube <command> --help" for more information about a given command.
seungsab@seungsab:~$ minikube version
minikube version: v1.30.1
commit: 08896fd1dc362c097c925146c4a0d0dac715ace0
```

## **2. Let's install Kubectl**  
kubectl is a command-line tool that allows you to run commands against Kubernetes clusters
1) 
## Trouble shooting
