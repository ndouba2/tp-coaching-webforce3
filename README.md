# tp-coaching-webforce3
Instruction pour la session de coaching
# tp-coaching-webforce3
Instruction pour la session de coaching
https://app.clickup.com/9003054650/v/li/900300883869



ubuntu@coaching-11:~$ python3 --version
Python 3.8.10


ubuntu@coaching-11:~$ nano .bashrc
ubuntu@coaching-11:~$ source .bashrc
ubuntu@coaching-11:~$ python -V
Python 3.8.10

root@coaching-11:~# python3 -V
Python 3.8.10

root@coaching-11:~# lsblk -fe7 -o +size
NAME    FSTYPE LABEL           UUID                                 FSAVAIL FSUSE% MOUNTPOINT  SIZE
vda                                                                                             35G
├─vda1  ext4   cloudimg-rootfs 610a7297-2bb1-43e0-af45-2cab169e5a54     31G     8% /          34.9G
├─vda14                                                                                          4M
└─vda15 vfat   UEFI            6FDE-C9AD                              98.3M     6% /boot/efi   106M
vdb     swap                   02f5c556-c2f0-4d48-8124-15bd1fef14b9                [SWAP]        2G
vdc                                                                                              1G

root@coaching-11:/home/ubuntu/tp-coaching-webforce3# mkfs.ext4 /dev/vdc
mke2fs 1.45.5 (07-Jan-2020)
Creating filesystem with 262144 4k blocks and 65536 inodes
Filesystem UUID: c612f49f-aa7f-4778-b391-ae16132ce781
Superblock backups stored on blocks:
        32768, 98304, 163840, 229376

Allocating group tables: done
Writing inode tables: done
Creating journal (8192 blocks): done
Writing superblocks and filesystem accounting information: done


root@coaching-11:/home/ubuntu/tp-coaching-webforce3# mount -t ext4 /dev/vdc
mount: /dev/vdc: can't find in /etc/fstab.
root@coaching-11:/home/ubuntu/tp-coaching-webforce3# mount -t ext4 /dev/vdc /home/ubuntu/tp-coaching-webforce3/log
root@coaching-11:/home/ubuntu/tp-coaching-webforce3#

ubuntu@coaching-11:~/tp-coaching-webforce3/log$ ll
total 24
drwxr-xr-x 3 root   root    4096 Feb 23 22:20 ./
drwxrwxr-x 5 ubuntu ubuntu  4096 Feb 23 22:31 ../
drwx------ 2 root   root   16384 Feb 23 22:20 lost+found/


# enable programmable completion features (you don't need to enable
# this, if it's already enabled in /etc/bash.bashrc and /etc/profile
# sources /etc/bash.bashrc).
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi



alias python='python3'

export FLASK_APP=blogs




