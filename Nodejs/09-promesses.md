# Node.js Promesses

## Introduction

Les **promesses** sont une amélioration des callbacks pour gérer les opérations asynchrones de manière plus lisible et plus facile à maintenir. Une promesse représente la valeur d'une opération asynchrone qui peut être disponible maintenant, dans le futur ou jamais. Elle permet de chaîner des opérations et de gérer les erreurs plus proprement.

---

## Qu'est-ce qu'une Promesse ?

Une **promesse** est un objet représentant la future valeur d'une opération asynchrone. Une promesse peut être dans l'un des trois états suivants :
1. **Pending** (En attente) : L'opération asynchrone est en cours.
2. **Fulfilled** (Résolue) : L'opération a réussi et la promesse a une valeur.
3. **Rejected** (Rejetée) : L'opération a échoué et la promesse contient une raison de l'échec (généralement une erreur).

---

## Création d'une Promesse

Une promesse est créée avec le constructeur `Promise`. Ce constructeur prend une fonction qui reçoit deux arguments : `resolve` et `reject`. Le `resolve` est appelé si l'opération réussit, et `reject` est appelé si l'opération échoue.

### Exemple :

```javascript
let promise = new Promise(function(resolve, reject) {
  let success = true;  // Variable simulant le succès ou l'échec

  if (success) {
    resolve("Opération réussie");
  } else {
    reject("Opération échouée");
  }
});
```

---

## Utilisation des Promesses

Une fois une promesse créée, vous pouvez utiliser les méthodes `then()` et `catch()` pour gérer les résultats.

### `then()`

La méthode `then()` est appelée lorsque la promesse est **résolue** (c'est-à-dire que l'opération a réussi). Elle prend une fonction de retour qui reçoit la valeur résolue.

### `catch()`

La méthode `catch()` est utilisée pour gérer les erreurs, c'est-à-dire quand la promesse est **rejetée**. Elle prend une fonction qui reçoit la raison du rejet (souvent une erreur).

### Exemple :

```javascript
let promise = new Promise(function(resolve, reject) {
  let success = true;

  if (success) {
    resolve("Opération réussie");
  } else {
    reject("Opération échouée");
  }
});

promise
  .then(function(result) {
    console.log(result);  // "Opération réussie"
  })
  .catch(function(error) {
    console.log(error);   // "Opération échouée"
  });
```

---

## Chaînage de Promesses

Une des forces des promesses est leur capacité à être chaînées. Cela permet de gérer plusieurs opérations asynchrones de manière plus lisible que les callbacks imbriqués.

### Exemple de Chaînage :

```javascript
let promise1 = new Promise(function(resolve, reject) {
  resolve(1);
});

let promise2 = promise1
  .then(function(result) {
    console.log(result);  // Affiche 1
    return result + 1;    // Résout avec 2
  })
  .then(function(result) {
    console.log(result);  // Affiche 2
    return result + 1;    // Résout avec 3
  })
  .then(function(result) {
    console.log(result);  // Affiche 3
  });
```

---

## Gestion des Erreurs avec `catch()`

Si une erreur se produit à n'importe quel moment dans la chaîne de promesses, elle sera capturée par la méthode `catch()`.

### Exemple :

```javascript
let promise = new Promise(function(resolve, reject) {
  let success = false;  // Variable simulant une erreur

  if (success) {
    resolve("Opération réussie");
  } else {
    reject("Opération échouée");
  }
});

promise
  .then(function(result) {
    console.log(result);  // Ne sera pas exécuté
  })
  .catch(function(error) {
    console.log(error);   // "Opération échouée"
  });
```

---

## Promesses avec `async`/`await`

Les **`async`** et **`await`** sont des mots-clés qui permettent d'utiliser des promesses de manière encore plus lisible, en écrivant du code asynchrone de manière synchrone.

- **`async`** : Marque une fonction comme étant asynchrone, ce qui signifie qu'elle renverra toujours une promesse.
- **`await`** : Attend la résolution de la promesse avant de continuer l'exécution du code.

### Exemple avec `async`/`await` :

```javascript
function attendre() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("Opération terminée");
    }, 2000);
  });
}

async function maFonction() {
  let result = await attendre();  // Attend la résolution de la promesse
  console.log(result);  // "Opération terminée"
}

maFonction();
```

Dans cet exemple, la fonction `attendre()` retourne une promesse, et `await` attend que la promesse soit résolue avant d'afficher le résultat.
