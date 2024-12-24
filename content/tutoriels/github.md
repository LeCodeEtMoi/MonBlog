+++
title="GitHub"
date=2024-01-06
draft=false
+++

# 1. Introduction à GitHub

Qu'est-ce que GitHub ? : GitHub est une plateforme basée sur le cloud où vous pouvez stocker, partager et travailler avec d’autres pour écrire du code.

Différence entre Git et GitHub : Clarifier que Git est un système de contrôle de version tandis que GitHub est un service hébergé pour les projets utilisant Git.

2. Création d'un compte GitHub

    - Allez sur la page pour créé son compte [ici](https://github.com/signup)

    - Entrer votre email , votre mot de passe , puis votre username suiver les étapes quoi ...

    Une fois votre compte créé vous pover modifier votre profil en allant sur la photo profil > Your Profile
    Ensuite allez sur votre image de profil (le crayon pour editer) et vous pourez ajouter votre bio , localisation , lier des réseaux sociaux ...

3. Les bases de Git

    Installation de Git : Fournir des instructions pour installer Git sur Windows, macOS et Linux.
    Commandes Git essentielles :

    ```
    git init
    ``` 
    - Initialiser un nouveau dépôt Git.

    ```
    git clone nom_du_dépôt_git

    # Exemple git clone https://github.com/LeCodeEtMoi/Matrix-Enigme
    ```
    - Cloner un dépôt existant.

    ```
    git add
    ```
    - Ajouter des fichiers au suivi.

    ```
    git commit -m "Votre message"
    ```
    - Enregistrer les changements dans l'historique.

    ```
    git push
    ``` 

    - Envoyer les changements vers GitHub.

    ```
    git pull
    ``` 
    - Récupérer les dernières modifications depuis GitHub.

4. Créer un dépôt sur GitHub

    Créer un nouveau dépôt : Instructions pour créer un nouveau dépôt via l'interface web.

    - Cliquez sur le "+" à côté de votre photo de profil.
    - Sélectionnez "New repository".
    - Remplissez les champs avec une astérisque ( * ) obligatoire.
    - Appuyez sur le bouton "Create repository".


    Ajouter un fichier README : 

    - **Introduction au projet** : Le fichier README permet de donner une vue d'ensemble du projet, expliquant son but, son fonctionnement, et ses fonctionnalités. Il sert souvent de première impression pour les visiteurs qui découvrent le projet, qu'il s'agisse de collaborateurs potentiels ou d'utilisateurs.

    - **Documentation** : Il fournit un espace pour détailler comment installer, configurer et utiliser le projet. Cela peut inclure des instructions d'installation, des exemples de code, des dépendances nécessaires, et plus encore. Une bonne documentation facilite grandement la prise en main du projet, surtout pour les nouveaux contributeurs.

    Configurer les paramètres du dépôt : Paramètres de base, comme la visibilité (public/privé) et l'ajout de collaborateurs.

    - **Engagement de la communauté** : Un fichier README bien rédigé peut aider à attirer et retenir des contributeurs. Il montre que le projet est bien organisé et accueillant, ce qui encourage d'autres développeurs à s'y impliquer.

    - **Informations de licence et de contribution** : Le README peut aussi contenir des informations sur la licence du projet (par exemple, MIT, GPL) ainsi que des consignes sur la manière de contribuer au projet, en détaillant les étapes à suivre pour soumettre des pull requests ou signaler des problèmes.

    - **Visibilité et SEO** : Sur GitHub, le fichier README est souvent ce qui apparaît en premier sur la page d'accueil d'un dépôt. Il joue un rôle clé dans le référencement du projet, car il contient des mots-clés qui améliorent la visibilité du projet sur les moteurs de recherche de GitHub et externes.

5. Collaborer sur GitHub
    
    ###  **Fork** : Un **fork** est une copie d’un projet GitHub sur ton propre compte. Cela te permet de modifier le projet librement sans toucher au dépôt original.

    Étapes pour forker un projet:

    - Trouve un dépôt à forker : Connecte-toi à GitHub et rends-toi sur le dépôt que tu veux copier.
    - Clique sur "Fork" : En haut à droite de la page du dépôt, tu verras un bouton "Fork". Clique dessus.
    - Ton fork est créé : GitHub crée une copie du dépôt dans ton propre compte.

    Travailler avec ton fork:

    - Clone ton fork sur ton ordinateur :
    ```bash
    git clone https://github.com/ton-compte/nom-du-projet.git
    cd nom-du-projet
    ```
    - Fais des modifications sur ton code localement.


    ### **Pull Request** : Une **Pull Request** est une demande pour que tes changements soient intégrés dans le dépôt original. Elle permet aux mainteneurs du projet de réviser et discuter de tes modifications avant de les accepter.

    Étapes pour créer une Pull Request:

    - **Ajoute un lien entre ton fork et le projet original** : Cela te permettra de récupérer les mises à jour du dépôt original.

    ```bash
    git remote add upstream https://github.com/auteur-original/nom-du-projet.git
    git fetch upstream
    ```

    - **Fais tes modifications** : Crée une nouvelle branche pour organiser ton travail.
    ```bash
    git checkout -b ma-nouvelle-fonctionnalité
    # Fais tes modifications...
    git add .
    git commit -m "Ajout de ma nouvelle fonctionnalité"
    ```

    - **Pousse ta branche sur GitHub** :
    ```bash
    git push origin ma-nouvelle-fonctionnalité
    ```

    - **Crée une Pull Request** :
        - Va sur ton fork sur GitHub.
        - Clique sur "Compare & Pull Request".
        - Ajoute un titre et une description expliquant les changements.
        - Clique sur "Create Pull Request".

    **Bonnes pratiques pour une Pull Request** : 

    - Donne un titre clair (par exemple : "Ajout d’un bouton de partage").
    - Décris les modifications dans le détail.
    - Si possible, ajoute des captures d’écran ou des GIFs pour illustrer les changements visuels.

    ### **Issue** : Une **Issue** est un moyen de signaler un problème ou de demander une nouvelle fonctionnalité sur GitHub. Elle permet une discussion ouverte entre les contributeurs.

    Étapes pour créer une **Issue**:

    - Va dans l’onglet "Issues" du dépôt GitHub.
    - Clique sur "New Issue".
    - Ajoute un titre clair et descriptif.
    - Dans la description, explique :
        - **Le problème** : Si c’est un bug, donne des détails sur comment le reproduire.
        - **La solution attendue** : Si c’est une fonctionnalité, explique ce que tu souhaites.
    - Clique sur "Submit new issue".

    Bonnes pratiques

    - Sois précis : "Le bouton X ne fonctionne pas quand je fais Y" est mieux que "Ça ne marche pas".
    - Ajoute des captures d’écran ou des logs pour aider les mainteneurs à comprendre rapidement le problème.

    ### Commentaires et révisions des Pull Requests

    Fork, Pull Requests, et Issues :
        Fork : Expliquer ce qu'est un fork et comment en créer un.
        Pull Request (PR) : Comment proposer des changements à un projet.
        Issues : Comment signaler des bugs ou demander des fonctionnalités.
    Commentaires et Révisions : Comment commenter et réviser les pull requests.

6. Utilisation avancée de GitHub

    Branches : Explication de la gestion des branches (création, fusion).
    GitHub Actions : Introduction aux CI/CD avec GitHub Actions.
    Pages GitHub : Hébergement d'un site statique via GitHub Pages.
    GitHub Projects : Utilisation de tableaux Kanban pour la gestion de projet.

7. Bonnes pratiques sur GitHub

    Commits atomiques : Faire des commits clairs et fréquents.
    Rédaction de messages de commit : Importance de messages explicites.
    Utilisation des fichiers .gitignore : Ignorer les fichiers inutiles pour le dépôt.

8. Sécurité sur GitHub

    Gestion des clés SSH : Comment configurer des clés SSH pour sécuriser les interactions avec GitHub.
    Maintien de la sécurité des dépôts : Comment gérer les permissions, éviter l'exposition accidentelle d'informations sensibles.

9. Ressources supplémentaires

    Documentation officielle de GitHub : Lien vers la documentation officielle.
    Tutoriels et cours en ligne : Recommandations de cours ou vidéos pour approfondir.
    Communautés et forums : Où poser des questions et trouver de l'aide.

10. FAQ GitHub

    Questions fréquemment posées : Réponses aux questions courantes des débutants, comme "Comment restaurer une branche supprimée ?" ou "Comment résoudre un conflit de fusion ?".