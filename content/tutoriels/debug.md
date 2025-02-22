+++
title="Debug Arch Linux"
date=2024-01-06
draft=false
+++

Si vous avez suivie cette config cette article peux vous être utiles [Installer Arch-Linux](/tutoriels/installation-archlinux/)

## Étape 1 : Allez sur en AndavoursOs

- Booter la clef usb sur AndavoursOs

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

- Dechiffrer la premier partition du disque

Dans la partition LUKS tu as un containeur LVM qui contient 2 volumes dont un qui s'appelle Arch-root. Il faut pas que {nom} choisi qui va être mappé dans /dev/mapper soit le même

```shell
cryptsetup luksOpen /dev/nvme0n1p2 toto # Mettre autre chose que Arch-root
```

- Monter la 1ere partition disque 

```shell
mount /dev/mapper/Arch-root /mnt
```

- Monter la 2eme partition disque 

```shell
mount /dev/mapper/nvme0n1p1 /mount/boot
```

- Si vous êtes pas bon endroit on se met à la racine ( fait le si vous en savez rien :) )

```shell
cd /
```

- On bascule sur la racine du disque du PC pour se retrouver dans l'environnement du PC à réparer.

```shell
arch-chroot /mnt
```

- On regle le probleme en réalisant souvant les mises à jours 

```shell
pacman -Suy
```

- Il se peut qu'il faut downdgrade un paquet , s'il le faut

```shell
downgrade <paquet>
```

- On sort 

```shell
exit
```
- On demonte les partitions , c'est bien de vérifier que les partitions qui n'ont pas été démontées correspondent à celles de l'environnement live seulement et pas du disque du PC

```shell
umount -a # Il risque d'avoir des erreurs mais rien de grave
```

- On ferme la partition LUKS.

```shell
 cryptsetup luksOpen toto # toto fais refference à la 3eme commande lorsqu'on dechiffrer le disque
```







