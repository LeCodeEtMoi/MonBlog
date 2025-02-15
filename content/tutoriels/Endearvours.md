+++
title="Mettre Endearvours sur une clef usb"
date=2024-01-06
draft=false
+++

 

## 1) Créé la clef bootable
### a) Recuperer Endavours

On va allez recupper ISO de Endeavours . Pourquoi Endeavours ? Endeavours est une distribution Linux légère et portable, ce qui signifie qu'elle peut être exécutée directement à partir de la clé USB sans avoir besoin de l'installer sur un ordinateur. Cela permet une grande flexibilité, car vous pouvez utiliser Endeavours sur n'importe quel ordinateur compatible sans modifier le système existant.
b) Intaller Rufus

Il nous faut rendre notre clef bootable pour cella nous allons Installé Rufus.Attention rend la lef bootable va tout supprimé ce qu'il y a dedans il faut donc soit prendre un clef vierge soit ,sauveguarde ses documents ! Une fois l'ISO recupperer il faut installé Rufus et puis l'executer et suivre les étapes suivantes:
I Formatage

Dans Periferique vous mettez votre clef usb
Type de démarage Image disque ou ISO et vous selctectionne l'ISO que vous avez télécharger (Endavours)
Pour le Shema de la Partition et Système de destination:

    GPT + UEFI (non CSM) : ordinateurs récents (PC UEFI) (2013)
    MBR + BIOS (ou UEFI-CSM) : ordinateurs anciens (PC BIOS) (< 2013)
    MBR + BIOS ou UEFI : tous les ordinateurs (dispo avec ISO Linux). Cela depent donc de votre pc

## II Option de Formatage

Nom du volume : Vous pouvez laisser la valeur par default cela na pas vraiment d'importance
Systeme de fichier : NTFS (requiert la désactivation du Secure Boot dans le BIOS) ou FAT32 (si disponible).
Taille d’unité d’allocation : laisser la valeur par défaut.
III Statut

Un fois tout bien configuré on clique sur le bouton Pret Confirmez la création de la clé USB bootable en cliquant sur OK Puis on attend que la clef devient bootable . Il vous reste plus que a choisir l'option de base , il se peux que la clef ne marche pas alors refaite la partie Intaller Rufus et choisissez l'option DD.

## 2) Le BIOS

Demaré votre ordinateur et appuyer sur F2 le plus courament ou la touche Echap si l'une de ces deux touche lors du demarage ne fait pas apparaitre sur le BIOS allez chercher sur Internet :) . Ici on va en profite pour modifier le securboot si vous en avez choisis l'option NTFS .Puis nous allons allez modifier l'ordre des executions pour que sa soit la clef usb qui soit pris en charge premier .Inserer votre clef usb bootable .Et enfin après ces changements sur le BIOS on va enregister et redemarer .Si apres le redemarage , le pc ne tourne pas sur la clef refaite la partie Intaller Rufus et choisissez l'option DD.

## 3) Endearvours

Slectionne la première option et attendez un peu . Vous devez voir apparaitre petit a petit Endeavours. Il peut être utils de se connecter a internet et de mettre le clavier en azerty.

Mettre le pc en azerty

```shell
setxkbmap fr
```








