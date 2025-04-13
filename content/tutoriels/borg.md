+++
title="Réaliser une sauveguarde sur ArchLinux via Borg"
date=2025-04-13
draft=false
+++



Borg est un programme de sauvegarde par déduplication. En option, il prend en charge la compression et le chiffrement authentifié.

L'objectif principal de Borg est de fournir un moyen efficace et sûr de sauvegarder des données. La technique de déduplication des données utilisée rend Borg approprié pour les sauvegardes quotidiennes puisque seules les modifications sont stockées. La technique de chiffrement authentifié permet d'effectuer des sauvegardes vers des cibles qui ne sont pas entièrement fiables. 

Pour toutes les questions que le tuto ne repond pas voici la page du wiki d'archlinux : [ici](https://wiki.archlinux.org/title/Borg_backup_(Fran%C3%A7ais))

La documentation borg : [ici](https://borgbackup.readthedocs.io/en/stable/)


# Étape 0 : Instalation et mise en place

Installation borg: 

```sh
pacman -S borg
```

Il nous faudra un point de montage , crééons le maintenant (si pas déjà fait):

```sh
cd /mnt
mkdir nom_du_point_de_montage #Moi je l'ai appelé backup
```


# Étape 1 : Monter le disque dur 

On pbrache le disque dur , puis on reguarde ou est monter le disque 

```sh
lsblk
```

Vous devrez avoir un truc comme ceci , on peut voir qu'il est monter dans sda1

```sh
NAME            MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINTS
sda               8:0    0 931,5G  0 disk
└─sda1            8:1    0 931,5G  0 part  
nvme0n1         259:0    0 476,9G  0 disk
├─nvme0n1p1     259:1    0   128M  0 part  /boot
└─nvme0n1p2     259:2    0 476,8G  0 part
  └─cryptVol    254:0    0 476,8G  0 crypt
    ├─Arch-swap 254:1    0     2G  0 lvm   [SWAP]
    └─Arch-root 254:2    0 474,8G  0 lvm   /
```

Une fois qu'on a identifier le chemin du disque dure on va monter le disque

On fait alors la commande suivante

```sh
sudo mount chemin_du_disque_dure chemin_du_point_de_montage
```

Pour moi cela donne 
```sh
sudo mount /dev/sda1 /mnt/backup
```
# Étape 2 On verifie que on a bien monté le disque dure 

- Si vous avez déja réaliser un sauveguarde :

On est censé un dossier

```sh
ls /mnt/nom_du_point_de_montage
```
On fait donc ensuite

```sh
ls /mnt/nom_du_point_de_montage/le_nom_du_dossier
```

On est sensé avoir ceci 
```sh
config  data/  hints.859  index.859  integrity.859  README
```
- Si vous n'vez encore jamais réaliser de sauveguarde

```sh
borg init --encryption=repokey /mnt/nom_du_point_de_montage/nom_du_repo
```

# Étape 3 : Faire la sauveguarde 

L'étape la plus importe :)

Nous on va créé une archive avec un nom unique en lui donnant comme nom la date de quand elle a été réaliser :

```sh
borg create --compression lz4 --list /mnt/nom_du_point_de_montage/le_nom_du_dossier::archive-nom_d_utilisateur$(date +"%Y-%m-%d_%H-%M-%S") chemin_de_ou_part_la_sauveguarde
```
Plus le chemin part de la racine plus on archive de chose. Il est conseiller de prendre comme chemin : /home/nom_d_utilisateur

Quand la sauveguarde est fini ( c'est sensé être un peu long si vous avez des films ou beacoup de fichier :) ) nous pouvons passer à l'étape suivante 


# Étape 4 : Verifier que la sauveguarde a bien été réalisée


```sh
borg list /mnt/nom_du_point_de_montage/le_nom_du_dossier
```

Vous devriez voir toutes les archives réaliser ou qu'une seul si c'est votre première archives .

# Étape 5 : Démonter le disque proprement après sauvegarde

```sh
cd ~
sudo umount /mnt/nom_du_point_de_montage
```

Voilà vous avez fini votre sauveguarde 