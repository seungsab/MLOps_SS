## Environment
- OS: Ubuntu 20.04

## Installation
**1. Update package manager using apt**
```bash
sudo apt-get update
```
**2. Install pre-requisite package for Docker**
```bash
sudo apt-get install apt-transport-https ca-certificates \
curl gnupg lsb-release
```
**3. Add GPG key of Docker**
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
**4. Set it to link the stable repository**
```bash
echo \
"deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] http
s://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /de
v/null
```
**5. Install Docker Engine**
```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
**6. Check Docker Installation using hello-world**
```bash
sudo docker run hello-world
```
If it is successful, the following message will be shown.
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
**7. Set Permission of Docker in Linux**
```bash
sudo usermod -a -G docker $USER
sudo service docker restart
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
