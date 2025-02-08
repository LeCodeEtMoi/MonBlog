+++
title="NSI : Thème 10 : Système d'exploitation "
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

 Qu'es qu'un systeme d'exploitation ?

 Un systeme d'exploitation est un logiciel spécialisé servant principalement à gerer le lien entre tous les mondes applicatifs, donc les logiciels et le monmateriels comme les processeurs et ainsi de suite . Le systeme d'exploitation est le premier programme éxecuté lors de démarage d'un ordinaeur . Son rôle est de :

 - Fournir une interface entre l'humain et la machine (IHM)

 - Gérer les ressource de l'ordinateurt ( mémoire , péréphiriques ... )

 - Gérer les utilisateurs et leurs droits d'accés au fichiers .

 En fonctionne des besoins d, on va utiliser un systeme d'exploitation ou un autre , plus ou moins spécialisé par rapport à ce que l'on souhaite ( mais bon entre nous on c'est très bien que Linux est bien mieux :p) Il y a deux type d'OS : les OS libres comme Linux( le code est public et il peux être modifier ) et les OS propritaire comme Windows i ln'es pas possible et même illegal de modifier le cdde) Mac est entre l' OS libre et pas libre .

 Les systèmes d'exploitation les plus connus et utilisés dans le monde appartient à l'une des ces familles : UNIX ( Max Os , Linux , Android) et Windows .

 ## Arborecence 

 mettre image 

 Remarque : L'absenceou la presence du / au début du chemin permet de distinguer un chemin relatif ( ne part pas de la racine , mais depuis un repertoire quelconque ) d'un chemin absolue ( doit indiquer "le chemin" dupuis la racine et indique tous les repertoire rencontré) .

 Lorsqu'il se connecte , un utilisateur a pour dossier courant le dossier "home".

## Communication avec le système d'exploitation 

a voir mais je crois que j'ai deja fait un truc sur les commande 

Dans tous les sytèmes d'exploitatio, on trouve qui s'applle terminal ( une des meilleur application perso :p ) qui permet d'executer des tache en écrivant des commande ( et non en cliquant sur des icône ) .

Pour cela il faut connaître les commandes permettant d'effectuer des actions , voici les commande à connaitre en première spè NSI : 



</head>
<body>
	<title>ISO 8859-15</title>
    <table>
        <tbody>
            <tr>
                <td>ls</td>
                <td>liste le contenue du repertoire courant </td>
            </tr>
            <tr>
                <td>mv</td>
                <td> Déplace des fichiers ou des repertoires </td>
            </tr>
            <tr>
                <td>cd</td>
                <td>Change de répertoire</td>
            </tr>
            <tr>
                <td>mkdir</td>
                <td>Supprime un dossier</td>
            </tr>
            <tr>
                <td>cp</td>
                <td>Coppie des fichier ou des répertoires</td>
            </tr>
            <tr>
                <td>rm</td>
                <td>Supprime un fichier ou un répertoire</td>
            </tr>
            <tr>
                <td>pwd</td>
                <td>Affiche le repertoire ou l'on se trouve exactement</td>
            </tr>
        </tbody>
    </table>
</body>

## Droit et permission

Chaque utilisateur possede des droites qui lui ont été octroyés par le "super utilisateur" . Nous nous interesserons ici uniquement aux droits liés au fichiers , mais vous devez savoir qu'il existe d'autre droits liées aux autre éléments du système d'exploitation ( imprimante , installation d'application ...)

### Les fichiers et les repertoires possèdents 3 types de droits : 

- Les droits en lecture ( symbolisant par la lecture r ) : est-il possible de lire un document ?

- Les droit d'écriture ( lettre w) : est -il possible de modifier du contenue ?

- Les droits d'execution ( lttre x ) : est - il possible d'executer du contenue de ce fichier 


Il existe 3 types d'utilisateurs pour un fichier ou un répertoire :

- le propriétaire du fichier : il est symbolisé par la lecture "u" (user)

- un fichier est associer à un groupe tous les utilisateurs appartenant à ce groupe possèdent des droits particulier sur ce fichier : Le groupe est symbolisé par la ettre "g" (group)

- pour les autres utilisateur . C'est utilisateur sont symbolisés par la lecture "o" (other)

Exemple : Un fichier dont le droit d'accès est rwxr-xr est accessoire :

- en lecture ecriture pour le propriétaire 

- en lecture et en exécution pour le groupe

- en lecture seul pour les autre

La comande chmod permet de modifier les droits d'accès à un fichier 