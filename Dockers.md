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
