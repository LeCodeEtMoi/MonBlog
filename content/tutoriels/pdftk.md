+++
title="Manipuler les pdf avec pdftk"
date=2025-07-10
draft=false
+++

pdftk est un outils puissant pour manipuler les fichiers pdf

# Instalation

Pour archlinux
```sh
sudo pacman -S pdftk
```

Pour Ubuntu/Debian
```sh
sudo apt-get install pdftk
```

# Utilisation

- Fusionner des fichiers PDF

Pour fusionner plusieurs fichiers PDF en un seul, utilisez la commande cat :

```sh
pdftk fichier1.pdf fichier2.pdf fichier3.pdf cat output fichier_fusionne.pdf
```

- Diviser un fichier PDF

Pour diviser un fichier PDF en plusieurs fichiers, un par page, utilisez la commande burst :

```sh
pdftk fichier.pdf burst
```

Cela créera plusieurs fichiers nommés pg_0001.pdf, pg_0002.pdf, etc.

- Extraire des pages spécifiques

Pour extraire des pages spécifiques d'un fichier PDF, utilisez la commande cat avec les numéros de page 

```sh
pdftk fichier.pdf cat 1-5 output extrait.pdf
```
Cela extrait les pages 1 à 5 du fichier fichier.pdf et les sauvegarde dans extrait.pdf.

- Faire pivoter des pages

Pour faire pivoter des pages d'un fichier PDF, utilisez la commande cat avec les options de rotation :

```sh
pdftk fichier.pdf cat 1east 2-endsouth output fichier_rotate.pdf
```
Cela fait pivoter la première page de 90 degrés dans le sens horaire et les pages restantes de 180 degrés.

- Remplir un formulaire PDF

Pour remplir un formulaire PDF avec des données FDF, utilisez la commande fill_form :

```sh
pdftk formulaire.pdf fill_form données.fdf output formulaire_rempli.pdf
```

- Appliquer un filigrane

Pour appliquer un filigrane à un fichier PDF, utilisez la commande background :

```sh
pdftk fichier.pdf background filigrane.pdf output fichier_filigrane.pdf
```

- Chiffrer un fichier PDF

Pour chiffrer un fichier PDF avec un mot de passe, utilisez les options owner_pw et user_pw :

```sh
pdftk fichier.pdf output fichier_chiffre.pdf owner_pw motdepasse_proprietaire user_pw motdepasse_utilisateur
```

## Exemples avancés

- Coller des pages scannées

Pour coller des pages scannées en alternant les pages paires et impaires :

```sh
pdftk A=paires.pdf B=impaires.pdf shuffle A B output collé.pdf
```

- Décrypter un fichier PDF

Pour décrypter un fichier PDF, utilisez l'option input_pw :

```sh
pdftk sécurisé.pdf input_pw motdepasse output non_sécurisé.pdf
```

- Mettre à jour les métadonnées

Pour mettre à jour les métadonnées d'un fichier PDF, utilisez la commande update_info :

```sh
pdftk fichier.pdf update_info métadonnées.txt output fichier_misàjour.pdf
```

Pour plus d'information sur pdfkt

```sh
pdftk --help
```