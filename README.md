# linux_handy_stuff
This repository contains the important and common to use shell commands for a quick reference.
## Copy directory from local to remote 
We can use secure copy (scp) with the recursive option (-r):
```
scp -r /path/to/local/dir user@remotehost:/path/to/remote/dir
```
## Copy directory from remote to local 
```
sudo scp -r user@remotehost:/path/to/remote/dir /path/to/local/dir
```
Alternatively
rsync because we can resume transfers if the connection breaks, and it intelligently transfers only the differences between files:
```
rsync -avz -e 'ssh' /path/to/local/dir user@remotehost:/path/to/remote/dir
rsync -avz -e 'ssh' user@remotehost:/path/to/remote/dir /path/to/local/dir 
```
