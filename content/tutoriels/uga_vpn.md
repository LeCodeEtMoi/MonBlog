+++
title="Se connecter au serveur IUT 2 de l’Université Grenoble Alpes depuis Arch Linux"
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

- `-L 5900:localhost:5900` : tout ce qui arrive sur le port 5900 de votre machine sera redirigé vers le même port sur le serveur distant.

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

# Fonctionnement de scp

`scp` (Secure Copy) est l’utilitaire de copie sécurisée fourni avec le client OpenSSH.
Il permet de transférer des fichiers ou des répertoires entre votre poste local et une machine distante (ou entre deux machines distantes) en s’appuyant sur le protocole SSH. Le trafic est chiffré, donc vos données restent confidentielles.

```sh
scp [options] source destination
```


- **source**: chemin du fichier ou du répertoire que vous voulez copier.

- **destination**: où placer le(s) fichier(s). Peut être local (/chemin/local) ou distant (user@host:/chemin/distant).

- Si **source** et **destination** sont tous deux distants, le transfert passe par votre machine locale (c’est‑à‑dire “pull‑push”).

> Rappel : le caractère : sépare l’identifiant de la machine (user@host) du chemin distant.

## Options les plus courantes


| Option           | Signification                                                | Exemple d’usage                                      |
|------------------|---------------------------------------------------------------|------------------------------------------------------|
| `-r`             | Copie récursive (pour les répertoires).                       | `scp -r dossier/ user@host:/dest/`                   |
| `-P port`        | Port SSH non standard (note : majuscule).                     | `scp -P 2222 file.txt user@host:/dest/`              |
| `-p`             | Conserve les timestamps, modes et propriétaires.              | `scp -p file.txt user@host:/dest/`                   |
| `-C`             | Active la compression (utile pour les gros fichiers).         | `scp -C bigfile.iso user@host:/dest/`                |
| `-i identity_file`| Spécifie une clé privée différente du fichier `~/.ssh/id_rsa`. | `scp -i ~/.ssh/ma_cle user@host:/dest/`              |
| `-v`             | Mode verbeux – affiche les étapes de connexion (débogage).     | `scp -v file.txt user@host:/dest/`                   |
| `-q`             | Mode silencieux – supprime les messages d’avertissement.      | `scp -q file.txt user@host:/dest/`                   |
| `-l limit`       | Limite le débit en kilobits/s (ex. : `-l 500 = 500 kbps`).     | `scp -l 1000 file.txt user@host:/dest/`              |


##  Scénarios d’utilisation classiques

Copier un fichier de votre PC vers la VM

```sh
scp /chemin/local/fichier.txt  VOTRE_LOGIN@iut2-dg-transit.u-ga.fr:~/destination/
```

- `~/destination/` désigne le répertoire home de l’utilisateur distant.

Copier un fichier de la VM vers votre PC

```sh
scp VOTRE_LOGIN@iut2-dg-transit.u-ga.fr:/chemin/distant/fichier.txt  ./local/
```

- `./local/` est le répertoire courant sur votre machine.

Copier un répertoire entier (récursivement)

```sh
scp -r projet/ VOTRE_LOGIN@iut2-dg-transit.u-ga.fr:~/backup/
```

## Bonnes pratiques & pièges fréquents 

| Situation                           | Risque                                                            | Solution                                                      |
|-------------------------------------|-------------------------------------------------------------------|---------------------------------------------------------------|
| Oublier le `:` après `host`        | `scp` interprète tout comme un chemin local → erreur « no such file or directory ». | Toujours écrire `user@host:/chemin`.                           |
| Port SSH non‑standard              | Connexion refusée (par défaut 22).                                | Utiliser `-P <port>`.                                          |
| Fichiers volumineux sans compression| Transfert lent.                                                   | Ajouter `-C`.                                                  |
| Permissions locales perdues        | Le fichier distant hérite des permissions du serveur.             | Utiliser `-p` pour conserver timestamps et modes.              |
| Interruption du transfert          | Reprise impossible avec `scp`.                                    | Préférer `rsync -e ssh …` pour les gros transferts ou les reprises. |
