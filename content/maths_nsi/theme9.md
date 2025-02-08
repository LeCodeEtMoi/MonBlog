+++
title="NSI : Thème 9 : Rechereche dichotomique "
date=2024-01-06
draft=false
+++

Des volumes importants de données sont susceptibles d'être traitées par les ordinateurs. Des algorithmes efficaces sont alors nécessaires pour réaliser ces opérations comme par , exemple la sélection et la récupération des données. Les algorithmes de recherche entrent dans cette catégorie. Leur rôle est de déterminer si une donnée est présent et , le cas échéant , d'en indiquer sa position, pour effectuer des traitements annexes . La recherche d'un information dans un annuaire illustre cette idée. On recherche si telle personne est présente dans l'annuaireafin d'en déterniner l'adresse. Plus généralement , c'est l'un des mécanisme principaux des bases de données : à l'aide d'un identifiant , on souhaite retrouver les informations correspondantes. Dans cette famille d'algorithmes, la recherche dichotomique permet de traiter efficacement des données représentées dans une liste de façon ordonée .

### Problèmatique : Comment optimiser le recherche dans un tableau ordonée ?

## Première approche Rechèrche naive à l'aide d'un parcours de liste . 

Combien d'operations de comparaison doivent être effectuées au pire pour une lise n ? 

Réponse : n

Et pour une liste de taille 2n ?

Réponse : 2n

Commme tout algorithme ayant cette forme, la complexité est linaire : le temps de recherche double lorsque la longeur de la liste double . On note la complecité O(n) . Mais avec cette méthode , on n'exploite pas le charactère ordonée de la liste , ce qui fait savoir que valeur de la liste n'es pas la valeur recherchée n'apprend absolument rien sur les autre valeur de la liste .

## Seconde approche : Jeu du plus ou moins permettant de trouvé un nombre 

Avec un peu de méthode , en combien de est-on sur de déterminer la valeur recherchée ?

7 coups pour 100 valeurs ( 2⁶ = 64 / 2⁷ = 128)

Sans méthode en éssayant 1 puis 2 et en testant tout les autre valeurs , combien de coups faudrait -t-il au maximum ? 100 coups !

L'idée centrale de 2me approche repose sur l'idée de reduire de moitier l'espace de recherche à chaque étape : on reguarde la valeur du milieu et si ce n'es pas celle recherché , on sait que qu'il faut continué de chercher dans la première moitier ou dans la second . Plus préssisement , en tenant compte du caratère trié de la liste , il est posssible d'améliorer l'éfficaciter d'une telle recherche de faço conséquente en procédant ansi :

1) On détermine l'élement m au milieu de la liste ;

2) Si c'est la valeur recherchée , s'arrête avec un succès ;

3) Sinon , deux cas sont possible

- Si m est plus grand que la valeur recherchée , comme la liste est triée , cela signifie qu'il suffit de continuer à chercher dans la première moitier de la liste

- sinon , il suffit de chercher dans l'autre moitier.

4) on répète cela jusque avoir trouvé la valeur recherché , ou bien avoir réduit l'intervalle de recherche à un intevalle vide , ce qui signifie que la valeur recherchée n'es pas présente.

**À chaque étape , on coupe l'intervalle de recherche en deux et on en choisit une moitier . On dit que l'on possède par dichotomie , du grec dikha (en deux) et tomos ( couper)**

Entrée : tab une liste triée et valeur une valeur que l'on veux recherche dans la liste

Sortie : La valeur n'est pas dans tab sinon l'indice dans la valeur est dans le tableau

```
def recherche_dichotomique(tab,val):
	gauche = 0
	droite = len(tab)-1
	while(gauche+droite)//2
	if tab [milieu] == val:
		return
	elif tab[milieu] > val:
		droite = milieu -1
	else:
		gauche = milieu + 1
	return -1
```

Exemple d'application : On recherche la valeur 10 dans le tableau [3,3,5,6,8,11,13,14,14,17,19,21,23]

gauche = 0

milieu = 6

droite = 12

10 < 13

gauche = 0

milieu = 2

droitee = 5

10 > 5

gauche = 3

milieu = 4

droite = 5

10 < 11


## Terminaison de ce programme :

La fonction recherche_dichotomique contient une boucle non bornéee while et pour être sur de toujours obtenir un résultat , il faut s'assurer que le progrmme terminer , que l'on ne reste pas bloqué infiniment dans la boucle . Pour prouver que c'est bien le cas , nous allons utliser un variant de boucle.

**Variant de boucle**

Il s'agit d'une quantité entière qui :

- Doit être positive ou nulle pour rester dans la boucle

- Doit décroitre à chaque itération

Si l'on arrive a trouvé une telle quantité , il est évident que l'on a nécessairement sortie de la boucle au bout d'un nombre fini di'tération , puisqu'un entier positif ne peux décroitre infiniment.

Si l'on arrive trouver une telle quantité , il est évident que l'on a nessairement sortie de la boucle au bout d'un nombre fini d'operation , puisqu'un entier positif ne peux décroirtre indefiniment.

**Preuve de la terminiason**

Pour le cas qui nous occupe , un variant est très facile à trouvé : la quantité droite - gauche .
La condition de boucle étant gauche <= droite , cela correspond exactement à ce que notre variant soit positif ou nul .

Montrons maintenant que le variant décroit strictement lors de l'execution du corps de boucle .
On commence par définir : milieu = (gauche + droite)//2
ainsi gauche <= milieu <= droite
Ensuite trois cas sont possibles : 

- Si tab[milieu] == val : On sort de la boucle , terminson assuré 

- Si tab[milieu] > val : On modifie la valeur de droite . On appelle d cette nouvelle valeur : droite - gauche < milieu - gauche < droite - gauche

- Sinon , on modifie guache et a de même :

Droite - gauche < droite - ancien gauche .

Ayant réussis à exhiber un variant pour notre boucle , nous avons prouvé qu'elle se termine bien . Bien sur , l'utilisation très basique de ce variant ne permet pas de cette manière , de justifier la complexité de la recherche dichotomique . On a prouvé qu'il diminue de 1 ( au mions ) par étape , et on peux donc seulement affirmer que le nombre d'itération est majoré par la taille initiale de tableau . Cela correspond à la complexité linéaire de l'agorithme naif . On peux améliorer cette borne en exploitant l'idée de la dichotomie 