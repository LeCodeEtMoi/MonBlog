+++
title="NSI : Theme 4 : Codage des nombres entiers naturels"
date=2024-01-06
draft=false
+++

Une quantité d'objets est représentée par un nombre . A l'origine de l'humanité chaque quantité était représenté par un nombre équivalent de cailloux (calucules) de batons ou de points ...

L'homme , utilisant ses 10 doigts (digit) pour compter , est venue la numération en base de 10 ou numération décimale . On utilise aussi de manière épisodique la base de 12 ( douzaines) la base soixante ( heures , minutes et secondes ) Les informations utilisent les base 2, 16 et 8 .

## <u>I La numération de position : systéme décimal</u><br>

NOus utilisons dans la vie courante le système décimal ou on peut écrire n'importe quel nombre entier comme une succession de chiffre dont chacun est pris dans l'ensemble des dix chiffres : 
{0,1,2,3,4,5,6,7,8,9}

Par exemple : Le nombre 2329 est formé de quatre chiffres.

L'écriture 2329 exprime un entier naturel formée de 2 milliers 3 centaines 2 dizaines et 9 unités :

Ou encore 2×10³+3×10²+9×10⁰
Cette representation à l'aide de puissance successives de 10 s'appelle une écriture de nombre a en base 10 (base décimale)

Généralisation : Soit p un nombre entier . L'entier d'un nombre en base p : ...... il manque des chose

Exemple :  (58623)10 = 5×10⁴+8×10³+6×10²+2×10¹+3×10⁰ 

(1230)4 = 1×4³+2×4²+3×4¹+0×1⁰ = 92

(212)2 = 2×3²+1×3²+1×3¹+2×3$0 =23
 
## <u>II La numération binaire</u><br>

On reprend la formule précédente avec les p=2 . Il n'y a donc que deux chiffre qui sont : 0 et 1 . La numération en base 2 est le systéme le plus adaptéaux machine électronique . Les deux symboles 1 et 0 correspondent  à deux étaps : le courant passe ou ne passe pas . La representation d'un nombre en base 2 suit le même principe qu'en base 10 .

Savoir faire conversion de l'écriture binaire à l'écriture décimale 

Exemple : (1101)2 1×2³+1×2²+0×2¹+1×2 = 2³+2²+2⁰ = 8+4+1 =13

Tableau Des Puissance :
<table>
        <thead>
            <tr>
                <th>Puissance de 2</th>
                <th>Résultat</th>
            </tr>
        </thead>
        <tbody>
        	<tr>
                <td>2⁷</td>
                <td>125</td>
            </tr>
            <tr>
                <td>2⁶</td>
                <td>64</td>
            </tr>
            <tr>
                <td>2⁵</td>
                <td>32</td>
            </tr>
            <tr>
                <td>2⁴</td>
                <td>16</td>
            </tr>
            <tr>
                <td>2³</td>
                <td>8</td>
            </tr>
            <tr>
                <td>2²</td>
                <td>4</td>
            </tr>
            <tr>
                <td>2¹</td>
                <td>2</td>
            </tr>
            <tr>
                <td>2¹</td>
                <td>1</td>
            </tr>
        </tbody>
</table><br>

Savoir-faire : conversion de l'écriture décimale à l'écriture bianire : 

On fait un sucesion de division par 2 ( car on veut un binaire) jusqu'a obtenir un quotion égaule à 0 . On va donc faire une division euclidienne .

Exemple : Determiner l'écriturebinaire de 29 : 

J'ai pas trouvé representé la representation de la divisoon euclidienne en html .

29/2 = 16 16/2 = 8 8/2=4 4/2=2 (11101)2 

# 3 Operations avec les nombres binaires 

Addition : L'addition se pratique de la meme façon que dans le calcule décimal usuel , et repose sur la table d'addition suivant :

Table d'adition en binaire : 
<table>
        <thead>
            <tr>
                <th>+</th>
                <th>0</th>
                <th>1</th>
            </tr>
        </thead>
        <tbody>
        	<tr>
                <td>0</td>
                <td>0</td>
                <td>1</td>
            </tr>
            <tr>
                <td>1</td>
                <td>1</td>
                <td>10</td>
            </tr>
        </tbody>
</table><br>
 
 Exemple :  Il recommande de la possé l'opération

 1011
 
+1001 

10100


Multiplication : La multiplication

101×11 = 101 + 101 = 1111

Table de la multiplication en binaire : 
<table>
        <thead>
            <tr>
                <th>×</th>
                <th>0</th>
                <th>1</th>
            </tr>
        </thead>
        <tbody>
        	<tr>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
            <tr>
                <td>1</td>
                <td>0</td>
                <td>1</td>
            </tr>
        </tbody>
</table><br>


# 4 La numération hexadécimale

L'utulisation par l'homme de système binaire est particulièrement délicate ( risque d'erreur ) la conersion systématique en décimale est loudre . Les informatitien utilisent le systeme Hexadecimal (base 16). Nous allons voir qu'il est relativement simple et surtout que le passage de la 2 à la base est très simple .
Le systeme hexadecimale est comme le binaire et le decimal un systeme de numérotation de position ponderé. Il néssécite 16 symbole . 0 1 2 3 4 5 6 7 8 9 A B C D E F ou A = 10 B = 11 C = 12 D = 13 E = 14 F = 15

Savoir-faire : Conversion de l'écriture hexadecimale à l'écriture décimale 

(B2) 11×16¹ + 2×16⁰ = 178

Savoir-faire : conversion de k'écriture décimale à l'écriture Hexadecimale

Comme dans le cas de l'écriture binaire , on fait une succession de division non plus par 2 mais par 16 jusqu'a obtenir un quotion ègale à 0 

5567 = (15BF)16 = 1×16³+5×162+11×16¹+15×16⁰

Savoir-faire : La conversion del'hexadecimal vers le binaire et , inversement, la conversion du binaire vers hexadecimal , se font directement ( c'est a dire sans passer par le code décimal) et très rapidement avec le tableau suivant 

<table>
        <thead>
            <tr>
                <th>Décimale</th>
                <th>Binaire</th>
                <th>Hexadécimale</th>
            </tr>
        </thead>
        <tbody>
        	<tr>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
            <tr>
                <td>1</td>
                <td>1</td>
                <td>1</td>
            </tr>
            <tr>
                <td>2</td>
                <td>10</td>
                <td>2</td>
            </tr>
            <tr>
                <td>3</td>
                <td>11</td>
                <td>3</td>
            </tr>
            <tr>
                <td>4</td>
                <td>100</td>
                <td>4</td>
            </tr>
            <tr>
                <td>5</td>
                <td>101</td>
                <td>5</td>
            </tr>
            <tr>
                <td>6</td>
                <td>110</td>
                <td>6</td>
            </tr>
            <tr>
                <td>7</td>
                <td>111</td>
                <td>7</td>
            </tr>
            <tr>
                <td>8</td>
                <td>1000</td>
                <td>8</td>
            </tr>
            <tr>
                <td>9</td>
                <td>1001</td>
                <td>9</td>
            </tr>
            <tr>
                <td>10</td>
                <td>1010</td>
                <td>A</td>
            </tr>
            <tr>
                <td>11</td>
                <td>1011</td>
                <td>B</td>
            </tr>
            <tr>
                <td>12</td>
                <td>1100</td>
                <td>C</td>
            </tr>
            <tr>
                <td>13</td>
                <td>1101</td>
                <td>D</td>
            </tr>
            <tr>
                <td>14</td>
                <td>1110</td>
                <td>E</td>
            </tr>
            <tr>
                <td>15</td>
                <td>1111</td>
                <td>F</td>
            </tr>
        </tbody>
</table><br>

Savoir Faire : Une conversion de l'écriture hexadecimal à une ecriture décimale 

Pour (B2)16 = 11 * 16¹ + 2 * 16⁰ = 178

Savoir faire : une conversionde l'écriture décimale à l'écriture Hexadécimale 

Comme dans le cas d'une écriture binaire , on fait une succession de division non plus par 16 jusqu'à obtenir un quotient égal à 0

5567 = (15BF)16 = 1 * 16³ + 5* 16² + 11* 16¹ + 15* 16⁰

Savoir faire : la conversion de l'hexadecimal vers le binaire et inversement , la conversion du binaire vers l'hexadeciaml se font directement  

