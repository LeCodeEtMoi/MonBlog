+++
title="Debug Arch Linux"
date=2024-01-06
draft=false
+++

Si vous avez suivie cette config cette article peux vous être utiles [Installer Arch-Linux](/tutoriels/installation-archlinux/)

## Étape 1 : Allez sur en AndavoursOs

Voir tuto : [Mettre Endearvours sur sa clef](/tutoriels/endearvours/) 

## Étape 2 : Le shell

- Mettre le pc en azerty

```shell
setxkbmap fr
```

- Se mettre en root

```shell
sudo su
```

- Dechiffrer le premier disque

```shell
cryptsetup luksOpen /dev/nvme0n1p2 toto # Mettre autre chose que Arch-root car il peut rentrer en conflit avec le dossier Arch-root 
```

- Monter le 1ere disque 

```shell
mount /dev/mapper/Arch-root /mount
```

- Monter le 2eme disque 

```shell
mount /dev/mapper/nvme0n1p1 /mount/boot
```

- Si vous êtes pas bon endroit on se met à la racine ( fait le si vous en savez rien :) )

```shell
cd ~
```

- On change la racine du système de fichiers (chroot) vers le répertoire /mnt

```shell
arch-chroot /mnt
```

- On regle le probleme en réalisant souvant les mises à jours 

```shell
pacman -Suy
```

- Il se peut qu'il faut downdgrade un paquet , s'il le faut

```shell
downgrade example-pkg-1.0.0-1-x86_64.pkg.tar.xz
```

- On sort 

```shell
exit
```
- On demonte les disques  

```shell
umount -a # Il risque d'avoir des erreurs mais rien de grave
```

- On chiffre le disque 

```shell
 cryptsetup luksOpen /dev/nvme0n1p2 toto # toto fais refference à la 3eme commande lorsqu'on dechiffrer le disque
```









