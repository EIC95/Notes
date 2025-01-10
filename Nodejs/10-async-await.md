# Node.js Async / Await

## Introduction

Les mots-clés **`async`** et **`await`** sont utilisés pour travailler avec des **promesses** de manière plus lisible et synchrone. Ils permettent d'écrire du code asynchrone de façon qui ressemble davantage à du code synchrone, ce qui rend le code plus facile à comprendre et à maintenir.

---

## Qu'est-ce qu'une fonction `async` ?

Une fonction marquée avec le mot-clé **`async`** est une fonction qui retourne toujours une promesse. Si la fonction retourne une valeur, cette valeur est automatiquement enveloppée dans une promesse résolue.

### Exemple :

```javascript
async function maFonction() {
  return "Bonjour, Node.js!";
}

maFonction().then(result => console.log(result));  // Affiche "Bonjour, Node.js!"
```

Même si la fonction retourne directement une valeur, cette valeur est traitée comme une promesse résolue.

---

## Qu'est-ce que `await` ?

Le mot-clé **`await`** est utilisé pour attendre la résolution d'une promesse. Il ne peut être utilisé qu'à l'intérieur d'une fonction marquée **`async`**. Lorsque vous utilisez **`await`**, l'exécution de la fonction est "mise en pause" jusqu'à ce que la promesse soit résolue, ce qui permet de travailler de manière synchrone tout en utilisant des opérations asynchrones.

### Exemple :

```javascript
async function attendre() {
  let promesse = new Promise(resolve => {
    setTimeout(() => resolve("Opération terminée"), 2000);
  });
  
  let result = await promesse;  // Attends la résolution de la promesse
  console.log(result);  // Affiche "Opération terminée" après 2 secondes
}

attendre();
```

---

## Exemple Complet avec `async` et `await`

Supposons que nous avons une fonction asynchrone qui récupère des données à partir d'une API. Nous utiliserons **`async`** et **`await`** pour gérer cette opération.

### Exemple :

```javascript
async function fetchData() {
  let data = await fetch('https://jsonplaceholder.typicode.com/posts/1');
  let jsonData = await data.json();  // Attend que les données soient converties en JSON
  console.log(jsonData);  // Affiche les données récupérées
}

fetchData();
```

Dans cet exemple, la fonction `fetchData()` récupère des données depuis une API. Nous utilisons **`await`** pour attendre que la requête se termine et que les données soient converties en JSON avant de les afficher.

---

## Gestion des erreurs avec `try` / `catch`

Lorsque vous utilisez **`async`** et **`await`**, il est recommandé de gérer les erreurs avec un bloc **`try` / `catch`**. Si une promesse est rejetée ou qu'une erreur se produit dans une fonction **`async`**, elle sera capturée par le bloc **`catch`**.

### Exemple :

```javascript
async function fetchData() {
  try {
    let data = await fetch('https://jsonplaceholder.typicode.com/posts/1');
    let jsonData = await data.json();
    console.log(jsonData);
  } catch (error) {
    console.log('Une erreur est survenue:', error);
  }
}

fetchData();
```

Dans cet exemple, si une erreur se produit lors de la récupération des données ou de la conversion en JSON, elle sera capturée et affichée dans la console.

---

## Avantages de `async` / `await`

1. **Lisibilité améliorée** : Le code est plus facile à comprendre, car il ressemble à du code synchrone.
2. **Gestion des erreurs simplifiée** : L'utilisation de **`try` / `catch`** est plus simple pour capturer et gérer les erreurs que les méthodes **`then()`** et **`catch()`** des promesses.
3. **Meilleure gestion des opérations asynchrones** : Vous pouvez chaîner plusieurs appels asynchrones sans avoir à imbriquer des callbacks ou des promesses.
