+++
title="Maths Chapitre 2 : Dérivation"
date=2024-02-22
draft=false
+++

# Nombre dérivé et tangente

Definition : Soit f une fonction et a un réel du domaine de definition de f. Le nombre dérivé de f en a note f'(a) est le nombre :

<math>
  <mfrac bevelled="true">
    <mfrac>
      <mi>f(x)-f(a)</mi>
      <mi>x-a</mi>
    </mfrac>
  </mfrac>
</math>

> Remarque : 
> 1) On supose que la limite précédente existe ( ce qui n'est pas toujours le cas !) On dit alors que f dérivable en a
> 2) Autre version , en posant x = a + h : f'(a) lim -> <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi>f(a+h)-f(a)</mi>
      <mi>h</mi>
    </mfrac>
  </mfrac>
</math>

 **Interpretation graphique** : Dans la situation precedente , on considere les point A(a;f(a)) et M(a+h;f(a+h)),alors le quotien <math>
  <mfrac bevelled="true">
    <mfrac>
      <mi>f(a+h)-f(a)</mi>
      <mi>h</mi>
    </mfrac>
  </mfrac>
</math>
represente le coef directeur de (AM) lorsque h tend vers 0 M se rapproche de ... et la droite (AM) se "raproche" d'une droite appelée la tangant à f en a

**Définition** : Soit une fonction definie sur un intervalle I et dérivable en un nombre réel a appartenant à I . A est un point d'abscisse a appartenant à la courbe representative f

La tangente à la courbe f au point A est la droite passant par A de coef directeur le nombre dérivé f'(a)

**Propriété** Une équation de la tangente à la courbe f en A est ```y = f'(a) * (x-a) + f(a)```

## Calculs de dérivées

1) Formule de dérivation des fonction usuelles 

Propriété (admise) les fonctions usuelles (fonction affines , fonction polynome du 2nd degré , fonction inverse , fonction racine , fonction exponentielle ) sont dérivable sur leur domaine de definition et on a les formules suivante : 

<table border="1">
        <thead>
            <tr>
                <th>Fonction f</th>
                <th>Ensemble de définition de f</th>
                <th>Dérivée f'</th>
                <th>Ensemble de définition de f'</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>f(x) = a, a ∈ ℝ</td>
                <td>ℝ</td>
                <td>0</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = x</td>
                <td>ℝ</td>
                <td>1</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = x²</td>
                <td>ℝ</td>
                <td>2x</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = xⁿ, n ∈ ℕ</td>
                <td>ℝ</td>
                <td>nxⁿ⁻¹</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = 1/xⁿ</td>
                <td>ℝ*</td>
                <td>-n/xⁿ⁺¹</td>
                <td>ℝ*</td>
            </tr>
            <tr>
                <td>f(x) = √x</td>
                <td>ℝ⁺</td>
                <td>1/(2√x)</td>
                <td>ℝ*⁺</td>
            </tr>
            <tr>
                <td>f(x) = e^x</td>
                <td>ℝ</td>
                <td>e^x</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = cos(x)</td>
                <td>ℝ</td>
                <td>-sin(x)</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = sin(x)</td>
                <td>ℝ</td>
                <td>cos(x)</td>
                <td>ℝ</td>
            </tr>
            <tr>
                <td>f(x) = ln(x)</td>
                <td>ℝ*⁺</td>
                <td>1/x</td>
                <td>ℝ*⁺</td>
            </tr>
        </tbody>
    </table>

## Formule de derivation par operation de fonction usuelles 

Propriete (admise) les fonctions obtenues par operations (Somme , multiplication par un réel multiplication de fraction , quotient , composition ) et on a les formules suivantes 


 <table border="1">
        <thead>
            <tr>
                <th>f</th>
                <th>f'</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>u + v</td>
                <td>u' + v'</td>
            </tr>
            <tr>
                <td>u * v</td>
                <td>u'v + uv'</td>
            </tr>
            <tr>
                <td>k * v (k ∈ ℝ)</td>
                <td>k * v'</td>
            </tr>
            <tr>
                <td>u / v</td>
                <td>(u'v - uv') / v²</td>
            </tr>
            <tr>
                <td>1 / uⁿ</td>
                <td>-n u⁻ⁿ⁻¹ u'</td>
            </tr>
            <tr>
                <td>uⁿ</td>
                <td>n uⁿ⁻¹ u'</td>
            </tr>
            <tr>
                <td>√u</td>
                <td>u' / (2√u)</td>
            </tr>
            <tr>
                <td>e<sup>u</sup></td>
                <td>u' e<sup>u</sup></td>
            </tr>
            <tr>
                <td>cos(u)</td>
                <td>-u' sin(u)</td>
            </tr>
            <tr>
                <td>sin(u)</td>
                <td>u' cos(u)</td>
            </tr>
            <tr>
                <td>ln(u)</td>
                <td>u' / u</td>
            </tr>
        </tbody>
    </table>

## Composition d'une fonction

**Definition** : Soit u une fonction défini sur un intervalle I et soit V une fonction definie sur intervalle J tel que u(I) ∈ J . On appelle fonction composée de u suivie de v de la fonction notée V∘U definie sur I par 
V∘U(x) = V(U(x))

# Fonction convexes,fonction concave

## Definition et caracteristique

Shema a réaliser 

**Definition**: 

- Une fonction f est dite convexe sur un intervalle I si elle se situe entièrement sous ses cordes

- Une fonction f est dite concave sur un intervalle I si elle se situe entièrement sur ses cordes

> Remarque : ceci se traduit mathématiquemen par les inegalité 
>
> f convexe sur I
>
> f(tx + (1-t)y) =< tf(x) + (1-t)f(y)
>
> t ∈ [0;1] et x,y ∈ I
>
> f concave sur I
>
> f(tx + (1-t)y) >= tf(x) + (1-t)f(y)
>
> t ∈ [0;1] et x,y ∈ I


**Théoreme** : Soit f une fraction definie sur l'intervalle I

- f est convexe sur I si et seulement si f' croissante sur I
- f est concave sur I si et seulement si f' decroissante sur I

**Propriété 1** : SOit f une fonction definie sur un intervalle I qui est 2 fois dérivable sur I

- f est convexe sur I si et seulement si f''(x) >= 0
- f est concave sur I si et seulement si f''(x) =< 0

**Propriété 2** : Soit f une fonction dérivable sur l'intervalle

- f convexe si et seulement si f se situe au dessus de ses tengentes en I

- f concave si et seulement si f se situe au dessous de ses tengentes en I

## Point d'inflexion


**Définition** Soit f une fonction définie sur l'intervalle I . Un point d'inflextion en lequel f change de convexite

**Propriété** : Au point d'inflextion f traverse la tengente

**Théoreme** Soit f une fonction definie et deux fois derivable sur un intervalle I

Le point A (a;f(a)) est un point d'inflexion pour f si et seulement si f''(x) s'annule et change de signe en a

