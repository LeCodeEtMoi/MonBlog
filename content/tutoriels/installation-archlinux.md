+++
title="Installation Arch Linux"
date=2024-01-06
draft=false
+++

# Guide complet

## Materiels
- 2 clefs usb
- Un appraille autre que celui ou vous voulez intalez Arch Linux pour lire ce tuto ( de preference un Ordinateur)


# 1) Créé la clef bootable

## a) Recuperer Endavours
On va allez recupper ISO de [Endeavours](https://endeavouros.com/#Download) .
Pourquoi Endeavours ?
Endeavours est une distribution Linux légère et portable, ce qui signifie qu'elle peut être exécutée directement à partir de la clé USB sans avoir besoin de l'installer sur un ordinateur. Cela permet une grande flexibilité, car vous pouvez utiliser Endeavours sur n'importe quel ordinateur compatible sans modifier le système existant.

## b) Intaller Rufus
Il nous faut rendre notre clef bootable pour cella nous allons Installé Rufus.**Attention** rend la lef bootable va tout supprimé ce qu'il y a dedans il faut donc soit prendre un clef vierge soit ,sauveguarde ses documents !
Une fois l'ISO recupperer il faut installé [Rufus](https://rufus.ie/fr/) et puis l'executer et suivre les étapes suivantes:
### I Formatage
Dans **Periferique** vous mettez votre clef usb<br> **Type de démarage** Image disque ou ISO et vous selctectionne l'ISO que vous avez télécharger (Endavours)<br>
Pour le **Shema de la Partition** et **Système de destination**:
- GPT + UEFI (non CSM) : ordinateurs récents (PC UEFI) (2013)
- MBR + BIOS (ou UEFI-CSM) : ordinateurs anciens (PC BIOS) (< 2013)
- MBR + BIOS ou UEFI : tous les ordinateurs (dispo avec ISO Linux).
Cela depent donc de votre pc
### II Option de Formatage
**Nom du volume** : Vous pouvez laisser la valeur par default cela na pas vraiment d'importance<br>
**Systeme de fichier** : NTFS (requiert la désactivation du Secure Boot dans le BIOS) ou FAT32 (si disponible).<br>
**Taille d’unité d’allocation** : laisser la valeur par défaut.
### III Statut
Un fois tout bien configuré on clique sur le bouton **Pret**
Confirmez la création de la clé USB bootable en cliquant sur **OK**
Puis on attend que la clef devient bootable .
Il vous reste plus que a choisir l'option de base , il se peux que la clef ne marche pas alors refaite la partie **Intaller Rufus** et choisissez l'option DD.

## 2) Le BIOS

Demaré votre ordinateur et appuyer sur F2 le plus courament ou la touche Echap si l'une de ces deux touche lors du demarage ne fait pas apparaitre sur le BIOS allez chercher sur Internet :) . Ici on va en profite pour modifier le securboot si vous en avez choisis l'option **NTFS** .Puis nous allons allez modifier l'ordre des executions pour que sa soit la clef usb qui soit pris en charge premier .Inserer votre clef usb bootable .Et enfin après ces changements sur le BIOS on va enregister et redemarer .Si apres le redemarage , le pc ne tourne pas sur la clef refaite la partie **Intaller Rufus** et choisissez l'option DD.

## 3) Endearvours

Slectionne la première option et attendez un peu . Vous devez voir apparaitre petit a petit Endeavours. Il peut être utils de se connecter a internet et de mettre le clavier en azerty.

Deux solution s'offre a vous soit vous fait tout manuellements soit vous executer un scripte qui fait tout a votre place sachant qu'il va executer les meme commande que la solution à la mano


## Solution Scripte 

Une fois la configuration faite , nous allons utiliser la deuxieme clef usb . Pour gagner du temps j'ai réaliser un scripte que je vous invite a télécharger et mettre dans votre clef usb <a href="./Arch-Install.zip" download>ICI</a> <a download="Arch-Install.zip">Mdr</a>
si vous voulez suivre la suite du tutoriels. Mettre ici le lien du scirpte .


Pour une simple question de facilité copier coler le scipte dans document puis ouvrer le terminal et executer les commandes suivantent : 

> cd Documents

> chmod +x Arch-Install


Vous avez plus que a attandre que l'on vous demande de redemarrer (reboot)

## Solution à la mano

### Internet

Tout d'abors nous allons voir si on a internet 

``ping -q -c1 archlinux.org``

Si vous avez cette vous avez comme resultat c'est que vous avez internet: 


 ``PING archlinux.org (2a01:4f9:c010:6b1f::1) 56 octets de données
	--- statistiques ping archlinux.org ---
	1 paquets transmis, 1 reçus, 0% packet loss, time 0ms
	rtt min/avg/max/mdev = 48.744/48.744/48.744/0.000 ms``

Sinon va falloir vous connecter à internet et je sais plus comment on fais :p :

### Détection de l'UEFI et du SSD NVME 

efivar -l >/dev/null 2>&1
lsblk | grep -q "nvme"


### Mise en place des partitions :

``timedatectl set-ntp true``

Cette commande active la synchronisation de l'heure via NTP (Network Time Protocol). Cela permet à l'ordinateur de maintenir une heure précise en synchronisant son horloge avec des serveurs de temps sur Internet.


``pacman -Sy --noconfirm``

Ce commandement met à jour la base de données des paquets de pacman et synchronise les paquets locaux avec la version la plus récente disponible dans les dépôts. L'option --noconfirm est utilisée pour éviter les demandes de confirmation pendant le processus de mise à jour.

``sgdisk --zap-all /dev/nvme0n1``

Cette commande supprime toutes les partitions sur le périphérique spécifié (/dev/nvme0n1) en utilisant sgdisk, qui est un utilitaire de partitionnement pour les disques GPT (GUID Partition Table). Cela permet de nettoyer le disque avant de créer de nouvelles partitions.

``printf "n\n1\n4096\n+128M\nef00\nw\ny\n" | gdisk /dev/nvme0n1``

Cette série de commandes printf et gdisk est utilisée pour créer une nouvelle partition EFI (ESP - EFI System Partition) sur le disque spécifié. Cela crée une partition de 128 Mo à partir du secteur 4096 avec le type de partition EFI.

``printf "n\n2\n\n\n8e00\nw\ny\n" | gdisk /dev/nvme0n1``

Cette série de commandes printf et gdisk est utilisée pour créer une deuxième partition de type Linux LVM (Logical Volume Manager) sur le disque spécifié. La partition est créée en utilisant tout l'espace restant disponible sur le disque.

``mkfs.fat -F32 /dev/nvme0n1p1``

Cette commande formate la première partition (/dev/nvme0n1p1) avec le système de fichiers FAT32. Cette partition est généralement utilisée comme partition EFI (ESP) pour démarrer le système.

``printf "%s" "$encryption_passphrase" | cryptsetup --type luks2 -h sha512 --pbkdf argon2id --label LVMPART luksFormat /dev/nvme0n1p2``


Cette commande utilise cryptsetup pour formater la deuxième partition (/dev/nvme0n1p2) en tant que volume chiffré LUKS (Linux Unified Key Setup). Elle utilise l'algorithme de chiffrement AES-XTS-PLAIN64 avec le hachage SHA-512 et la fonction de dérivation de clé argon2id.

``printf "%s" "$encryption_passphrase" | cryptsetup luksOpen /dev/nvme0n1p2 cryptVol``

Cette commande ouvre le volume chiffré précédemment créé en fournissant la phrase de passe de chiffrement. Le volume chiffré est maintenant accessible sous le nom cryptVol.

Cette commande marque le périphérique /dev/mapper/cryptVol comme un nouveau volume physique pour être utilisé avec LVM (Logical Volume Manager).


``pvcreate /dev/mapper/cryptVol``

Cette commande marque le périphérique /dev/mapper/cryptVol comme un nouveau volume physique pour être utilisé avec LVM (Logical Volume Manager).

Cette commande crée un nouveau groupe de volumes appelé Arch en utilisant le volume physique /dev/mapper/cryptVol

``lvcreate -L +"$swap_size"GB Arch -n swap``

Cette commande crée un volume logique de swap nommé swap dans le groupe de volumes Arch. La taille du swap est définie par la variable $swap_size.


``lvcreate -l +100%FREE Arch -n root``

Cette commande crée un volume logique nommé root dans le groupe de volumes Arch, en utilisant tout l'espace restant disponible.

``mkswap /dev/mapper/Arch-swap``

Cette commande configure le volume logique Arch-swap en tant que partition de swap.

### Intallation de arch linux

``mkfs.ext4 /dev/mapper/Arch-root``

Cette commande formate le volume logique Arch-root avec le système de fichiers ext4. Cela prépare le volume pour être monté comme la partition racine du système de fichiers.

``mount /dev/mapper/Arch-root /mnt``

Cette commande monte le volume logique Arch-root sur le point de montage /mnt. Cela rend le contenu du volume accessible à partir de l'emplacement /mnt dans l'environnement actuel.

``mkdir /mnt/boot``

Cette commande crée un répertoire appelé boot dans le système de fichiers racine monté (/mnt). Ce répertoire servira de point de montage pour la partition EFI.

``mount /dev/nvme0n1p1 /mnt/boot``

Cette commande monte la partition EFI (/dev/nvme0n1p1) sur le répertoire /mnt/boot. Cela rend le contenu de la partition EFI accessible à partir du répertoire /boot dans le système de fichiers racine.

``swapon /dev/mapper/Arch-swap``

Cette commande active la partition de swap en utilisant le périphérique /dev/mapper/Arch-swap. Cela permet au système d'utiliser la partition de swap pour la gestion de la mémoire virtuelle.

### 

``arch-chroot /mnt /bin/bash``

Cette commande permet de changer l'environnement racine du système de fichiers vers /mnt, qui est le point de montage de la nouvelle installation d'Arch Linux. Cela permet d'exécuter des commandes comme si vous étiez dans le système installé plutôt que dans l'environnement live.

``ln -sf /usr/share/zoneinfo/$continent_city /etc/localtime``

Cette commande crée un lien symbolique entre le fichier de fuseau horaire spécifié (déterminé par les variables $continent_city) et /etc/localtime, ce qui configure le fuseau horaire du système.

``hwclock --systohc --localtime``

Cette commande synchronise l'horloge matérielle avec l'heure système actuelle. L'option --localtime indique que l'horloge matérielle est configurée pour être en temps local.

``echo "fr_FR.UTF-8 UTF-8" >> /etc/locale.gen``

Cette commande ajoute la configuration pour le jeu de caractères et l'encodage des caractères UTF-8 pour la localisation française dans le fichier /etc/locale.gen.

``echo "LANG=fr_FR.UTF-8" >> /etc/locale.conf``

Cette commande définit la variable d'environnement LANG pour spécifier la langue par défaut du système comme français avec l'encodage UTF-8. Cela configure la localisation du système.

``locale-gen``

Cette commande génère les fichiers de localisation spécifiés dans /etc/locale.gen. Cela met à jour les paramètres de localisation du système avec les nouvelles configurations.

``printf "KEYMAP=fr\n" >> /etc/vconsole.conf``

Cette commande configure la disposition du clavier par défaut en français en ajoutant la ligne KEYMAP=fr dans le fichier /etc/vconsole.conf.

``echo $hostname > /etc/hostname``

Cette commande définit le nom d'hôte du système en écrivant le contenu de la variable $hostname dans le fichier /etc/hostname.

``echo -en "$root_password\n$root_password" | passwd``

Cette commande change le mot de passe de l'utilisateur root en utilisant la syntaxe d'entrée standard echo. Le mot de passe est fourni deux fois pour confirmation.

``useradd -m -G wheel -s /bin/bash $user_name``

Cette commande crée un nouvel utilisateur avec le nom spécifié dans la variable $user_name. L'option -m crée un répertoire de base pour l'utilisateur, -G wheel ajoute l'utilisateur au groupe wheel, et -s /bin/bash définit le shell par défaut de l'utilisateur.

``echo -en "$root_password\n$root_password" | passwd $user_name``

Cette commande change le mot de passe de l'utilisateur spécifié ($user_name) en utilisant la syntaxe d'entrée standard echo. Le mot de passe est fourni deux fois pour confirmation.

``sed -i 's/^HOOKS.*/HOOKS=(base udev autodetect keyboard modconf block keymap encrypt lvm2 resume filesystems fsck)/' /etc/mkinitcpio.conf``

Cette commande modifie le fichier de configuration mkinitcpio.conf pour inclure les crochets nécessaires au processus d'initialisation. Cela spécifie les crochets à utiliser lors de la création de l'image initiale du noyau Linux.

``mkinitcpio -p linux``

Cette commande reconstruit l'image initiale du noyau Linux en utilisant les paramètres définis dans mkinitcpio.conf. Cela garantit que le système peut démarrer correctement avec le nouveau noyau.

``bootctl --path=/boot install``

Cette commande installe et configure systemd-boot comme chargeur d'amorçage. Cela configure le système pour démarrer à partir du fichier de configuration et des entrées de démarrage stockées dans /boot.

Continuer avec la configuration systemd-boot, etc.

``mkdir -p /boot/loader/``
``touch /boot/loader/loader.conf``
``tee -a /boot/loader/loader.conf << END``
``default arch``
``timeout 0``
``editor 0``
``END``

``mkdir -p /boot/loader/entries/``
``touch /boot/loader/entries/arch.conf``
``tee -a /boot/loader/entries/arch.conf << END``
``title ArchLinux``
``linux /vmlinuz-linux``
``initrd /$cpu_microcode.img``
``initrd /initramfs-linux.img``
``options cryptdevice=LABEL=LVMPART:cryptVol root=/dev/mapper/Arch-root resume=/dev/mapper/Arch-swap quiet rw``
``END``

``echo "Setting up Pacman hook for automatic systemd-boot updates"``
``mkdir -p /etc/pacman.d/hooks/``
``touch /etc/pacman.d/hooks/systemd-boot.hook``
``tee -a /etc/pacman.d/hooks/systemd-boot.hook << END``
``Type = Package``
``Operation = Upgrade``
``Target = systemd``

``[Action]``
``Description = Updating systemd-boot``
``When = PostTransaction``
``Exec = /usr/bin/bootctl update``
``END``

``echo "Enabling autologin"``
``mkdir -p  /etc/systemd/system/getty@tty1.service.d/``
``touch /etc/systemd/system/getty@tty1.service.d/override.conf``
``tee -a /etc/systemd/system/getty@tty1.service.d/override.conf << END``
``[Service]``
``ExecStart=``
``ExecStart=-/usr/bin/agetty --autologin $user_name --noclear %I $TERM``
``END``

``echo "Updating mirrors list"
``cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.BAK``
``reflector --latest 10 --age 12 --protocol https --sort rate --save /etc/pacman.d/mirrorlist``

``touch /etc/pacman.d/hooks/mirrors-update.hook``
``tee -a /etc/pacman.d/hooks/mirrors-update.hook << END``
``[Trigger]``
``Operation = Upgrade``
``Type = Package``
``Target = pacman-mirrorlist``

``[Action]
``Description = Updating pacman-mirrorlist with reflector``
``When = PostTransaction``
``Depends = reflector``
``Exec = /bin/sh -c "reflector --latest 10 --age 12 --protocol https --sort rate --save /etc/pacman.d/mirrorlist"``
``END

``echo "Enabling periodic TRIM"``
``systemctl enable fstrim.timer``

``echo "Enabling NetworkManager"``
``systemctl enable NetworkManager``

``echo "Enabling suspend (but no hibernate)"``
``sed -i 's/#HandleLidSwitch=suspend/HandleLidSwitch=suspend/g' /etc/systemd/logind.conf``

``echo "Adding user as a sudoer"``
``echo '%wheel ALL=(ALL) ALL' | EDITOR='tee -a' visudo``
``EOF``

``umount -R /mnt``
``swapoff -a``

``reboot``




## Arch Linux

Voila nous avons installé Arch Linux , bravo a vous c'est merveilleux.



