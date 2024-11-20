+++
title="Thème 7 : Les dictionnaires"
date=2024-01-06
draft=false
+++

# Qu'est-ce qu'un dictionnaire ? 

En Python, un dictionnaire est une collection de valeurs. Cependant, chaque valeur d'un dictionnaire est repérée par un nom (appelé une clé) plutôt que par un indice. Les données du dictionnaire sont modifiables et non ordonnées. Chaque clé doit être unique.

On peut créer un dictionnaire de plusieurs manières :

```python
Exemple = dict()  # Crée un dictionnaire vide

Exemple = {}  # Crée un dictionnaire vide

Exemple = {'pommes': 5, 'poires': 6, 'bananes': 2} 
```

Crée un dictionnaire contenant 3 clés ('pommes', 'poires' et 'bananes') associées respectivement aux valeurs 5, 6 et 2

## Manipulation d'un dictionnaire

Pour accéder aux valeurs d'un dictionnaire, on peut utiliser la même syntaxe que pour les listes, sauf que l'index est une clé (un mot) et non un nombre. Avec cette syntaxe, on peut également ajouter de nouvelles clés à tout moment.

Voici quelques exemples :
```python
>>> panier = {'pommes': 5, 'poires': 6, 'bananes': 2}

>>> panier
{'pommes': 5, 'poires': 6, 'bananes': 2}

>>> panier['pommes']
5

>>> panier['bananes'] = 5  # Modification d'une valeur existante

>>> panier['bananes']
5

>>> panier
{'pommes': 5, 'poires': 6, 'bananes': 5}

>>> panier['kiwi'] = 4  # Ajout d'une nouvelle clé

>>> panier
{'pommes': 5, 'poires': 6, 'bananes': 5, 'kiwi': 4}
```
## Les commandes à connaître

- ```[nom_du_dictionnaire].pop('[la clé]')``` : Comme pour une liste, cette instruction renvoie la valeur de la clé et supprime cette clé du dictionnaire.

- ```[clé] in panier ```: Renvoie une valeur booléenne qui est vraie si la clé donnée fait partie du dictionnaire. Cela permet d'éviter des erreurs lors de l'accès à des clés inexistantes.

## Parcourir un dictionnaire

Cela se fait grâce à une boucle for. On peut parcourir les clés du dictionnaire :

```python
>>> for clef in panier:
        print(clef)

pommes
poires
bananes
kiwi

```
Ou parcourir les couples (clé, valeur) grâce à la méthode ```dictionnaire.items()```
```python
>>> for item in panier.items():
        print(item)

('pommes', 5)
('poires', 6)
('bananes', 5)
('kiwi', 4)
```