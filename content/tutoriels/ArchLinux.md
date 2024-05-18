+++
title="Instalé Arch Linux"
date=2024-01-06
draft=false
+++

# Installation d'Arch Linux : Guide Étape par Étape
Prérequis :

* Téléchargement de l'image ISO : Obtenez la dernière image ISO d'Arch Linux depuis le site officiel.
* Clé USB bootable : Utilisez une application comme Rufus (sous Windows) ou dd (sous Linux) pour créer une clé USB bootable avec l'image ISO.

## Étape 1 : Démarrage depuis la clé USB

Insérez la clé USB dans le PC et démarrez à partir de celle-ci.

## Étape 2 : Préparation du disque dur

Partitionnement : Utilisez des outils comme cfdisk ou parted pour partitionner le disque dur selon vos besoins. Créez au moins une partition racine (/) et une partition de swap si nécessaire.

Formatage : Formatez les partitions nouvellement créées avec des systèmes de fichiers appropriés (par exemple, ext4 pour la partition racine).

## Étape 3 : Installation du système de base

Montage des partitions : Montez la partition racine sur /mnt. Si vous avez créé d'autres partitions (comme /home), montez-les également.

Installation du système de base : Utilisez pacstrap pour installer les paquets de base. Par exemple : ```pacstrap /mnt base base-devel ```

## Étape 4 : Configuration du système

Fstab : Générez le fichier fstab avec ```genfstab -U /mnt >> /mnt/etc/fstab```

Chroot : Utilisez arch-chroot pour accéder à votre installation nouvellement créée : ```arch-chroot /mnt```

## Étape 5 : Configuration finale

Fuseau horaire : Configurez le fuseau horaire avec ```ln -sf /usr/share/zoneinfo/Region/Ville /etc/localtime ```

Langue : Décommentez la langue de votre choix dans /etc/locale.gen et exécutez locale-gen. Ensuite, créez le fichier /etc/locale.conf et définissez votre langue préférée.

Réseau : Définissez le nom d'hôte dans /etc/hostname et configurez le réseau. Assurez-vous d'installer un gestionnaire de réseau tel que NetworkManager.

Mot de passe root : Définissez le mot de passe root avec passwd.

## Étape 6 : Installation du chargeur d'amorçage

Installation de GRUB : Installez GRUB avec pacman -S grub et configurez-le avec grub-install --target=i386-pc /dev/sdX (remplacez sdX par votre disque) et ```grub-mkconfig -o /boot/grub/grub.cfg```

## Étape 7 : Fin de l'installation

Sortie du chroot : Quittez le chroot avec exit.

Redémarrage : Redémarrez votre système avec reboot.
