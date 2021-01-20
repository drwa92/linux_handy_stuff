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
## SSH Key Generation 
open terminal/cygwin and type
```
ssh-keygen.exe
```
press enter for all answers

Copy the public key into the remote system
 ```
 scp .ssh/id_rsa.pub remote_user@IP:  e.g. (scp .ssh/id_rsa.pub muhayy@192.168.1.1:)
 ```
 the colon is important
 
Access the remote system using ssh with follwoing command

```
ssh remote_user@IP   e.g. (ssh muhayy@192.168.1.1)
```
## Permissions

|Command|	Meaning|
| :---: |:---: |
|chmod 400 file|	To protect a file against accidental overwriting.
|chmod 500 directory|	To protect yourself from accidentally removing, renaming or moving files from this directory.
|chmod 600 file	|A private file only changeable by the user who entered this command.
|chmod 644 file|	A publicly readable file that can only be changed by the issuing user.
|chmod 660 file	|Users belonging to your group can change this file, others don't have any access to it at all.
|chmod 700 file|	Protects a file against any access from other users, while the issuing user still has full access.
|chmod 755 directory|	For files that should be readable and executable by others, but only changeable by the issuing user.
|chmod 775 file	|Standard file sharing mode for a group.
|chmod 777 file|	Everybody can do everything to this file.
 
