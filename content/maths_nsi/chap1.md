+++
title="Maths Chapitre 1 : Suite numérique et raisonnement par recurence"
date=2024-02-22
draft=false
+++

# Definition 
Une suite numerique est une suite de nombre réels , c'est a dire c'est une application de N dans ||R 

Notaton : 
- (U<sub>n</sub>) designe l'ensemble des termes 
- U<sub>n</sub> designe le terme de rang n

## Mode de définition explicite U<sub>n</sub> = f(n)

"Chaque terme se calcule en fonction du n"

Ex : 

1) 
- U<sub>n</sub> = 2 + 3n² = f(n) ou f(x) = 2+ 3x²
- U<sub>0</sub> = 2 U<sub>1</sub> = 5 U<sub>10</sub> = 302

2) U<sub>n</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>
  n + 2 = f(n) ou f(x) = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>x+2</math>
</math> 


**Remarque** : On represente la suite (U<sub>n</sub>) en plaçant les point (n,U<sub>n</sub>) 

Shema a réaliser 

## Mode de definition par récurence :

U<sub>n+1</sub> = f(U<sub>n</sub>) "Chaque terme se calcule en fonction du precedant"

1) "Chaque terme est l'inverse du precedent"

- U<sub>n+1</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1</mi>
      <mi>U<sub>n</sub></mi>
    </mfrac>
  </mfrac>
<math>

- U<sub>0</sub> = 2

U<sub>1</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>
= 0,5<math>

U<sub>2</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 0,5 </mi>
    </mfrac>
  </mfrac>
= 2<math>

U<sub>3</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>
= 0,5<math>

U<sub>4</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 0,5 </mi>
    </mfrac>
  </mfrac>
= 2<math>

2) 
- U<sub>n+1</sub> = U<sub>n</sub> + 4 = f(U<sub>n</sub>)
- U<sub>0</sub> = -1

U<sub>1</sub> = 3
U<sub>2</sub> = 7
U<sub>3</sub> = 11

3) - U<sub>n+1</sub> = <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi> 1 </mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>
  U<sub>n</sub> + 2 = f(Un)
<math>

- U<sub>0</sub> = 0

U<sub>1</sub> = 2
U<sub>2</sub> = 3
U<sub>3</sub> = 3,5

## Representation graphique

A faire 

Methode : 

- On trace la droite d'équation y = x 
- On trace f
- On trace U<sub>0</sub> sur l'axe des absisses puis U<sub>1</sub> sur l'axe des ordonées puis on reote U<sub>1</sub> sur l'axe des abscisses grâce à la droite d'équation x = y et ainsi de suite ...


# Cas particulier : Suite arithmetique et suite géometrique

## Suite arithmetique

- ### Formule de récurence :

- U<sub>n+1</sub> = U<sub>n</sub> + r
- U<sub>0</sub> est donnée

- ### Formule explicite :

- U<sub>n</sub> = U<sub>0</sub> + n * r
- U<sub>n</sub> = U<sub>p</sub> + (n - p) * r

- ### Sommes des terme successifs  (U0 + U1 + .... + Un):

- (n+1)<math>
  <mfrac bevelled="true">
    <mfrac>
      <mi>U<sub>0</sub> + U<sub>n</sub></mi>
      <mi> 2 </mi>
    </mfrac>
  </mfrac>
<math>

## Suite géometrique 

- ### Formule de récurence :

- V<sub>n+1</sub> = V<sub>n</sub> * q
- V<sub>0</sub> est donnée

- ### Formule explicite :

- V<sub>n</sub> = U<sub>0</sub> * q<sup>n</sup>
- V<sub>n</sub> = U<sub>p</sub> + (n - p) * r

- ### Sommes des terme successifs  (V0 x V1 x .... x Un):

- V<sub>0</sub><math>
  <mfrac bevelled="true">
    <mfrac>
      <mi>1-q<sup>n+1</sup></mi>
      <mi>1-q</mi>
    </mfrac>
  </mfrac>
<math>

- Formule générale  = V<sub>n = V<sub>p * V<sup>n-p


# 2 Le raisonnement par récurence 

Soit n un entier naturel et V<sub>n</sub> une propriete à démontrer

### Initialisation :

"On montrer que P<sub>0</sub> est vrai ..."

Cas ou P<sub>n</sub> "A<sub>n</sub> = B<sub>n</sub>" : On calcule A<sub>0</sub> d'une part et B<sub>0</sub> d'une autre par et on verifie que les quantités sont égales

Cas ou P<sub>n</sub> "A<sub>n </sub>< B<sub>n</sub>" : On calcule A<sub>0</sub> est on verifie que l'inegalité est vérifier

### Heredité : "Pour un certain entier k on suppose que P<sub>k</sub> est vrai"

c'est a dire A<sub>k</sub> = B<sub>k</sub> alors on doit démontrer que P<sub>k+1</sub> l'est aussi c'est a dire que A<sub>k+1</sub> = B<sub>k+1</sub>

Cas où P<sub>n</sub> "A<sub>n</sub> = B<sub>n</sub> : Généralement on part de A<sub>k+1</sub> pour arriver à B<sub>k+1</sub> en utilisant l'HR et les éventuelles données de l'énoncé


cas P<sub>n</sub> "A<sub>n </sub>< B<sub>n</sub> : Généralement on part de l'HR pour arriver à P<sub>k+1</sub> en détaillant les operation en justifiant le sens l'inegalité a chaque étape .

### Conclusion "P<sub>n</sub> est initialisée et héréditaire donc P<sub>n</sub> vrai pour tout entier n"

> Remarque : Une demonstration par recurence est bien indiquer lorsque l'on veut demontrer une assertion qui depent d'un entier 

!! Il existe des propriété Initialisation mais non hereditaire et Hereditaire mais non Initialiser !!