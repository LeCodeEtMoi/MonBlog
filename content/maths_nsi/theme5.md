+++
title="NSI : Theme 5 : Les tableaux 2"
date=2024-01-06
draft=false
+++

**Rappel** Un tableau ( ou une liste) est une variable contenat plusieur variables , representée par une suite d'éléments séparés par des virgules , le tout étant entre crochet 

Liste = [13,12,9]

La longeur d'une liste est donnée par len(nom_de_la_liste)

len(Liste) = 3

Commen dans le première partie du cours l'instruction L2 = L1 copie dans la variable L2 le contenue de la variable L1 qui est l'adresse mémoire de la liste ( plus précisement , un poiteur). Tout modification de L1 entraîne une modification de L2 et vice versa . On peux coppier une liste en faisant L2 = list(L1)

## Quelques méthodes utils sur les listes : 

Il y a de nombreuse autre méthode. Avant de les utiliser , essayer de constuire vous meme une fonction qui fait la meme chose !  C'est méthodes ne concernet que les listes et s'utilisent de la manière suivante ( L conrespond a une liste :

- L.append(valeur) : ajoute l'élément unique élément à la fin de la liste
- L.pop() : enlève le dernier éléement et le renvoie ( à recupere dans une variable)
- L.remove(valeur) : supprime la première occurence de la valeur dans la liste

- L.min() : donne le minimum d'une liste . Il existe au L.max()

- L.insert(index,valeur) : insère valeur à l'indice index
- L.reverse() : inverse les éléments de la liste 
- L.count(valeur) : compte le nombre d'occurence de la valeur dans le liste et le renvoie
- L.index(valeur) : donne l'index de la première occurence de la valeur dans la liste

## 2 Construction d'un tableau par compréhension.

On peux construie un tableau plus rapidement que de partir d'un tableau videet de la compléter élément par élément. Pour cela, on insère une boucle "for" à l'interieur de la construction du tableau. On parle alors de la construction:

[f(x) for x in ITERABLE]

Nombres pairs de 0 à 20 : 

```[ 2* i for i in range(10)]```

[0,2,4,6,8,10,12,14,16,18]

[f(x) for x in ITERABLE if TEST]

Multiple de 3 pour 0 à 30
```[i* 3 for i in range(10) if i*3%2 == 0]```

[0,6,12,18,24]

```[j**2 for j in range(10,22,2)]```

[100,144,196,256,324,400]

un dernier exemple 

```[i* 3 for i in range(20) if (i * 3-1)%4==0]```

[8,20,32,44,56]

Exercice : Ecrire une instruction qui affecte 10 valeur aléatoire comprise entre 13 et 50(inclus) dans la liste

## 3 Matrices

Une matrice est un tableau de tableaux ( une liste de liste ) Chaque élément d'un tableau est alors un tableau C'est un tableau à plusieur colonnes

[image](https://www.google.com/url?sa=i&url=https%3A%2F%2Fpixees.fr%2Finformatiquelycee%2Fterm%2Fc9c.html&psig=AOvVaw13E0Faqo_-1hcRUMGowLOw&ust=1713359061958000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCJjpsoTmxoUDFQAAAAAdAAAAABAE)

L'élément a ij est à l'intersection de la linge d'indice i et de la colonne d'indice j. Pour des raisons de compatibilité avec la programmation en Python, dans ce cours on a débuté les indiceà 0. (En mathématique les indices commancent à 1)

Pour acceder à un élément , on met d'abord l'index de la ligne puis celui de la colone :

```
def affiche(mat):
	for i in range(len(mat)):
		print(mat[i])
mat = [[1,2],[3,4],[5,6]]
```
Pour ```mat[1]``` on a [3,4]

Pour ```mat[2][0]``` on a 5

Et enfin pour ```affiche(mat)``` on obtient :

[1,2]

[3,4]

[5,6]

Il est possible de parcourir l'ensemble des éléments d'une matrice à l'aide d'une double boucle for :

```
(nb_ligne,nb_colonne) = (3,2)
for i in range(nb_ligne):
	for j in range(nb_colonne):
		print(mat[i][j])
```
