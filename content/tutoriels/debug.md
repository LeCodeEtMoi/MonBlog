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

```sh
setxkbmap fr
```

- Se mettre en root

```sh
sudo su
```

- Dechiffrer la premier partition du disque

Dans la partition LUKS tu as un containeur LVM qui contient 2 volumes dont un qui s'appelle Arch-root. Il faut pas que {nom} choisi qui va être mappé dans /dev/mapper soit le même

```sh
cryptsetup luksOpen /dev/nvme0n1p2 toto # Mettre autre chose que Arch-root
```

- Monter la 1ere partition disque 

```sh
mount /dev/mapper/Arch-root /mnt
```

- Monter la 2eme partition disque 

```sh
mount /dev/mapper/nvme0n1p1 /mount/boot
```

- Si vous êtes pas bon endroit on se met à la racine ( fait le si vous en savez rien :) )

```sh
cd /
```

- On bascule sur la racine du disque du PC pour se retrouver dans l'environnement du PC à réparer.

```sh
arch-chroot /mnt
```

- On regle le probleme en réalisant souvant les mises à jours 

```sh
pacman -Suy
```

- Il se peut qu'il faut downdgrade un paquet , s'il le faut

```sh
downgrade <paquet>
```

- On sort 

```sh
exit
```
- On demonte les partitions , c'est bien de vérifier que les partitions qui n'ont pas été démontées correspondent à celles de l'environnement live seulement et pas du disque du PC

```sh
umount -a # Il risque d'avoir des erreurs mais rien de grave
```

- On ferme la partition LUKS.

```sh
 cryptsetup luksOpen toto # toto fais refference à la 3eme commande lorsqu'on dechiffrer le disque
```







