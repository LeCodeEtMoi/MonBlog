+++
title="Theme 7 : Les dictionnaires"
date=2024-01-06
draft=false
+++

# Qu'es qu'un dictionnaire ? 

En python , un dictionnaire est une collection de valeur . Cepednant , chauqe valeur d'un dictionnaiare est repérée par un nom ( appelé une clée ) plutôt que par un indice . Les données du ditionnaire sont modifiables, non ordonées. Chaque clé doit être uniques.

On peux créé un dictionnaire de plusieur manières :

Exemple = dict() créé un dictionnaire vide

Exemple = {} créé un dictionnaire vide

Exemple = {'pommes':5,"poires":6,"bananes":2} créé un dictionnaire contenant 3 cléees ('pommes','poir', et 'bananaes') associées respectivement au trois valeurs 5, 6 et 2 respectivements

# Manipulation d'un dictionnaire

Pour accéder au valeurs d'un dictionnaire on peux utiliser la meme syntaxe que pour les listes sauf que l'index est un mot de et non un nombre. On peux à l'aidede cette syntaxe , ajouter une nouvelle clef à tout moment 

Voici quelque exemple 

```

>>> panier = {'pommes':5,"poires":6,"bananes":2}


>>> panier 
{'pommes':5,"poires":6,"bananes":2}

>>> panier['pommes']
5

>>> panier['bananes'] = 5

>>> panier['bananes']
5

>>> panier
{'pommes':5,"poires":6,"bananes":5}

>>> panier['kiwi'] = 4

>>> panier
{'pommes':5,"poires":6,"bananes":2,'kiwi':4}

```

# Les commandes à connaitre 

[nom_du_dictionaire].pop('[la clef]') : comme pour un tableau cette instruction renvoie la valeur de la clé et supprime cette clé du dictionnaire

'[cle]' in panier : valeur booléenne qui est vraie si la clé donnée fait partie du dictionnaire, pratique pour éviter des erreus en tentant d'accéder à des clé inexistantes

# Parcourir un dictionnaire

Cela se fait grace à une boucle for . On peux parcourir les clefs du dictionnaire 

```
>>> for clef in panier:
		print(clef)

pommes
bananes
kiwi
```


ou les couples ( clef, valeur) grâce à la commande dictionnaire.items()

```
>>> for item in panier.items():
		print(item)

('pommes',5)
(bananes,5)
(kiwi,4)
```











