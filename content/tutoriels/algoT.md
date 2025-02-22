+++
title = "Algo à connaitre Terminale"
date = 2025-01-19
draft = false
+++

Algo Echange

```python
def echange(T,i,j):
	tmp=T[i]
	T[i] = T[j]
	T[j] = tmp
```

```python
def Tri_par_selection(T):
    for i in range(len(T)-1):
        min_index = i
        for j in range(i+1,len(T)):
            if T[j] < T[min_index]:
                min_index = j
        echange(T,i,min_index)
    return T
```

```python
def Insere_nombre(T,element):
    i = 0
    while T[i] < element:
        i += 1
    T.append(element)
    for j in range(i,len(T)-1):
        echange(T,j,len(T)-1)
    return T
```

```python
def Tri_insertion(T):
    for i in range(1,len(T)):
        j = i
        while T[j] < T[j-1] and j > 0:
            echange(T,j,j-1)
            j = j-1
    return T
 ```

 ```python
 def Recherche_Dichotomique(L,valeur):
    """
    Entréé : une liste triée et une valeur
    Sortie : l'indice de l'element
    """
    debut = 0
    fin = len(L)-1
    while debut <= fin:
        milieu = (debut+fin)//2
        if L[milieu] == valeur:
            return milieu
        elif L[milieu] < valeur:
            debut = milieu +1
        else:
            fin = milieu -1
    return -1
```
```python
def Boyer_Moore(dico, motif, texte):
    """
    Entrée :
        dico : dictionnaire des décalages pour chaque caractère du motif
        motif : le motif à rechercher
        texte : le texte où effectuer la recherche
    Sortie : une liste des indices où le motif est trouvé dans le texte
    """
    indices = []
    taille_motif = len(motif)
    taille_texte = len(texte)
    i = 0  # Indice dans le texte

    while i <= taille_texte - taille_motif:
        j = taille_motif - 1  # Indice dans le motif
        while j >= 0 and texte[i + j] == motif[j]:
            j -= 1
        if j == -1:
            indices.append(i)
            i += taille_motif
        else:
            if texte[i + j] in dico:
                decalage = dico[texte[i + j]]
            else:
                decalage = taille_motif
            if decalage > 1:
                i += decalage
            else:
                i += 1
    return indices

```
# Arbre 

```python
class Noeud:
    def __init__(self, valeur, gauche=None, droit=None):
        self.valeur = valeur
        self.gauche = gauche
        self.droit = droit


arbre = Noeud(1,
              gauche=Noeud(2, gauche=Noeud(4), droit=Noeud(5)),
              droit=Noeud(3, gauche=Noeud(6), droit=Noeud(7)))
              
    
def parcours_profondeur(arbre):
    """
    Parcours un arbre en profondeur dans l'ordre spécifié.
    :param arbre: le noeud racine de l'arbre.
    :param ordre: "prefixe", "infixe" ou "suffixe".
    """
    if arbre is None:
        return
    # Si parcours préfixe : traiter avant les sous-arbres
    print(arbre.valeur)
    # Parcours du sous-arbre gauche
    parcours_profondeur(arbre.gauche)
    # Si parcours infixe : traiter entre les sous-arbres
    print(arbre.valeur)
    # Parcours du sous-arbre droit
    parcours_profondeur(arbre.droit)
    # Si parcours suffixe : traiter après les sous-arbres
    print(arbre.valeur)
    
parcours_profondeur(arbre)
```
```python
def Parcours_Largeur(a):
    """
    Parcours un arbre en largeur (BFS).
    :param a: Racine de l'arbre à parcourir.
    """
    if a is None:
        return

    F = File()  # Initialisation de la file
    F.Inserer(a)  # Ajouter la racine à la file

    while not F.FileVide():
        noeud = F.Extraire()  # Extraire le prochain élément de la file
        Traiter(noeud.valeur)  # Traiter la valeur du noeud

        # Ajouter les fils gauche et droit à la file, s'ils existent
        if noeud.gauche:
            F.Inserer(noeud.gauche)
        if noeud.droit:
            F.Inserer(noeud.droit)
```
