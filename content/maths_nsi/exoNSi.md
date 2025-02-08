+++
title="Exercice Tux NSI"
date=2024-01-06
draft=false
+++

## Contexte 

Tux, notre cher pingouin, veut connaître la température de son igloo. Il installe donc un thermomètre et, chaque heure, note sur un bout de papier la température de son igloo. 
Il obtient donc ceci : -7,-20,-30,-20,8,-23,-5,-1,-29,-10,-19,-27,-6,-10,-2,2,-21,1,10,3,8,-19,-5,-9 .

## Question

1) Fait donc une liste nommé TemperatureTux en python avec tout les informations 

<details>
<summary>Réponse</summary>
TemperatureTux = [-7, 30, -20, -20, 8, -23, -5, -1, -29, -10, -19, -27, -6, -10, -2, 2, -21, 1, 10, 3, 8, -19, -5, -9]
</details>


2) Tux aimerait que son robot lui dise la température. D'après la liste donnée dans la question 1, créez une fonction qui affiche la température correspondant à une heure donnée.

Exemple : Si on lui donne l'heure ```3```, la fonction doit renvoyer ```-30```.

<details>
<summary>Réponse</summary>

```python

def temperature(heure):
    print(TemperatureTux[heure-1])

```
</details>



3. Tux va effectuer des relevés chaque heure et souhaite enregistrer ces valeurs dans une base de données. Ces températures seront stockées dans une liste appelée TuxTemperature.

Au début de la fonction, un message indiquera : "Veuillez fournir une température". La température saisie sera ensuite ajoutée à la liste, et cette dernière sera retournée.


<details>
<summary>Réponse</summary>

```python

def AutomatisationTemperature(liste):
   reponse = input("Veillez fournir une temperature ") 
   liste.append(reponse)
   
AutomatisationTemperature(TemperatureTux)

```
</details> 


Tux souhaite connaître la température moyenne enregistrée à partir des données de sa liste de relevés. Écrivez une fonction qui :

- Prend en entrée la liste des températures.
- Calcule et renvoie la température moyenne.

Exemple :

Pour une liste ```[5, -3, -10, 7]```, la fonction doit retourner ```-0.25```.

<details>
<summary>Réponse</summary>

```python
def moyenne(liste):
    somme = 0
    for element in liste:
        somme += element
    return somme/len(liste)

```
</details>

Un matin, Tux remarque qu'il fait particulièrement froid dans son igloo. Il veut connaître les températures extrêmes de la journée : la plus chaude et la plus froide. Grâce a la fonction extremites(liste) qui prend en paramettre la liste des temperatures Tux peut obtenir ces informations rapidement 


<details>
<summary>Réponse</summary>

```python
def extremites(liste):
    max = liste[0]
    min = liste[0]
    for element in liste:
        if element > max:
            max = element
        if element < min:
            min = element
    return max,min

```
</details>

Un jour, alors que Tux vérifie ses relevés de température, il se demande combien de fois il a eu des températures négatives dans son igloo. Il décide donc de créer une fonction temperatures_negatives(liste) qui filtre les températures négatives pour les examiner de plus près.

<details>
<summary>Réponse</summary>

```python

def temperatures_negatives(liste):
    compteur = 0
    for element in liste:
        if element < 0:
            compteur += 1
    return compteur

```
</details>



