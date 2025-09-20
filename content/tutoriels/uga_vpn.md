+++
title="Se connecter au serveur IUT 2 de l’Université Grenoble Alpes depuis Arch Linux
"
date=2025-09-20
draft=false
+++

>Prérequis
>- Un compte UGA (identifiant + mot de passe).
>- Une connexion Internet.
>- Les paquets suivants :  `openconnect`,`openssh`,(client SSH) et un client VNC (ex.`vinagre`, `remmina` ou `tigervnc`).

# 1 Installation des outils nécessaires

```sh
# Mettre à jour la base de paquets
sudo pacman -Sy

# Client VPN (OpenConnect)
sudo pacman -S openconnect

# Client SSH (fourni par le paquet openssh)
sudo pacman -S openssh

# Client VNC – choisissez celui que vous préférez
#   • Vinagre (GNOME)          sudo pacman -S vinagre
#   • Remmina (multi‑proto)    sudo pacman -S remmina remmina-plugin-vnc
#   • TigerVNC (léger)         sudo pacman -S tigervnc
```

> **Note** : openssh installe à la fois le client (ssh) et le serveur (sshd). Vous n’avez besoin que du client.

# 2 Connexion au VPN SSL

Ouvrez un terminal et lancez :

```sh
sudo openconnect vpn.grenet.fr
```

1. **Identifiant** : saisissez votre login UGA.
2. **Mot de passe** : entrez votre mot de passe.
3. **Choix du groupe** : électionnez le groupe qui correspond à votre statut (ex. `Etudiants UGA`).

> À la fin de la procédure vous devez voir un message similaire :

```sh
Connect Banner:
| Bienvenue aux etudiants de l'Universite Grenoble Alpes. |
| Votre session VPN SSL vous fournit un acces securise aux ressources numeriques de l'etablissement. |

Using vhost-net for tun acceleration, ring size 32
```

> **Astuce** : laissez le terminal ouvert tant que vous avez besoin du VPN. Le tunnel reste actif tant que le processus openconnect tourne.

# 3 Création du tunnel SSH (port 5900 → VNC)

Dans **un second terminal** (le VPN doit rester actif):

```sh
ssh -f -N -L 5900:localhost:5900 VOTRE_LOGIN@iut2-dg-transit.u-ga.fr
```

- `-f` : passe le client SSH en arrière‑plan après l’authentification.

- `-N` : ne lance aucune commande distante (on veut juste le tunnel).

- `-L 5900:localhost:5900` : out ce qui arrive sur le port 5900 de votre machine sera redirigé vers le même port sur le serveur distant.

> **Vous serez invité(e) à entrer votre mot de passe** du compte UGA (ou votre clé SSH si vous avez configuré l’authentification par clé).

>**Vérification** : le tunnel est actif si la commande suivante renvoie une écoute sur le port 5900

```sh
ss -ltnp | grep 5900
# ou
netstat -tlnp | grep 5900
```

# 4 Accès à l’interface graphique du serveur via VNC

Avec **Vinagre** (exemple)

```sh
vinagre &
```

- Dans la fenêtre qui s’ouvre, choisissez **«Connexion VNC»**.
- Adresse : `localhost:590`
- Cliquez sur «Connecter»

Avec **Remmina**

- Lancez : `remmina &`
- Nouveau -> Protocole:VNC.
- Adresse: `localhost:5900`
- Enregistrez et cliquer sur **Connecter**

Avec **TigerVNC**

```sh
vncviewer localhost:5900
```

> **Important** : le client VNC se connecte à localhost – le trafic passe par le tunnel SSH, qui lui‑même passe par le VPN. Vous êtes donc totalement isolé(e) du réseau public

# 5️ Nettoyage (fermer le tunnel et le VPN)

Lorsque vous avez terminé :

```sh
# Fermer le tunnel SSH
pkill -f "ssh -f -N -L 5900:localhost:5900"

# Fermer le client VPN
sudo killall openconnect
```



