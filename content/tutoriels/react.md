+++
title="Les bases de react"
date=2024-02-22
draft=false
+++

# Qu'es ce que React ? 

React est une bibliothèque JavaScript pour créer des interfaces utilisateur. Il repose sur la composition de composants.

### Le composant de base

```sh
import React from 'react';

const Bonjour = () => {
  return <h1>Bonjour Maître</h1>;
};

export default Bonjour;
```

### Variable

Dans un composant React, on utilise souvent useState pour créer des variables réactives

```sh
import React, { useState } from 'react';

const Exemple = () => {
  const [compteur, setCompteur] = useState(0);

  return (
    <div>
      <p>Valeur : {compteur}</p>
      <button onClick={() => setCompteur(compteur + 1)}>+1</button>
    </div>
  );
};
```

### Dictionnaire

```sh
const personne = {
  nom: 'Spike',
  age: 27,
};

<p>{personne.nom} a {personne.age} ans</p>
```

### Listes (tableaux)

```sh
const noms = ['Spike', 'Faye', 'Jet'];

noms.map((nom, index) => (
  <p key={index}>{nom}</p>
));
```

> map() permet de boucler sur un tableau en JSX.

### Les boucles 

JSX ne supporte pas directement for, donc on utilise .map()

```sh
const nombres = [1, 2, 3];

return (
  <ul>
    {nombres.map(n => (
      <li key={n}>Nombre : {n}</li>
    ))}
  </ul>
);
```

### Les fonctions

#### Fonction classique

```sh
function direBonjour() {
  console.log("Bonjour Maître !");
}
```

#### Fonction fléchée (arrow function)

```sh
const direBonjour = () => {
  console.log("Bonjour Maître !");
};
```

#### Avec paramètres

```sh
const saluer = (nom: string) => {
  console.log(`Bonjour ${nom}`);
};
```

#### Fonctions dans un composant React

```sh
const Composant = () => {
  const cliquer = () => {
    alert("Tu as cliqué, Maître !");
  };

  return <button onClick={cliquer}>Clique ici</button>;
};
```

#### Retourner une valeur

```sh
const addition = (a: number, b: number) => {
  return a + b;
};

const resultat = addition(3, 5); // 8

```