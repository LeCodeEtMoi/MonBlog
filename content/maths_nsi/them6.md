+++
title="NSI : Theme 6"
date=2024-01-06
draft=false
+++

Rappel : Un tableau ( ou une liste ) est une variable contenant plusieur variables , représentée par une suite d'éléments séparés par des virgules , le tout étant entre des crochet.

La longueur d'une liste est donnée par len(nom_de_la_liste)

Comme dans <a href="./theme2.md">le Theme 2</a> l'instructionL2 = L1 copie dans la variable L2 le contenue de la variable L1 qui est l'adresse mémoire de la liste ( plus précisement , un pointeur) Tout modification de L1 entraine une modification de L2 et vice versa. On peux copier une liste en faisant L2=list(L1)

1. # Quelques méthodes utiles sur les listes : 

Il y a de nombreuse autre méthodes . Avant de les utiliser , essayer de construire vous meme une fonction qui fait la meme chose ! Ces méthodes ne concernet que les liste et s'utilise de la manière suivante : 

* L.appende(truc) : ajouter l'élément unique truc à la fin de la liste
* L.pop : enleve le dernier élément et le renvoie ( à récupere dans la variable)
* L.remove(valeur) : suprime la premère occurence de la valeur de la liste
* L.min() : donne le minimum de la liste . Il existe aussi L.max()
* L.reverse() : inverse les élément de la liste 
* L.count() : compte le nombre d'occurences de valeur dans la liste et le renvoie
* L.index(valeur) : donne l'index de la première occurence de la valeur dans la liste

1. # Construction d'un tableau par compréhension

On peut construire un tableau plus rapidement que de partir d'un tableau vide et de le completer élément par élément . Pour cela , on considère une boucle "for" à l'interieur de la construction du tableau . On parle alors de constuction par compréhension :

[F(x) for x in ITERABLE]

Nombre paire de 0 à 20 :

 [2*i for i in range(10)]

[0,2,4,6,8,10,12,14,16,18]

[F(x) for x in ITERABLE if TEST]

Multiple de 3 pour 0 à 30

[2*i for i in range(10) if i*3%2==0]

 [j**2 for i in range (10,22,2)]

[100,144,196,256,324,400]

 [i*3-1 for i in range(20) if (i*3-1)%4 == 0 ]

[8,20,32,44,56]

**Exercice :** Écrice une instruction qui affecte 10 valeur aléatoire comprise entre 13 et 50 (inclus) dans la liste

Réponce : [randint(13,50) for i in range(10)]

# 3 Matrices

Une matrice est une variable de tableau ( une liste de liste). Chaque éléments d'un tableau est alors un tableau . C'est un tableau à plusieur ligne et plusieur colonnes

L'lément est un ai,j est à l'intersection de la linge d'indice i et de la colonne d'indice j. Pour des raison de comptabilité avec la programation Python , dans ce cours on a débuté les indices à 0 .
(En Mathématique les indice commence à 1)

Pour accéder à un élément , on met d'abord l'index de la ligne puis celui de la colonne:
```
def affiche(not):<br>
    for i in range(len(mat)):<br>
        print(mat[i])
mat = [[1,2],[3,4],[5,6]]
```

mat[1] va donner [3,4]<br>
mat[2][0] va donner 5

affiche()mat va donner [1,2][3,4][5,6]

Il est possible de parcourir l'emsemble des éléments d'une matrice à l'aide d'une double boucle for:
