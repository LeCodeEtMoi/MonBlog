+++
title="Sublime Texte"
date=2025-07-16
draft=false
+++

Sublime Text est un éditeur de texte léger, rapide et puissant pour les développeurs, disponible sur Windows, macOS et Linux.

# Instalation

A voir en fonction de la distribution linux : [ici](https://www.sublimetext.com/docs/linux_repositories.html)


# Un peu de vocabulaire

-  Zone d’édition : Là où vous écrivez le code.

- Sidebar : L’arborescence des fichiers du projet.

- MiniMap : Aperçu vertical du fichier à droite.

- Tabs : Onglets pour naviguer entre les fichiers ouverts.

# Raccourci de base

Ouvrir la palette de commande (changer de thème, installer un plugin, etc.) : ```Ctrl + Shift + P```

Aller à un fichier : ```Ctrl + P```

Aller à une ligne : ```Ctrl + G```

Multi-cursor : ```Ctrl + Click```

Commenter : ```Ctrl + /```
 
Sidebar toggle	: ```Ctrl + K``` puis ```Ctrl + B```



# Customisation rapide 

```Preferences → Settings```

On va avoir 2 panneaux

- à gauche : les réglages par défaut (à ne pas modifier),

- à droite : vos réglages personnels (à modifier librement).

Voici ce que l'on peut faire :

A vous de changer les valeurs pour vos préférences

## Lisibilité 

```"font_size": 14``` → augmente la taille du texte.

```"font_face": "Fira Code"``` → police avec ligatures pour le code (fonctionne mieux si elle est installée)

```"line_padding_top": 2``` et ```"line_padding_bottom":```  → ajoute de l’air entre les lignes.

## Mise en forme

```"word_wrap": true``` → active le retour à la ligne automatique.

```"wrap_width": 120``` → largeur maximale avant de couper la ligne (confort visuel).

```"tab_size": 2``` → taille d'une tabulation

```"translate_tabs_to_spaces": true``` → remplace les tabs par des espaces (standard moderne).

## Visualisation & confort :

```draw_white_space": "selection"``` → montre les espaces quand on sélectionne.

```"highlight_line": true``` → surligne la ligne active.

```highlight_modified_tabs": true``` → indique visuellement les fichiers non sauvegardés.

## Gestion des fichiers

```"ensure_newline_at_eof_on_save": true``` → ajoute une ligne vide à la fin (bonne pratique).

```"trim_trailing_white_space_on_save": true``` → supprime les espaces inutiles à la fin.


```"detect_indentation": true``` → adapte automatiquement l’indentation à l’ouverture.

## Parenthèses & balise

```"match_brackets": true``` → surligne les paires de parenthèses.

```"match_brackets_square": true```, ```"match_brackets_angle": true```, etc → idem pour tous types de parenthèses.


## Navigation

```"scroll_past_end": true```→ permet de scroller après la fin d’un fichier (reposant visuellement).

```"fade_fold_buttons": false``` → rend les boutons de repli visibles en permanence.

## Apparence :

```"theme"``` → thème de l'interface (Default, Adaptive…)

```"color_scheme"``` → thème des couleurs du code (Mariana, Monokai…)

Exemple de configuration :

```json
{
  "font_size": 14,
  "line_padding_top": 2,
  "line_padding_bottom": 2,
  "font_face": "Fira Code",
  "word_wrap": true,
  "wrap_width": 120,
  "tab_size": 2,
  "translate_tabs_to_spaces": true,
  "draw_white_space": "selection",
  "highlight_line": true,
  "highlight_modified_tabs": true,
  "scroll_past_end": true,
  "fade_fold_buttons": false,
  "match_brackets": true,
  "match_brackets_angle": true,
  "match_brackets_braces": true,
  "match_brackets_content": true,
  "match_brackets_square": true,
  "auto_complete": true,
  "auto_match_enabled": true,
  "ensure_newline_at_eof_on_save": true,
  "trim_trailing_white_space_on_save": true,
  "detect_indentation": true,
  "default_line_ending": "unix",
  "theme": "Default.sublime-theme",
  "color_scheme": "Mariana.sublime-color-scheme"
}
```

On aussi ajouter des rêlges en fonction du langages utilisée (HTML, python, php, rust ...)

On va utiliser ce que Sublime appelle un fichier Syntax Specific Settings.

Allez dans un fichier du langage concerné (par exemple : un .py pour Python), puis faites :

```Preferences``` → ```Settings``` → ```Syntax``` ```Specific```

On va avoir une fichier JSON

Ce réglage ne s’appliquera qu’au langage actuel (ici : Python uniquement).

## Rêgle combinée

Supposons que vous aimiez :

- des tabs de taille 2 globalement

- mais 4 espaces pour Python

- et 2 pour HTML

On va gèrer ceci ainsi via User Settings globaux

```json
{
  "tab_size": 2,
  "translate_tabs_to_spaces": true,
  "font_size": 13,
  "word_wrap": true
}
```
Les rêlges spécifiques : 

Python.sublime-settings

```json
{
  "tab_size": 4
}
```

HTML.sublime-settings

```json
{
  "tab_size": 2
}
```
>Ces fichiers sont automatiquement placés dans :
Packages/User/Python.sublime-settings
Packages/User/HTML.sublime-settings


# Installer des extensions

- Activer Package Control

```Tools → Install Package Control```

- Installer un package 

```Ctrl+Shift+P``` → tapez ```Install Package```

Liste des extensions utils :

- Terminus (terminal intégré)

- SendCode

- Emmet (HTML/CSS rapide)

- AutoFileName (Auto-complétion des chemins de fichier)

- CSS3 (Syntaxe améliorée pour le CSS moderne
)

- JavaScriptNext (Meilleur support ES6+
)

- Vue Syntax Highlight (Syntaxe pour Vue.js

)

- GitGutter  (affiche les modifs Git)

- GitSavvy (Interface Git complète dans Sublime (commit, branch, diff, log, etc.)

- Anaconda (IDE Python complet : auto-complétion, linting, refactoring
)

- SublimeLinter (Système de linting générique pour tous langages
)

- Sidebar Enhancements	(Plus d’options dans la sidebar (renommer, copier, ouvrir terminal, etc.)
)

- A File Icon	 (Ajoute des icônes de fichiers dans la sidebar)

- AdvancedNewFile (Crée rapidement des fichiers dans des sous-dossiers)

- Bookmarks  (Naviguer entre des zones marquées dans le code)

- Origami (Gestion avancée des splits (multi-panneaux)

- All Autocomplete (Complète avec tout le contenu ouvert, pas seulement le fichier courant)

- CodeComplice (Complétion intelligente basée sur le langage (fonctionne avec certains outils externes)

- TrailingSpaces (Surbrillance (et suppression automatique) des espaces inutiles)

- DocBlockr	(Génère automatiquement des commentaires de documentation pour les fonctions)

- Alignment (Aligne des blocs de code proprement (Ctrl + Alt + A)

- MarkdownEditing (Édition stylée et fluide pour les fichiers .md)

- Color Highlighter	(Affiche visuellement les couleurs définies (ex: #ff0000) dans le code
)


- BracketHighlighter	(Meilleure surbrillance des parenthèses, accolades, etc.)

- TrailingSpaces (Met en évidence les espaces inutiles en fin de ligne)


Pour + de packages :

```Preferences → Package Control → List Packages```


## Ajouter le theme dracula

C'est [ici](https://draculatheme.com/sublime)


## Créé un projet 

Un projet permet d'avoir une certaine configuration pour votre espace de travail


- On ouvre un dossier : ```File → Open Folder```

- ```Project → Save Project As…```

- Enregistrez un ```.sublime-project```

Fichier exemple:

```json
{
  "folders": [{ "path": "." }],
  "settings": {
    "tab_size": 2,
    "translate_tabs_to_spaces": true
  }
}
```