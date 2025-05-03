+++
title="Créé un NAS avec un rasbery Pi"
date=2025-04-13
draft=false
+++

A réaliser quand j'aurai internet !

https://raspberry-pi.fr/connecter-ssh-raspberry-pi/


attetnion il faut avoir un os tout propre 

attient de fois il déja monter , il faut le demonter et il a peut besoin des droit admin : sudo rpi-imager


Choisir le lite 64 bit

mettre wifi (optionnel)

faire la connextion via ssh

Pour lister tout les process qui empeche de demonter : lsof | grep /run/media/Spike/rootfs

puis on : kill 	id


dans les paramètres 

Attention on peux avoir 2 adress ipsi connecter en ethernet et wifi 

pour rechercher les appreils conecter à la box : sudo nmap -sn 192.168.1.0/24

Ip via eternet : 192.168.1.118


##  Pas fini 