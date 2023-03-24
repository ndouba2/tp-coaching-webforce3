# Mise place d'un serveur Web Flask

# EXERCICE LINUX
## Pre-requis
faire un
```
git clone https://github.com/crunchy-devops/tp-coaching-webforce3.git
```
sur la vm fournie

## Exercice 2
```shell
 sudo apt update   # mise a jour des references des repo
 sudo apt upgrade  # upgrade les packages et surtout les packages de securite
 sudo apt autoremove # enlever les packages inutiles
 python3 -V # la valeur affichee est Python 3.8.10
 ````
vi ~/.bashrc ajouter
 ```shell
 alias python='python3'
 ```
Verification
```shell
 source ~/.bashrc  # met a jour la session shell courante avec le nouvel bashrc
 python -V  # verification 
```
Installer python flask package
```shell
sudo apt -y install python3-pip 
pip install flask
```

## Exercice 3
See https://docs.fedoraproject.org/en-US/quick-docs/creating-a-disk-partition-in-linux/  
Utilisation de parted
```shell
sudo parted -l
sudo parted /dev/vdc
(parted) mklabel gpt
(parted) print
(parted) mkpart primary 0 1074MB
(parted) quit
lsblk -fe7  # -f filesystem -e exclude disk major 7 
sudo mkfs -t ext4 /dev/vdd1
mkdir /home/ubuntu/tp-coaching-webforce3/log
sudo mount /dev/vdc1 /home/ubuntu/tp-coaching-webforce3/log
sudo mount
sudo chown ubuntu:ubuntu log
lsblk -fe7
sudo vi /etc/fstab
# UUID=6a2ae8de-0d3f-4863-835b-7bd5091f09cc /home/ubuntu/tp-coaching-webforce3/log ext4 defaults 0 
sudo umount /home/ubuntu/tp-coaching-webforce3/log
sudo mount -av  # mount 
mount  # check 
```
### more on partition
```shell
#add more partition 
(parted) mkpart logical 1075 2048MB
```

## Exercice 6
Dans PyCharm allez dans File->Settings->Version control->github
Appuyer sur la croix, en haut a gauche de cette fenetre et selectionnez log in with token.
entrez votre token github
Vous pouvez faire des git commit et git push depuis PyCharm


## Exercice 5
vi blogs.py      
copier le code     
Ajouter la variable FLASK_APP=blogs dans le fichier ~/.profile

```shell
vi ~/.profile 
source ~/.profile
env | grep FLASK
```

ss -nlp

## Exercice 6
```shell
sudo ufw enable
sudo ufw allow ssh
sudo ufw allow 30101
sudo ufw deny 5000
flask run --host=0.0.0.0 -p 5000
sudo ufw allow 30101
sudo ufw deny 5000
sudo ufw allow 22
flask run --host=0.0.0.0 -p 5000
flask run --host=0.0.0.0 -p 30101
```

# EXERCICE ANSIBLE