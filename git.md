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

## 2. Commands
### 1) git init
- git init command creates a new Git repository
```bash
git init
```
> Output
```bash
user@SSWORKSTATION MINGW64 ~/Desktop/test (master)
$ git init
Initialized empty Git repository in C:/Users/user/Desktop/test/.git/
```

### 2) git remote
- add a new remote repository
```bash
git remote add origin {REMOTE_URL}
```
> Output
```bash
user@SSWORKSTATION MINGW64 ~/Desktop/test (master)
$ git remote add origin https://github.com/seungsab/test.git
(base)
```

## 3. .gitignore
- ignore files and directories that are not tracked and uploaded to github
- Create file as ".gitignore"
```bash
user@SSWORKSTATION MINGW64 ~/Desktop/test (master)
$ touch .gitignore
```
- format for ".gitignore"
```text
  # ignore all .class files
*.class

# exclude lib.class from "*.class", meaning all lib.class are still tracked
!lib.class

# ignore all json files whose name begin with 'temp-'
temp-*.json

# only ignore the build.log file in current directory, not those in its subdirectories
/build.log

# specify a folder with slash in the end
# ignore all files in any directory named temp
temp/

# ignore doc/notes.txt, but not doc/server/arch.txt
bin/*.txt

# ignore all .pdf files in the doc/ directory and any of its subdirectories
# /** matches 0 or more directories
doc/**/*.pdf
```


## 4. Trouble shooting
### 1) merge  error when pulling git (git pull)
- error: Your local changes to the following files would be overwritten by merge
> Output
```bash
user@SSWORKSTATION MINGW64 ~/Desktop/Useful_tutorials (main)
$ git pull
remote: Enumerating objects: 270, done.
remote: Counting objects: 100% (22/22), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 270 (delta 11), reused 21 (delta 11), pack-reused 248
Receiving objects: 100% (270/270), 66.55 MiB | 5.03 MiB/s, done.
Resolving deltas: 100% (53/53), completed with 3 local objects.
From https://github.com/seungsab/Useful_tutorials
   ea26c98..4855844  main       -> origin/main
error: Your local changes to the following files would be overwritten by merge:
        Create_image_as_base64.ipynb
Please commit your changes or stash them before you merge.
Aborting
Updating ea26c98..4855844
```
> **Solution**
```diff 
-Git stash
```
```bash
git stash
```
> Output
```
user@SSWORKSTATION MINGW64 ~/Desktop/Useful_tutorials (main)
$ git stash
warning: in the working copy of 'Create_image_as_base64.ipynb', LF will be replaced by CRLF the next time Git touches it
Saved working directory and index state WIP on main: ea26c98 categorical tuto added
```

## Appendix
[Writing Github README](https://medium.com/analytics-vidhya/writing-github-readme-e593f278a796)
