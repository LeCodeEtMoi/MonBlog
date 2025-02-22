+++
title = "Faire un blog avec Zola (Niveau Intermédiaire)"
date = 2024-01-06
draft = false
+++

# Réaliser un blog

Vous avez peut-être envie de partager vos connaissances ou bien de vous exprimer sur des sujets d'actualité... Vous voulez donc votre endroit à vous (donc personnalisé) pour pouvoir partager tout ce que vous voulez sur internet. Vous avez les réseaux sociaux, mais cela n'est pas assez personnalisable. Je vous propose donc de faire un blog. Il y a bien des sites qui permettent de maintenir un blog, mais cela reste peu personnalisable.

Je vous propose donc de vous accompagner de A à Z sur la création d'un blog. Pour cela, il vous faudra un ordinateur et rien d'autre.

Nous allons nous diriger vers des générateurs de sites statiques. Nous avons donc le choix entre Hugo et Zola. Nous allons nous intéresser dans ce tutoriel à Zola. Nous avons donc deux choix qui s'offrent à nous : soit nous construisons nous-mêmes notre thème, soit nous personnalisons un thème déjà créé. Nous allons partir sur la personnalisation d'un thème, car nous ne voulons pas trop nous casser la tête :) . Voyez, ce blog utilise le thème Hermit_Zola, mais il diffère de la démo. Je l'ai adapté à mes propres besoins. Je vous laisse donc choisir parmi tous les thèmes qu'il propose.

## Faire tourner le blog en local

Une fois le thème choisi, nous allons faire tourner notre blog en local (cela veut dire qu'il tourne sur notre PC, vous pouvez le voir car vous avez une adresse un peu particulière). Pour cela, nous allons tout d'abord créer un projet Zola avec la commande suivante dans votre terminal :

```sh
zola init le_nom_de_votre_blog
```

Vous allez ensuite avoir une série de questions auxquelles je vous conseille de répondre "oui".

Entrez dans le bon répertoire, puis nous allons lancer le serveur :

```sh
zola serve
```

Dans votre terminal, une URL devrait vous être donnée. Cliquez dessus et voilà, vous avez votre projet qui fonctionne.


# Installer le thème

Il faut à présent mettre votre thème. Dans le dossier ```themes``` de votre blog, dans le terminal, récupérez le lien qui redirige vers le dépôt GitHub, puis écrivez la commande :

```sh
git clone le_nom_du_dépôt
```

Installez Git si nécessaire.

Rafraîchissez la page et vous verrez le site comme dans la page de démo. Je vous laisse la documentation de votre projet pour l'adapter au mieux à vos envies. Tous vos articles s'écrivent sous forme Markdown, c'est de l'HTML simplifié (je le dis car vous pouvez mettre de l'HTML dans des fichiers Markdown

# Mettre en ligne votre site web

Pour mettre en ligne notre blog gratuitement, nous allons utiliser GitHub Pages. Tout d'abord, créez un compte ou connectez-vous. Vous allez créer un nouveau dépôt, puis le cloner avec :

```sh 
git clone le_nom_de_votre_dépôt
```

Ajoutez tous les dossiers à votre dossier cloné, puis allez dans votre terminal dans votre dossier cloné et effectuez les commandes suivantes :

```sh
git add .
git commit -m "votre_message"
git push origin main
```

Ensuite, dans votre dépôt, rafraîchissez la page. Normalement, tous vos documents devraient être dans votre dépôt. Nous devons maintenant créer un workflow. Allez dans Actions et créez un nouveau workflow avec le contenu suivant :

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

Créez un token et mettez-le dans votre projet. Puis, faites un git pull origin main pour mettre le workflow dans votre projet et effectuez les commandes suivantes :

```sh
git add .
git commit -m "votre_message"
git push origin main
```

Ensuite, allez dans les paramètres de GitHub Pages et mettez la branche ```gh-pages```. Attendez un peu et cliquez sur le lien.

**ATTENTION : Vérifiez bien que l'URL de votre site dans votre fichier config.toml correspond à l'URL de GitHub.**

Si vous avez des problèmes pour faire fonctionner votre blog sur GitHub, prenez exemple sur mon dépôt Git.





