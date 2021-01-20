# linux_handy_stuff

This repository contains the important and common to use shell commands for a quick reference.
## Copy directory from local to remote 
We can use secure copy (scp) with the recursive option (-r):
```
sudo scp -r /path/to/local/dir user@remotehost:/path/to/remote/dir
sudo scp -r /home/muhay/Documents/scripts remote@1.1.1.1:/home
```
## Copy directory from remote to local 
```
sudo scp -r user@remotehost:/path/to/remote/dir /path/to/local/dir
sudo scp -r remote@1.1.1.1:/home/scripts /home/muhay/Documents

```
Alternatively
rsync because we can resume transfers if the connection breaks, and it intelligently transfers only the differences between files:
```
rsync -avz -e 'ssh' /path/to/local/dir user@remotehost:/path/to/remote/dir
rsync -avz -e 'ssh' user@remotehost:/path/to/remote/dir /path/to/local/dir 
```
## SSH Key Generation Windows 
open terminal/cygwin and type
```
ssh-keygen.exe
```
press enter for all answers

Copy the public key into the remote system
 ```
 scp .ssh/id_rsa.pub remote_user@IP: (192.168.1.1)
 ```
 the colon is important
 
