+++
title = "Installer WebStorm sur Arch Linux"
date = 2024-11-16
draft = false
+++

WebStorm est un environnement de développement intégré (IDE) développé par JetBrains, conçu principalement pour le développement web et JavaScript.

Pour l'installer, nous allons passer par [l'AUR](https://aur.archlinux.org/packages/webstorm).

Exécutez la commande suivante :  
```bash
yay -S webstorm
```

Cependant, il est possible que vous rencontriez une erreur du type : ![image webstorm erreur](./content/img/webstorm.png)

Vérifier si le JRE/JDK est installé correctement 


Pour résoudre ce problème, vérifiez si le package webstorm-jre est accessible. Utilisez la commande suivante :

Exécutez la commande suivante :  
```bash
yay -Qs webstorm-jre
```
Si le package n'apparaît pas, réinstallez-le avec :

```bash
yay -S webstorm-jre
```


