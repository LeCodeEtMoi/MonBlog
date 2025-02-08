+++
title="NSI : Theme 6 : Representation d'un texte en machine"
date=2024-01-06
draft=false
+++
<style>
table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 20px;
      }

th, td {
        border: 1px solid #dddddd;
        text-align: center;
        padding: 8px;
        }

th {
    background-color: #f2f2f2;
</style>

## Encodage ?

Lors des premières transmissions d'information (télégraphe optique de Chappe en 1794 , télégraphe éléctrique de Cooke et Wheatstone en 1938, ...)il a été nécéssaire de définir un code pour representer les differents symboles utilisé dans le anguage courant ( lettre,chiffre,ponctuation, ...). Ce code peut être visuel(drapeau,tour Chappe ), codé à l'aide de plusieur impulsions ( code Morse), ... C'est ce que l'on appelle **l'encodage**.

Un ordinateur utilisant un système binaire pour stoker , transmettre et utiliser les données , il a fallu choisir un moyen de representer les differentes lettre et symbole à l'aide de 0 et de 1. Un des premiers systeme d'encode binaire ( sur 5 bits) et du au français Emile Baudot en 1874.

## Quel representation choisir ?

Au début de l'automatisation des recensements ( en 1890) machines fonctionnat à l'aide de cartes perforées ) chaque machines/constructeur possédait son propre système d'encodage. Certain étaient liés à la structure matèrielle du lecteur de cartes perforées par exemple ( lecteur purement méchaniquement) et qu'il y avait incompatibilité entre les 2 plus grands constructeur de l'époque (Bull et IBM).

C'est prolifération d'encodage possèdeplusieur inconvénients :

- Changement d'appareils compliqué

- Transfert de données compliqué

- Obligée de redévelloper des programmes à chaque machine

Le besoin pour un encoage standardisé se fait ressentir.

1) A.S.C.I.I. : En 1963, après un travail du Département de Défense des État UNis d'Amerique , une première norme apparait , c'est la naissance de l'encodage A.S.C.I.I American Standard Code for Informatique Interchange. Elle définit un standard pour code les caratères en binaire.

 <title>ASCII</title>
</head>
<body>
    <table>
        <tbody>
            <tr>
                <td>Nombre de bits utilisés </td>
                <td>7 soit 2⁷ symboles differents donc 128 symboles differents</td>
            </tr>
            <tr>
                <td>Symbole codable en ASCII</td>
                <td>Toutes les lettres ( majuscule, minuscule, et tout les letre sans accent) ansi que les chiffre et la ponctuation</td>
            </tr>
            <tr>
                <td>Avantages</td>
                <td>Universel , prend peu de place , sa compatibilité avec d'autre appareils</td>
            </tr>
            <tr>
                <td>Inconvéniens</td>
                <td>Non adapté pour toutes les langues ansi qu'un grand nombre de caratère limité</td>
            </tr>
        </tbody>
    </table>
</body>

 2) ISO 8859-15 : La norme ISO-15 ( aussi appelée Latin-9) est un nomre européenne qui apparait en 1998. Elle concerne les pays suivant : France ,Allemage , Espagne , Italie , Portugale , Finlande , Sude ,Norvège , Danemark et Cananda .

 <title>ISO 8859-15</title>
</head>
<body>
    <table>
        <tbody>
            <tr>
                <td>Nombre de bits utilisés </td>
                <td>8 soit 2⁸ symboles differents donc 256 symboles differents</td>
            </tr>
            <tr>
                <td>Symbole codable en ASCII</td>
                <td>A.S.C.I.I + les charatères speciaux</td>
            </tr>
            <tr>
                <td>Avantages</td>
                <td>Contabilité avec les pays UE et compatible avec A.S.C.I.I.</td>
            </tr>
            <tr>
                <td>Inconvéniens</td>
                <td>Marche qu'avec l'afabet latin et pas de smiley :(</td>
            </tr>
        </tbody>
    </table>
</body>

 3) UTF-8 : L'encodage UTF-8 ( Unicode Transformation Format) apparaît avec la norme ISO/CEI 10646 de 1993 . Il est depuis devenue entièrement compatible avec la norme Unicode ( qui a pour but depuis 1991 d'offirir un encodage commun au monde entier , pour cela la norme Unicode nécessite 2²¹ nombres).

 <title>UTF-8</title>
</head>
<body>
    <table>
        <tbody>
            <tr>
                <td>Nombre de bits utilisés </td>
                <td> Entre 1 et 4 octet mais uniquement 2²¹ donc 2 milliard symboles differents</td>
            </tr>
            <tr>
                <td>Symbole codable en ASCII</td>
                <td>A peu près tout les symboles</td>
            </tr>
            <tr>
                <td>Avantages</td>
                <td>Universel , prend en charge toutes les langes , compatible avec A.S.C.I.I</td>
            </tr>
            <tr>
                <td>Inconvéniens</td>
                <td>Peu prenddre de la place celon les charatère</td>
            </tr>
        </tbody>
    </table>
</body>

C'est maintenant l'encodage ke plus répandu sur internet ( utilisé par environs 95% des site internet en 2019)

