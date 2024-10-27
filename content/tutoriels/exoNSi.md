+++
title="Exercice Tux NSI"
date=2024-01-06
draft=false
+++

# Contexte 

Tux notre chère pinguin veux savoir la temperature de son igloo, il mait donc un témometre et tout les heures Tux note sur un boue de papier tout les heure la temperatur de son igloo . 
Il obtient donc ceci : -7,-20,-30,-20,8,-23,-5,-1,-29,-10,-19,-27,-6,-10,-2,2,-21,1,10,3,8,-19,-5,-9 .

# Question

1) Fait donc une liste nommé TemperatureTux avec tout les informations 

# Reponse : TemperatureTux = [-7,30,-20,-20,8,-23,-5,-1,-29,-10,-19,-27,-6,-10,-2,2,-21,1,10,3,8,-19,-5,-9]

2) Tux aimerez que son robot lui dit la temperature . D'après la liste de la question 1 faire une fonctionne qui print la temperature apatenant à l'heure . Exemple Si on lui donne 3 il nous donne -30 .

# def temperature(heure):
    print(TemperatureTux[heure])


3) Tux va donc faire des prise tout les heure il veux rentrer ces valeur dans un base de donée ceci ces temperature seron dans la liste TuxTemperature2 . Au debut de la fonction on aura un message "Veillez fournir une temperature" puis la temperature sera ajouter à la nouvelle liste puis la valeur liste sera retournée 

#  def AutomatisationTemperature():
   reponse = input("Veillez fournir une temperature ") 
   TuxTemperature2.append(reponse)
   return TuxTemperature2


