+++
title= "Faire un blog avec Zola ( Niveaux Intermediare )"
date=2024-01-06
draft=false
+++


# Réaliser un blog 

Vous avez peut être envie de partagé vos connaissances ou bien de vous exprimé sur des sujet d'actualité ... Vous voulez donc votre endroit à vous ( donc personalisé ) pour pouvoir partager tout ce que vous voulez sur internet . Vous avez les reéseau mais ceci n'est pas assez personalisable . Je vous propose donc de faire un blog . Il y a un bien site qui permet de maintenire un blog mais cela reste pas très personalisable . 

Je vous propose donc de vous acompagnée de A à Z sur la création d'un blog . Pour cela il vous faudra un ordinateur et rien d'autre . Nous allons faire un site static c'est a dire que l'utilisateur ne peux pas avoir espace que que lui peux voir .

Nous allons nous diriger vers des générateur de site statique nous avons donc le choix Hugo et Zola .... Nous nous allons nous interresser sur ce tutoriels à Zola . Nous avons donc 2 choix qui s'offre à nous . Soit on construit nous meme notre theme soit on personalise un theme déja créé . Nous allons partie sur la personalisation d'un thème on veux pas trop ce casser la tête :) . Voyez vous ce blog utilise le theme Hermit_Zola mais il different de cela de la démo je l'ai adapté à mes propre besoin . Je vous laisse donc choisir parmis tout les thme qu'il propose .


# 
 Une fois choisi, nous allons donc faire tourné notre blog en local ( sa ve dire qu'il tourne sur notre pc , vous pouvez le voire car vous avez que adresse un peu particulière ) pour cela on allons tout d'abords tout d'abors créé un projet zola avec la commade dans votre terminal
``` zola init le_nom_de_votre_blog ```
Vous allez avoir ensuite une serie de question ou je vous conseills de repondre tout par oui .

Entrer dans le bon repertoire , puis nous allons lancer le server ``` zola serve```

Dans votre terminale on est censé vous donner une url cliqué dessus et voilà vous avez projet qui fonctionne 

# Le theme 

Il faut a présent mettre votre theme . Alors dans le dossier theme de votre blog dans le terminal . Recupere le lien qui redirige vers le dépot github puis ecriver la commade ``` git clone le nom_du_dépot ``` installé git si néssaire .

Rafrechiser la page et vous verez le site comme dans la page de démo . Je vous laisse la doc de votre projet pour l'adapter au mieux a vos envie . Tout vos articles vous s'ecrire sous le forme markdown c'est de l'HTML en s'implifier ( je le dit car vous pouvez mettre du l'html dans des fichiers markdown)

# Rendre en ligne votre site web 

Pour mettre en ligne notre blog gratuitement nous allons utiliser la solution suivant qui github page . Alors tout d'abors créé vous un compte ou connectez vous . Vous allez créé un nouveaux dépot puis vous allez le cloner avec ``` git clone le nom_de_votre_dépot ``` ajouter tout les dossiers a votre dossier clone ensuite allez dans votre terminal dans votre dossier cloner et effectuez les commande suivante ``` git add .``` ``` git commit votre_message ``` puis ``` git push origin main ``` . Alors dans votre depot et rafraichiser la page . Normalement tout vos documents devrait être dans votre dépots . Puis nous devons créé un workflow nous allons new worflow et collez ceci 

``` 
on: push
name: Build and deploy GH Pages
jobs:
  build:
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - name: checkout
        uses: actions/checkout@v4
      - name: build_and_deploy
        uses: shalzz/zola-deploy-action@v0.17.2
        env:
          # Target branch
          PAGES_BRANCH: gh-pages
          # Provide personal access token
          TOKEN: ${{ secrets.TOKEN }}
          # Or if publishing to the same repo, use the automatic token
          #TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Vous allez créé un token et le mettre dans votre projet . Puis ``` git pull origin main ``` pour mettre le workflow dans notre projet effectuez les commandes suivante ``` git add .``` ``` git commit votre_message ``` puis ``` git push origin main ``` .

Il faut ensuite allez dans github page et mettre la branche gh-pages attendez un peu et cliquer sur le lien . 
#### ATTENTION : Verifier bien que votre le lien de votre url dans votre fichier config.toml corespont à l'url de github . 

Si vous avez des problèmes pour faire fonctionner fotre blog sur github prennez exemple sur mon dépot git .


