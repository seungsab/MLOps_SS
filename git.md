## Git
- OS Environment: Ubuntu:20.04

## 1. Installation
### 1) Update package manager using apt
- Update packages and intall git
```bash
sudo apt update
sudo apt install git
```
> Output
```bash
seungsab@DESKTOP-ALEHVET:~$ sudo apt install git
Reading package lists... Done
Building dependency tree
Reading state information... Done
Suggested packages:
  git-daemon-run | git-daemon-sysvinit git-doc git-el git-email git-gui gitk
  gitweb git-cvs git-mediawiki git-svn
The following packages will be upgraded:
  git
1 upgraded, 0 newly installed, 0 to remove and 18 not upgraded.
Need to get 4605 kB of archives.
After this operation, 258 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 git amd64 1:2.25.1-1ubuntu3.11 [4605 kB]
Fetched 4605 kB in 3s (1439 kB/s)
(Reading database ... 32685 files and directories currently installed.)
Preparing to unpack .../git_1%3a2.25.1-1ubuntu3.11_amd64.deb ...
Unpacking git (1:2.25.1-1ubuntu3.11) over (1:2.25.1-1ubuntu3.10) ...
Setting up git (1:2.25.1-1ubuntu3.11) ...
```

### 2) Update package manager using apt
- Check status of installation using printing out the git version 
```bash
git --version
```
> Output
```bash
seungsab@DESKTOP-ALEHVET:~$ git --version
git version 2.25.1
```

### 3) Configure Git
- Set username and E-mail
```bash
git config --global user.name "seungsab"
git config --global user.email "seungsab@gmail.com"
```
- Check modification of git config.
```bash
git config --list
```
> Output
```bash
seungsab@DESKTOP-ALEHVET:~$ git config --global user.name "seungsab"
seungsab@DESKTOP-ALEHVET:~$ git config --global user.email "seungsab@gmail.com"
seungsab@DESKTOP-ALEHVET:~$ git config --list
user.name=seungsab
user.email=seungsab@gmail.com
```
