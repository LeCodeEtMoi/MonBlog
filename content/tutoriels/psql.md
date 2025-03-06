+++
title = "PostgreSQL : Installation et Navigation"
date = 2025-03-05
draft = false
+++

Instalation sur arch Linux : 

```sh
sudo pacman -S postgresql
```

Demarer le service :
```sh
sudo systemctl start postgresql
```
Accéder à l'Environnement psql
```sh
sudo -i -u postgres
```
```sh
psql
```

## Commandes Pratiques pour Naviguer dans la Base de Données

Attention pour les commandes SQL ne pas oublier le ; à la fin !

Pour lister toutes les bases de donée

```sh
\l
```

Se Connecter à une Base de Données

```sh
\c nom_de_la_base
```
Lister les Tables

```sh
\dt
```
Lister les attributs de la table

```sh
\d nom_de_la_table
```
Lister tout les utilisateur

```sh
\du
```

Pour plus de commande

```
help
```

Créé un utilisateur 

```sh
CREATE USER nom_utilisateur WITH PASSWORD 'mot_de_passe';
```

Accorder des Privilèges :

```sh
GRANT ALL PRIVILEGES ON DATABASE nom_de_la_base TO nom_utilisateur;
```

Sauvegarder une Base de Données :
```sh
pg_dump nom_de_la_base > sauvegarde.sql
```



