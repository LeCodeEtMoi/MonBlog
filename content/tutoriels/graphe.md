+++
title = "Réaliser des graphique en python via matplotlib"
date = 2024-11-17
draft = false
+++

Nous allons voir ici comment on réaliser un graphique via [matplotlib](https://matplotlib.org/stable/) sans ce casser la tête dans la documentation .

Dans tout les exmple nous partirons sur les données fictives suivantes : annees = [
    2000,
    2001,
    2002,
    2003,
    2004,
    2005,
    2006,
    2007,
    2008,
    2009,
    2010,
    2011,
    2012,
    2013,
    2014,
    2015,
    2016,
    2017,
    2018,
    2019,
    2020,
]
temperatures = [14.5,14.8,15.0,15.2,15.4,15.6,15.9,16.1,16.3,16.5,16.7,16.8,17.0,17.2,17.5,17.8,18.0,18.3,18.5,18.7,19.0,]


# Sommaire
## Instalation
## Exemple pour tout les type de graphique
- Graphique en barres
- Graphique linéaire
- Graphique en aires
- Nuage de points
- Diagramme circulaire
- Pictogramme
- Graphique en colonnes
- Graphique à bulles
- Graphique en jauge
- Diagramme de Venn empilé
- Diagramme en mosaïque
- Diagramme de Gantt
- Diagramme en radar
- Diagramme en cascade
- Carte thermique
- Diagramme en entonnoir
- Diagramme de Pareto
- Graphique en barres empilées
- Organigramme
- Diagramme en boîte

## Mise en place concrettement via des données exterieur
- csv
- json

# Instalation

Inserer cette commande dans le shell 
```shell
pip install matplotlib
```

Tip : Si vous avez des problemes avec la librairie , l'installer dans un environnment virtuelle peux le regler 

# Graphique en barres

On va tout d'abors établire la taille du graphique en fonction ddu type de graphique la taille peux changer pour mieux voir les infos

```python
def GraphiqueLineaire(annees, temperatures):
	plt.figure(figsize=(10, 6))  # Taille du graphique
```

On va ensuite mettre les points on donne donc les 2 listes , une pour les absices et une autre pour les ordonées . Ensuite on peux ajouter un maker pour differience si on a plusieur courbe dans le meme graphque : 
Voici donc la liste 
## Points simples
- `.` : Point  
- `,` : Pixel  

## Cercles et disques
- `o` : Cercle  
- `O` : Cercle grand (non rempli dans certains cas)  

## Triangles
- `v` : Triangle vers le bas  
- `^` : Triangle vers le haut  
- `<` : Triangle vers la gauche  
- `>` : Triangle vers la droite  

## Carrés et losanges
- `s` : Carré  
- `D` : Losange  
- `d` : Petit losange  

## Étoiles
- `*` : Étoile  
- `p` : Pentagone  
- `h` : Hexagone régulier  

## Croix et plus
- `+` : Plus  
- `x` : Croix  
- `X` : Grande croix  

## Triangles penchés
- `1` : Triangle bas  
- `2` : Triangle haut  
- `3` : Triangle gauche  
- `4` : Triangle droit  

## Formes alternatives
- `|` : Ligne verticale  
- `_` : Ligne horizontale  

## Aucun marqueur
- `None`  

# Liste des couleurs (color)

## Couleurs de base (codes courts) :
- **b** : Bleu (blue)
- **g** : Vert (green)
- **r** : Rouge (red)
- **c** : Cyan
- **m** : Magenta
- **y** : Jaune (yellow)
- **k** : Noir (black)
- **w** : Blanc (white)

## Couleurs nommées (par nom) :
Exemples : "blue", "green", "red", "cyan", "magenta", "yellow", "black", "white"

## Codes hexadécimaux :
Exemple : "#FF5733" pour une couleur orange

## Niveaux de gris :
Utilisez une valeur entre "0.0" (noir) et "1.0" (blanc).
Exemple : "0.5" pour un gris moyen.

## Couleurs X11/CSS :
Exemples : "dodgerblue", "lightgreen", "salmon", "gold", "darkorchid"

## Couleurs dans les cartes de couleurs prédéfinies :
Exemple : `plt.cm.Blues(0.5)` pour une nuance de bleu dans la carte Blues.


```python
plt.plot(annees, temperatures, marker='o', color='b', label='Température annuelle')
```

ensuite on va ajouter cette ligne si on veux que la valeur des absices corespond au point 

```python
plt.xticks(annees, rotation=45) 
```
Ensuite on va etablire un titre pour le graphique puis pour les ordonées et les absices

```python
plt.title("Évolution de la température annuelle (2000-2020)")
plt.xlabel("Année")
plt.ylabel("Température (°C)")
``` 

On peut ajouter une grille pour mieux visualiser les graphiques et une legende pour comprendre a quoi corespond quel courbe 


```python
plt.grid(True)

plt.legend()
```

On peut mettre ceci pour éviter les chevauxchments 

```python
plt.tight_layout()
```

Et enfin on affiche le graphique

```python
plt.show()
```