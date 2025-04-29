+++
title="Épisodes n°1 Comprendre le fonctionnements internets"
date=2025-04-13
draft=false
+++

# Origine d'internet

## Le réseau ARPANET

Tout commença dans les années 1960 avec J.C.R. Licklider du MIT, qui imagina un réseau global d'ordinateurs permettant l'accès rapide aux données. Il fut soutenu par la DARPA (Defense Advanced Research Projects Agency) et des chercheurs comme Ivan Sutherland et Lawrence Roberts. En 1965, Roberts réalisa le premier test de connexion entre ordinateurs, mais c’est grâce à Leonard Kleinrock que la commutation par paquets devint essentielle pour les réseaux informatiques. Puis en 1969 le réseau ARPANET est créé , le 21 novembre 1969 le premier lien ARPANET verra le jour. Le premier message inter-hôte fut transmis entre UCLA et SRI. Rapidement, d’autres ordinateurs rejoignirent ARPANET, et un protocole de communication, le NCP, fut développé. Le NCP (Network Control Protocol) était limité à la gestion des connexions sur le réseau ARPANET et reposait sur la fiabilité de ce dernier, sans mécanisme d’erreur de bout en bout.


## Le réseau Cyclades

Louis Pouzin est chargée d'un réseau innovant, le projet Cyclades, qui repose sur la commutation de paquets par datagramme. Contrairement aux réseaux de l'époque, qui utilisent principalement la commutation de circuits (c’est-à-dire la création d'une connexion dédiée entre deux points pour transmettre des données),
Cyclades se base sur une approche différente et révolutionnaire : le datagramme. Dans ce modèle, chaque paquet de données circule indépendamment des autres, sans qu'une connexion dédiée soit nécessaire, ce qui offre une grande flexibilité et une meilleure tolérance aux pannes. Ce concept est un des principes fondamentaux sur lesquels repose Internet aujourd'hui. Cependant, le projet Cyclades se heurte rapidement à des obstacles politiques et économiques. En France, le monopole des Postes, télégraphes et téléphones (PTT) contrôlait toutes les infrastructures de télécommunications, et ses responsables ainsi que ses fournisseurs privilégiaient la commutation de circuits, jugée plus fiable et lucrative à l’époque. Cette opposition est renforcée par l'État français, qui, influencé par le monopole des PTT, estime que la commutation de circuits est plus conforme aux standards de télécommunication en vigueur et potentiellement plus rentable.Face à ces pressions, et malgré les avancées techniques du projet, le financement public est finalement retiré de Cyclades en 1974, ce qui conduit à l’abandon du projet après seulement trois ans.

## Le protocole TCP/IP

Robert E. Kahn recruta Vinton G. Cerf de l'université Stanford dans le but de travailler ensemble sur le problème du NCP. En 1973, ils avaient déjà réalisé une reformulation profonde, dans laquelle les différences entre les protocoles s'estompaient par l'utilisation d'un protocole de communication . Le protocole TCP original combinait fonctions d’adressage et
de transport, mais il a été scindé en deux : IP, pour l’adressage et la transmission de paquets, et TCP, pour le contrôle de flux et la correction des erreurs. L’UDP a ensuite été ajouté pour des applications nécessitant moins de contrôle.

## L'ARPANET et la Défense	

Après plusieurs années de service, ARPANET dépassait les missions de recherche pour lesquelles il avait été créé. En effet, l'agence DARPA était avant tout chargée de financer des recherches et non d’entretenir un réseau de communication à grande échelle. En juillet 1975, cette tâche fut transférée à la Defense Communications Agency (DCA), une branche du département de la Défense des États-Unis, marquant le début d’une évolution qui allait préparer la transition vers l'Internet. En 1983, pour répondre à des besoins distincts, ARPANET se scinda en deux réseaux : l’un destiné à la recherche (ARPANET) et l’autre aux communications militaires (MILNET), cette séparation contribuant à l'organisation des futurs réseaux mondiaux.

## Des Réseaux Fermés à l'Expansion

À ses débuts, ARPANET était restreint à un usage non commercial, et les connexions étaient principalement limitées aux sites militaires et aux universités, les entreprises étant exclues de l’utilisation du réseau. Le but principal était de faciliter la communication et la collaboration entre les chercheurs dans un cadre strictement académique et gouvernemental. Toutefois, dans les années 1980, ARPANET s'est progressivement élargi à d’autres institutions éducatives et à un nombre croissant d'entreprises technologiques, telles que Digital Equipment Corporation et Hewlett-Packard, qui participaient à des projets de recherche ou proposaient des services aux utilisateurs du réseau. Le développement de l'Internet s'est également accéléré avec l’implication d'autres entités gouvernementales. La National Science Foundation (NSF), une autre agence fédérale, a commencé à jouer un rôle majeur dans la recherche et la mise en place d'infrastructures de réseau. En 1984, la NSF a lancé un réseau de communication destiné à succéder à ARPANET : le NSFNET.


## NSFNET : La Fondation d'Internet

Le NSFNET, mis en place en 1986, allait devenir la dorsale centrale de l'Internet. Conçu spécifiquement pour utiliser le protocole TCP/IP, ce réseau étendu reliait plusieurs superordinateurs et centres de recherche financés par la National Science Foundation, facilitant ainsi le partage de ressources de calcul à haute performance entre différentes universités et laboratoires. L'extension progressive de NSFNET a permis à un nombre croissant d'institutions de se connecter au réseau et de participer à l'élargissement de ce qui allait devenir un véritable réseau global. Au fur et à mesure de son déploiement, NSFNET est devenu l'infrastructure essentielle qui a permis à l’Internet de se développer et de se structurer, unissant les chercheurs, les universités, et plus tard les entreprises à une échelle jamais vue auparavant. Grâce à l'implémentation du protocole TCP/IP, les différents réseaux se sont interconnectés, et le concept d'Internet tel que nous le connaissons aujourd'hui a pris forme.


## Un Réseau Ouvert : Le Passage à la Commercialisation

Bien que dans ses premières années, l'Internet ait été un espace de recherche et d'innovation réservé à un petit groupe d'utilisateurs, les années 1990 ont marqué un tournant. Les progrès dans le développement des protocoles et des technologies ont permis l'intégration de réseaux privés et commerciaux, propulsant l'Internet au-delà de sa fonction initiale de support à la recherche académique et militaire. L’introduction des services commerciaux, des sites Web et du commerce électronique a fait de l'Internet un outil omniprésent dans la vie quotidienne. 


## La Transition vers une Infrastructure Internet à Grande Échelle

Au fur et à mesure que la technologie Internet était validée par des expérimentations et adoptée par un nombre croissant de chercheurs en sciences informatiques, d'autres réseaux et technologies ont émergé, alimentés par un intérêt croissant pour les communications informatiques. Si l'ARPANET, soutenu par DARPA et utilisé par la communauté militaire et académique, avait démontré l'importance des réseaux, d'autres acteurs ont rapidement reconnu son potentiel et cherché à développer des infrastructures similaires. Dès le milieu des années 1970, plusieurs réseaux ont vu le jour. Le département américain de l’Énergie (DoE) a mis en place le MFENet pour ses chercheurs en fusion magnétique, tandis que le DoE, suivi par la NASA, a développé le HEPNet et le SPAN pour les physiciens. D'autres initiatives ont vu le jour, comme CSNET (créé pour les scientifiques en informatique) et BITNET (un réseau académique conçu pour faciliter l’échange de courriels). La diffusion du système UNIX par AT&T a également contribué à la naissance de USENET, un autre réseau de communication basé sur les protocoles UNIX. Cependant, à l'exception de BITNET et USENET, ces réseaux étaient souvent fermés et spécifiques à des communautés académiques ou de recherche, et ils n'étaient pas nécessairement compatibles les uns avec les autres. Pendant ce temps, des technologies commerciales comme XNS de Xerox, DECNet de Digital Equipment Corporation et SNA d'IBM étaient également explorées, bien que ces protocoles ne visaient pas à connecter des réseaux distincts de manière universelle.

## L’Émergence de NSFNET et la Transition vers une Infrastructure Universelle

NSF a lancé un programme crucial pour l'avenir d'Internet. Sous la direction de Dennis Jennings et plus tard de Steve Wolff, NSFNET a adopté une approche inclusive, choisissant d'utiliser le protocole TCP/IP, garantissant ainsi l'interopérabilité avec d'autres réseaux et d'autres initiatives. En 1986, NSFNET a été déployé comme un réseau étendu national pour relier les institutions de recherche et les universités, tout en favorisant une infrastructure indépendante du financement fédéral direct. NSFNET s'est appuyé sur les fondations posées par ARPANET, notamment l'Internet Activities Board (IAB), qui supervisait les efforts de normalisation et de gestion technique des protocoles Internet. NSF a également soutenu l'infrastructure de connexion internationale, en établissant des points d'interconnexion pour gérer le trafic entre les organisations. Ces points de connexion ont servi de modèles pour les futures architectures d'échange de données, essentielles à l'Internet moderne.

## Un Modèle de Partage et de Privatisation

Le modèle de partage de l'infrastructure entre les agences fédérales a permis une expansion rapide et efficace. Par exemple, les circuits trans-océaniques et les points d'interconnexion Internet étaient financés collectivement. Cette coopération a été renforcée par des partenariats internationaux, notamment avec des organisations comme RARE en Europe, afin de soutenir le réseau mondial de recherche. À partir de 1988, NSF a commencé à encourager les réseaux régionaux à chercher des clients commerciaux pour soutenir la croissance du réseau, tout en maintenant un contrôle strict sur les usages académiques et de recherche. Ce modèle a stimulé l’émergence de réseaux privés, tels que PSI, UUNET et ANS CO+RE, qui ont commencé à fournir une connectivité à l’échelle nationale, en concurrence avec les réseaux financés par l'État. En 1994, un rapport clé a été publié, formulant des recommandations pour l'avenir de l’Internet, notamment en ce qui concerne les questions de propriété intellectuelle, de régulation et d'éthique. Ce rapport a posé les bases de l'« autoroute de l'information » et a conduit à la privatisation de l’infrastructure Internet, en particulier la dorsale NSFNET, en 1995. Cette privatisation a marqué la fin du financement public direct pour la dorsale, qui est devenue entièrement gérée par des acteurs privés.


## L'Expérience du Changement Technologique : Du Logiciel à l'Équipement Commercial

À l'origine, NSFNET reposait sur des routeurs développés par la communauté de recherche, mais l’infrastructure s’est progressivement transformée, passant de matériels faits maison à des équipements commerciaux. En 1995, après près de 10 ans de service, NSFNET avait évolué, passant de 6 nœuds avec des connexions lentes à 21 nœuds avec des liens à haute vitesse. Ce changement reflétait une croissance exponentielle du nombre de réseaux, avec plus de 50 000 réseaux dans le monde entier.

## Le protocole TCP/IP, le Ciment de l'Internet Moderne

Le processus de transformation de l'Internet, soutenu par des programmes comme NSFNET, a permis de bâtir une infrastructure de réseau solide et interconnectée, essentielle à l'Internet mondial d'aujourd'hui. Le protocole TCP/IP, choisi dès le départ pour sa capacité à interconnecter des réseaux hétérogènes, a progressivement dominé, remplaçant d'autres protocoles et facilitant la communication entre des millions de machines à travers le monde. En 1990, avec la mise hors service d'ARPANET, le TCP/IP était devenu le standard mondial, et l’Internet, tel que nous le connaissons aujourd'hui, était en route pour connecter des utilisateurs et des entreprises à une échelle sans précédent.

## Le Rôle Crucial de la Documentation dans la Croissance de l'Internet

L'une des raisons principales de la croissance rapide de l'Internet a été l'accès libre et gratuit aux documents essentiels, en particulier les spécifications des protocoles. Dès ses débuts, l'Internet a été influencé par la tradition académique de publication ouverte des idées et des résultats, ce qui a facilité l'échange d'informations au sein de la communauté scientifique. Cependant, le processus formel de publication universitaire était trop lent pour répondre aux besoins d'innovation rapide exigés par le développement de réseaux. En 1969, une avancée importante fut réalisée avec la création des Demandes de Commentaires (RFC), mises en place par S. Crocker à l'UCLA. Ces mémos informels permettaient un partage rapide d'idées entre chercheurs. Initialement distribuées par courrier postal, les RFC ont rapidement évolué vers une version électronique grâce au protocole FTP, et aujourd'hui, elles sont accessibles en ligne via le Web. Jon Postel, responsable de l'administration des RFC et de l'attribution des numéros de protocoles, a joué un rôle clé dans cette gestion jusqu'à son décès en 1998. L'objectif des RFC était de créer un cycle d'évaluation collaborative où chaque proposition générait des retours et de nouvelles idées, aboutissant à un consensus. Ce consensus menait ensuite à la création de spécifications officielles, servant de base à la mise en œuvre technique des protocoles. Au fil du temps, les RFC sont devenus des documents de référence essentiels pour la norme des protocoles Internet. En plus des RFC normatifs, il existe encore des RFC informatifs, qui proposent des alternatives ou des explications supplémentaires sur les protocoles. L’accès libre à ces documents a contribué à la diffusion des spécifications dans les milieux universitaires et à leur utilisation par des entreprises développant de nouveaux systèmes. Le courrier électronique a joué un rôle déterminant dans l'évolution des spécifications des protocoles. Il a permis un échange rapide d’idées entre chercheurs situés à travers le monde, modifiant le processus de collaboration. L’utilisation de listes de diffusion spécialisées est devenue un outil clé dans le développement des RFC, avec l'Internet Engineering Task Force (IETF) et ses plus de 75 groupes de travail, chacun concentré sur un aspect spécifique du développement d'Internet. Lorsque le consensus est atteint sur un document, il est publié sous forme de RFC. Ainsi, le partage de l'information sur la conception et le fonctionnement de l'Internet, facilité par les RFC, a été essentiel pour l'expansion de l'Internet. Cette approche ouverte et collaborative reste au cœur de l'évolution future de l'Internet, permettant une innovation continue et un développement technologique mondial.

# Le réseau internet à notre époque

## La structure d'internet

Le principe est simple on a ce qu'on appel un noeud qui est un appareils ( téléphones portables, ordinateur , tableau , objet qui peut se conecter à internet) qui peuvent envoyés des informations et en ressevoir . Un réseau est un groupe de noeuds , donc par exmple dans votre maison il y a un réseau qui regroupe tout les appareils pouvants communiqué à Internet.
Chaque noeud a nom , une adresse , qu'on appel adresse IP.Les noeuds d'un même réseau peuvent communiquer entre eux en fournissant l'dresse IP de la destination . Par exmple la machine 1 veux communiquer avec la machine 2 . Elle va envoyé ceci . 

```sh
De 1 
A 2 
Message : Coucou
```
Ainsi l'adresse IP permet au machine de communiquer entre elle.

Mais comment on fait pour pouvoir communiquer avec le voisin qui utiliser un autre reseau ?

C'est la qu'intervient les routeurs (la box internet) , ils permettent de communiquer d'un réseau a un autre . Les routeurs permettent ainsi d'envoyé des paquets d'IP .

C'est pourquoi on dit souvent qu'Internet est un réseau de réseau !

Les noeuds qui fournisse des services sur un réseau sont appelés des serveurs . Un serveur est donc un noeud qui aceptent les connextions provennats d'autre noeuds sur un réseau qui habituellement transmet de l'information , la reçoit , l'analyse en tant que service ou application . Tous ce qui est serveur de jeux en ligne , les hebergeurs de site web et les services de transmissions de mails sont des exemple de noeud serveurs . 

Un noeud qui utilise un noeud serveur est dit client . Quand on consulte ses mails on utilise un client pour se connectée au serveur . 

Il existe plusieur type de réseau que l'on peux représenter sous forme de graphe . 

Les réseaux dit centralisée, décentralisée,distribuée 







Source : [InternetSociety](https://www.internetsociety.org/fr/internet/history-internet/brief-history-internet/) , [Wikipedia](https://fr.wikipedia.org/wiki/Histoire_d%27Internet)
Connaissez-vous vraiment internet par Article 19