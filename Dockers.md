## Environment
- OS: Ubuntu 20.04

## 1. Installation
**1) Update package manager using apt**
```bash
sudo apt-get update
```
**2) Install pre-requisite package for Docker**
```bash
sudo apt-get install apt-transport-https ca-certificates \
curl gnupg lsb-release
```
**3) Add GPG key of Docker**
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
**4) Set it to link the stable repository**
```bash
echo \
"deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] http
s://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /de
v/null
```
**5) Install Docker Engine**
```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
**6) Check Docker Installation using hello-world**
```bash
sudo docker run hello-world
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ sudo docker run hello-world

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
**7) Set Permission of Docker in Linux**
```bash
sudo usermod -a -G docker $USER
sudo service docker restart
```

## 2. Basic Commands of Docker
**1) Docker pull**
- Get(download) docker image from Docker image repository.
```bash
docker pull ubuntu:20.04
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker pull ubuntu:20.04
20.04: Pulling from library/ubuntu
ca1778b69356: Pull complete
Digest: sha256:db8bf6f4fb351aa7a26e27ba2686cf35a6a409f65603e59d4c203e58387dc6b3
Status: Downloaded newer image for ubuntu:20.04
docker.io/library/ubuntu:20.04
```
**2) Docker images**
- Print a list of docker images in the local.
```bash
docker images
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker images
REPOSITORY                    TAG       IMAGE ID       CREATED         SIZE
my-image                      v1.0.0    e6512da24f98   4 weeks ago     108MB
seungsab/my-image             v1.0.0    e6512da24f98   4 weeks ago     108MB
ubuntu                        20.04     88bd68917189   6 weeks ago     72.8MB
gcr.io/k8s-minikube/kicbase   v0.0.39   67a4b1138d2d   7 weeks ago     1.05GB
registry                      latest    8db46f9d7550   8 weeks ago     24.2MB
busybox                       latest    7cfbbec8963d   2 months ago    4.86MB
hello-world                   latest    feb5d9fea6a5   20 months ago   13.3kB
```
**3) Docker images**
- Print a list of docker images that are working in the local.
```bash
docker ps
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```
- Print a list of docker images that are working or have worked in the local.
```bash
docker ps -a
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker ps -a
CONTAINER ID   IMAGE         COMMAND    CREATED          STATUS                      PORTS     NAMES
fda4a142a7e5   hello-world   "/hello"   17 minutes ago   Exited (0) 17 minutes ago             compassionate_lehmann
```

**4) Docker run**
- Run Docker container
```bash
docker run -it --name demo1 ubuntu:20.04 /bin/bash
```
- `it`: `-i` option (interative) + `-t` option (terminal)
- `--name`: Define name to use it instead of container ID
- `/bin/bash`: Run a command simultaneously as a container runs (herein, `/ban/bash` => bash terminal)
- `-d`: After disconnecting a docker container, the docker container still run in the background
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker run -it --name demo1 ubuntu:20.04 /bin/bash
root@2830de517777:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@2830de517777:/#
```

**5) Docker exec**
- Make a command in a docker container or get access to a docker container 
- First, run a docker container in the background.
```bash
docker run -it -d --name demo_ss ubuntu:20.04
docker ps
```
- Then, we can access this container by the following command
```bash
docker exec -it demo_ss /bin/bash
```
> Output
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker run -it -d --name demo_ss ubuntu:20.04
14296930eaba535764f73959eb41978c14ab4d7d031d77e7b7cd2150fe699eed
seungsab@DESKTOP-9CD5Q7P:~$ docker ps
CONTAINER ID   IMAGE          COMMAND       CREATED         STATUS         PORTS     NAMES
14296930eaba   ubuntu:20.04   "/bin/bash"   5 seconds ago   Up 4 seconds             demo_ss
seungsab@DESKTOP-9CD5Q7P:~$ docker exec -it demo_ss /bin/bash
root@14296930eaba:/# ls
bin  boot  dev  etc  home  lib  lib32  lib64  libx32  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@14296930eaba:/#
```

## Trouble shooting
- OS Environment: Ubuntu 20.04

#### **1. [Running Issues] "Cannot connect to the Docker at unix"**
```bash
seungsab@DESKTOP-9CD5Q7P:~$ docker images
Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?
```
At first, you should check the status of Docker as below:
```bash
seungsab@DESKTOP-9CD5Q7P:~$ service docker status
* Docker is not running
```
If you get the message like the above, then type the below:
```bash
sudo service docker start
```
