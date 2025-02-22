+++
title= "Insalée Node.js avec un shell fish"
date=2024-01-06
draft=false
+++

Si vous allez sur le site de [Node.js](https://nodejs.org/fr/download/package-manager) vous trouverez des commandes bash. Si vous les exécutez, votre shell fish ne sera pas content.

## Brew

Nous allons utiliser Brew. Tout d'abord, nous allons l'installer :

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Puis, nous allons dans le fichier de config fish :

```sh
nano ~/.config/fish/config.fish
``` 
et vous allez y mettre ces lignes de commande :
```sh
set -gx PATH /home/linuxbrew/.linuxbrew/bin $PATH
eval ( /home/linuxbrew/.linuxbrew/bin/brew shellenv )
```

Ce qui nous donne ceci :

```sh
if status is-interactive
    set -gx PATH /home/linuxbrew/.linuxbrew/bin $PATH
    eval ( /home/linuxbrew/.linuxbrew/bin/brew shellenv )
end
```
On va recharger la config fish :

```sh
source ~/.config/fish/config.fish
```
On vérifie que Brew est bien installé :

```sh
brew --version
```
## Node.js

Une fois Brew installé, on va installer Node.js :

```sh
brew install node
```

Et voilà, Node.js est installé. Il suffit de vérifier que tout a bien fonctionné :
```sh
node -v
nmp -v
```
