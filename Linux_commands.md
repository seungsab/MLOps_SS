## **1. `ls`: Command in Linux to list directories**
- `al`: Display all information about files in a directory, including owner, file size, and creation/modification date.
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt  test1.txt  test2.txt  test3.txt
(base) seungsab@SSWORKSTATION:~$ ls -l
total 12
drwxr-xr-x 28 seungsab seungsab 4096 Jul 13  2022 anaconda3
drwxr-xr-x  2 seungsab seungsab 4096 Jun 14 10:17 test
-rw-r--r--  1 seungsab seungsab   15 Jun 14 10:18 test.txt
-rw-r--r--  1 seungsab seungsab    0 Jun 14 10:22 test1.txt
-rw-r--r--  1 seungsab seungsab    0 Jun 14 10:22 test2.txt
-rw-r--r--  1 seungsab seungsab    0 Jun 14 10:22 test3.txt
(base) seungsab@SSWORKSTATION:~$ ls -al
total 60
drwxr-xr-x  8 seungsab seungsab 4096 Jun 14 10:22 .
drwxr-xr-x  3 root     root     4096 Jul 13  2022 ..
lrwxrwxrwx  1 seungsab seungsab   22 Jul 13  2022 .aws -> /mnt/c/Users/user/.aws
lrwxrwxrwx  1 seungsab seungsab   24 Jul 13  2022 .azure -> /mnt/c/Users/user/.azure
-rw-------  1 seungsab seungsab  867 Jul 13  2022 .bash_history
-rw-r--r--  1 seungsab seungsab  220 Jul 13  2022 .bash_logout
-rw-r--r--  1 seungsab seungsab 4258 Jul 13  2022 .bashrc
```

## **2. `pwd`: Command to print working directory**
```bash
(base) seungsab@SSWORKSTATION:~$ pwd
/home/seungsab
```

## **3. `cd`: Command to navigate through directories**
```bash
(base) seungsab@SSWORKSTATION:~$ cd anaconda3/
(base) seungsab@SSWORKSTATION:~/anaconda3$ cd ..
(base) seungsab@SSWORKSTATION:~$
```

## **4. `mkdir`: Command to create directories in Linux**
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3
(base) seungsab@SSWORKSTATION:~$ mkdir test
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test
```

## **5. `touch`: Command to Create blank/empty files**
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test
(base) seungsab@SSWORKSTATION:~$ touch test.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt
```

## **6. `mv`: Command to move or rename files in Linux**
```bash
(base) seungsab@SSWORKSTATION:~$ mv test.txt test1.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test1.txt
(base) seungsab@SSWORKSTATION:~$ mv test1.txt ./test/test1.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test
(base) seungsab@SSWORKSTATION:~$ cd test
(base) seungsab@SSWORKSTATION:~/test$ ls
test1.txt
```

## **7. `cp`: Command to copy files in Linux**
- `-R`: Copy all files in the subdirectories
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt
(base) seungsab@SSWORKSTATION:~$ cp test.txt test1.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt  test1.txt
(base) seungsab@SSWORKSTATION:~$ cp -R <Source directory> <Destination>
```

## **8. `rm`: Command to delete files or directories**
- `-r`: find and delete all files in the subdirectories
- `-f`: delete without asking for confirmation
- `-v`: display the deletion progress
- `-d`: delete directory if it is empty
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt  test1.txt
(base) seungsab@SSWORKSTATION:~$ rm test1.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt
(base) seungsab@SSWORKSTATION:~$ rm -v test.txt
removed 'test.txt'
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test
```

## **9. `cat`: Command to display file contents on the terminal**
- `cat > [FILENAME]`: write the input from standard input to a file
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test
(base) seungsab@SSWORKSTATION:~$ touch test.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt
(base) seungsab@SSWORKSTATION:~$ cat > test.txt
This is work~!
(base) seungsab@SSWORKSTATION:~$ cat test.txt
This is work~!
(base) seungsab@SSWORKSTATION:~$
```

## **10. `clear`: Command to clear the terminal display**
```bash
(base) seungsab@SSWORKSTATION:~$ clear
```

## **11. `tar`: Command to extract and compress files in Linux**
- `-cvf`: zip all files into tar-file
- `-xvf`: unzip all files into tar-file
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.txt  test1.txt  test2.txt  test3.txt
(base) seungsab@SSWORKSTATION:~$ tar -cvf test.tar test1.txt test2.txt test3.txt
test1.txt
test2.txt
test3.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.txt  test1.txt  test2.txt  test3.txt
(base) seungsab@SSWORKSTATION:~$ rm -f test1.txt test2.txt test3.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.txt
(base) seungsab@SSWORKSTATION:~$ tar -xvf test.tar
test1.txt
test2.txt
test3.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.txt  test1.txt  test2.txt  test3.txt
```
- `-zcvf`: zip all files into tar-gz-file
- `-zxvf`: unzip all files into tar-gz-file
```bash
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.txt  test1.txt  test2.txt  test3.txt
(base) seungsab@SSWORKSTATION:~$ tar -zcvf test.tar.gz test1.txt test2.txt test3.txt
test1.txt
test2.txt
test3.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.tar.gz  test.txt  test1.txt  test2.txt  test3.txt
(base) seungsab@SSWORKSTATION:~$ rm test1.txt test2.txt test3.txt
(base) seungsab@SSWORKSTATION:~$ ls
anaconda3  test  test.tar  test.tar.gz  test.txt
(base) seungsab@SSWORKSTATION:~$ tar -zxvf test.tar.gz
test1.txt
test2.txt
test3.txt
(base) seungsab@SSWORKSTATION:~$ ls -l
total 28
drwxr-xr-x 28 seungsab seungsab  4096 Jul 13  2022 anaconda3
drwxr-xr-x  2 seungsab seungsab  4096 Jun 14 10:17 test
-rw-r--r--  1 seungsab seungsab 10240 Jun 14 11:12 test.tar
-rw-r--r--  1 seungsab seungsab   145 Jun 14 11:14 test.tar.gz
-rw-r--r--  1 seungsab seungsab    15 Jun 14 10:18 test.txt
-rw-r--r--  1 seungsab seungsab     0 Jun 14 10:22 test1.txt
-rw-r--r--  1 seungsab seungsab     0 Jun 14 10:22 test2.txt
-rw-r--r--  1 seungsab seungsab     0 Jun 14 10:22 test3.txt
```

## **12. `grep`: Command to search for a string within an output**
```bash
(base) seungsab@SSWORKSTATION:~$ cat test.txt
This is work~!
(base) seungsab@SSWORKSTATION:~$ cat test.txt | grep 'This'
This is work~!
```

## **12. `df`: Command to display disk filesystem information**
```bash
(base) seungsab@SSWORKSTATION:~$ df
Filesystem      1K-blocks       Used Available Use% Mounted on
/dev/sdd        263174212    9063032 240673024   4% /
tmpfs            26201548          0  26201548   0% /mnt/wsl
/dev/sdc        263174212    1168776 248567280   1% /mnt/wsl/docker-desktop-data/isocache
none             26201548         16  26201532   1% /mnt/wsl/docker-desktop/shared-sockets/host-services
/dev/sdb        263174212     123624 249612432   1% /mnt/wsl/docker-desktop/docker-desktop-user-distro
/dev/loop0         371152     371152         0 100% /mnt/wsl/docker-desktop/cli-tools
tools           498916956  342114996 156801960  69% /init
none             26199464          0  26199464   0% /dev
none             26201548          8  26201540   1% /run
none             26201548          0  26201548   0% /run/lock
none             26201548          0  26201548   0% /run/shm
none             26201548          0  26201548   0% /run/user
tmpfs            26201548          0  26201548   0% /sys/fs/cgroup
C:\             498916956  342114996 156801960  69% /mnt/c
D:\            3907000316 3007936080 899064236  77% /mnt/d
```
