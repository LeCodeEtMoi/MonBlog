+++
title = "Theme 9 Systeme de gestion de Base de Donnée Terminale"
date = 2025-01-19
draft = false
+++

- SQL est le langage pour communiquer avec une base de donnée
- On fait des requetes vers une BDD

Ici on va avoir tout les requette qu'il faut connaitre pour le bac mais si vous avez un doutes sur une requettes ou voulez en savoir plus : https://sql.sh/

On cherche tout les nom qui commence par m
```SQL
SELECT prenom
FROM usager
WHERE nom LIKE vers "m%"
``` 

```SQL
COUNT(*) # Pour conter le nombre d'élément

SUM() # Pour additionner

ORDER BY nom ASC/DESC

LIMIT

DISTINT # Pour avoir chaque element qu'une seul fois 

AVG() #Pour avoir la moyenne

MAX()/MIN()
AS # Pour renomer

INSERT INTO nom_de_la_table
VALUES (....);

UPDATE nom_de_la_table
SET nom_attribut = nouvelle valeur
WHERE ...

DELET FROM nom_de_la_table
WHERE

DROP TABLE nom_de_la_table # Pour supprimer la table

SELECT *
FROM A
JOIN B ON A.key = B.key

```