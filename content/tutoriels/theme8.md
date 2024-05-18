+++
title="Theme 8 : IP et modèle des couches"
date=2024-01-06
draft=false
+++

Une adresse IP ( IP pour Internet Protocole) est un numéro d'identification qui est attribué de fçon permanete ou provisoire à chaque péréphirique rélié à un réseau informatique que utilise l'Iternet Protocol. L'adresse Ip est à la base du systeme d'acheminement (le routage) dans paquets de données sur Internet Il existe des adresse Ip de version 4 sur 32 bits 2³² soit 4 milliard et de version sur 128 bits 2¹28 soit 3,4 * 10³8 de machine.
La versione 4 est actuellement la plus utilisée : elle est généralement representée en notation décimale avec quatre nombres compris entre 0 et 255 , séparés par des points, ce qui donne par exemple "172.16.254.1".

Source : Wikipedia

##  Qu'est-ce que le protocole IP ?

Une fois que les donées ont été mise en forme ( découpées en paquet grace au protocole TCP ) , le protocole IP de prend le relai , il s'ccupe uniquement de faire arriver à destination les paquets en utilisant l'adresse de l'ordinateur de destination. Les adresse IP de l'ordinateur de départ ( ordinateur A) et de l'ordinateur de destination (ordinateur B) sont ajouteées aux paquets de donées 

On dit que le paquet IP a encapsulé le paquet TCP. Ces 2 protocoles sont tellement liés l'un à autre que l'on parle souvent du protocole TCP/IP

## Le modèle des couches TCP/IP

A chaque phase d'encapsulation on associe ce que l'on appelle une couche :

- Les protocoles HTTP, HTTPS , FTP, SMTP, DNS ... sont associès à la couche "Application" 

- Les protocoles TCP et UDP sont associès à la couche "Transport"

- Le protocole IP est associé à la couche "Internet"

- Les trames Ethernet ( ou Wifi) sont associées à la couche "Accès réseau"

La couche du "dessous" encapsule la couche située "au dessus"

