
**Mounting the remote directory to local system in Ubuntu**
===========================================================

Solution: Use SSHFS

*Step-1:*  **Install SSHFS**
```
sudo apt-get install sshfs
```

*Step-2:*  **Mount the remote directory**
```
$ sshfs  user@host:/remote_directory  /local_directory
```
Try to mount the remote directory inside anyfolder in /mnt folder and then create a link to this folder. 
Example:
```
$ sudo mkdir /mnt/remote
$ sudo chown rahul:rahul /mnt/remote
$ sshfs  rahul@172.27.26.231:/home/rahul/language  /mnt/remote
$ ln -s /mnt/remote  <path_where_to_pat_link>
```

Incase you need to unmount the remote directory that is mounted in /mnt/remote

*Step-3:*  **Unmount the remote directory**
```
$ fusermount -u /mnt/remote
```


