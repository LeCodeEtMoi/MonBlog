+++
title= "NSI : Theme 11: Codage des nombres a virgules"
date=2024-01-06
draft=false
+++


# Décomposition

En base 10, l'expression 652,375 est une manière abrègée d'écrire: 6 * 10² + 5 * 10¹ + 2 * 10⁰ + 3 * 10⁻¹ + 7 * 10⁻² + 5 * 10⁻³ .

On fait exactement la meme pareil pour la base 2 . Ainsi , l'expression 110,101 signifie : 1 * 2² + 1 * 2¹ + 0 * 2⁰ + 1 + 2⁻¹ + 0 * 2⁻² + 1 * 2 ⁻³

# Passer de la base 2 à la base 10 

Pour convertir un nombree réel de la base vers la base 10 , on ne décompose à l'aide de puissance de 2 avec des exposants positifs et négatifs . Par exemple : 110,101 = 1 * 2² + 1 * 2¹ + 0 * 2⁰ + 1 * 2⁻¹ + 0 * 2⁻² + 1 * 2⁻³ = 4 + 2+0,5+0,125 = 6,625

Exercice : converitr en base base 10 (101,101)2 = 1 * 2² + 0 * 2¹ + 1 * 2⁰ + 1 * 2⁻¹ 0 * 2⁻² + 1 * 2⁻³ = 1 * 2² +  1 * 2⁰ + 1 * 2⁻¹ + 1 * 2⁻³ = 4 + 1 + 0,5 + 0,125 = 5,625

# Passer de base 10 à base 2 

Le passage de base 10 en base 2 est plus subtil . Par exemple : convertissons 124.6875 en base 2 .

- La partie entière se transforme comme dans le [Theme 4](./tutoriels/theme4/) et donc (124)10 = (1111100)2

- On transforme la partie décimale selon le shéma suivant : on multiplie la partie fractionnaire par 2 et on note la partie entière de résultat . On recommence cette opération avec la partie fractionnaire du résultat . On continue ainsi jusqu'à ce qu'on obtienne 1 .

0,6875 * 2 = *1*,375
0,375 * 2 = *0*75
0,75 * 2 = *1*,5
0,5 * 2 = 1

Les parties entières ( 0 ou 1 ) des quatre résultats donne les chiffres après la virgule de l'écriture binaire de 0,6875: (0,6875)10 = (0,1011)2

Donc finalement, (124.6875)10 = (1111100,1011)2

Exercice : Convertire en binaire le 7,09375

Vous devez trouver le résultat 111,00011

Attention ! Un nombre à développement décimal fini en base 10 ne l'est pas forcément en base 2 ( exemple 1,2 ou 0,347)

# Écriture scientifique

L'écriture scientifique permet d'écrire un nombre sous la forme m * 10^n

Exemple : -398457,5 = -3,984575 * 10⁵ ou 0,000025 = 2,5 * 2,5 * 10⁻⁵

Nous allons pouvoir représentr des "nombres à virgule" écrit en base 2 , sous forme "scientifique" de façon completement analogue  à ce qu'on fait en base 10 .

Ainsi , un nombre réel x pourra s'écrire sous la forme m * 2^p :

 - La mantisse m du nombre dans l'intervalle [(1)2, (10)2[ ( ou un nombre compris en 1(inclus) et 2(exclus) dans un langage profane 

 - l'exposant p un entier relatif

 Exemple : Pour (124,6875)10 = (1111111,1011)2 = (1111111,1011)2 * 2⁶

 # Code en virgule flottante sur 32 bits Norme IEEE-754

La norme IEEE-754 est la norme la plus employée pour la representation des nombres à virgule flottant dans le domaine informatique . La première version de norme date 1985 . Il existe deux formats associés à cette norme : le format dit "simple précision" ( utilise 32 bits pour écrire un nombre décimal) et le format dit "double précision" ( sur 64 bits). 

### On a 32 bits pour representer ce nombre : 

- Le premier bit represente le signe ( 0 pour *positif* , 1 pour *négatif* ) : 0

- Les 8 bit suivant representent p + 127 ( Pourquoi ? : Pour ne pas a avoir coder de négatif ... par exemple la puissance 2⁻⁵ , on code 122 qui est positif ) : 7 + 127 = 134 = (10000110)2

- Les 23 bits restants codent la parite après la virgule de la mantisse ( donc pas le "1" avant la virgule , ce serait inutile puisqu'on sait qu'il ne peux y avoir que "1") : 111100101 



