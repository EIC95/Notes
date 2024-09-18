# Promesses en JavaScript

Les promesses (ou `Promises` en anglais) en JavaScript sont un mécanisme pour gérer les opérations asynchrones. Elles permettent de traiter des valeurs qui ne sont pas encore disponibles mais le seront probablement dans le futur. Une promesse peut être dans l'un des trois états suivants :

- **Pending (En attente)** : L'état initial. La promesse est en cours de traitement et n'est ni résolue ni rejetée.
- **Fulfilled (Réussie)** : La promesse a été résolue avec succès. Une valeur est maintenant disponible.
- **Rejected (Rejetée)** : La promesse a échoué. Une erreur est disponible.

## Création d'une Promesse

Une promesse est créée en utilisant le constructeur `Promise`, qui accepte une fonction de rappel (callback) avec deux arguments : `resolve` et `reject`.

### Exemple

```javascript
const promesse = new Promise((resolve, reject) => {
  const succès = true;
  if (succès) {
    resolve('Opération réussie');
  } else {
    reject('Opération échouée');
  }
});
```

## Méthodes des Promesses

### `then(onFulfilled, onRejected)`

Permet de définir des fonctions à exécuter lorsque la promesse est remplie (résolue) ou rejetée. `onFulfilled` est appelé en cas de succès, et `onRejected` en cas d'échec.

#### Syntaxe

```javascript
promesse.then((valeur) => {
  // Code à exécuter en cas de succès
}, (erreur) => {
  // Code à exécuter en cas d'échec
});
```

#### Exemple

```javascript
promesse.then((message) => {
  console.log(message); // "Opération réussie"
}).catch((erreur) => {
  console.error(erreur); // Gère les erreurs
});
```

### `catch(onRejected)`

Permet de capturer les erreurs si la promesse est rejetée. Il est utilisé en chaîne après `then()` ou seul.

#### Syntaxe

```javascript
promesse.catch((erreur) => {
  // Code à exécuter en cas d'échec
});
```

#### Exemple

```javascript
promesse.catch((erreur) => {
  console.error(erreur); // "Opération échouée"
});
```

### `finally(onFinally)`

Permet d'exécuter du code après que la promesse ait été remplie ou rejetée, que ce soit avec succès ou non.

#### Syntaxe

```javascript
promesse.finally(() => {
  // Code à exécuter toujours, après then() ou catch()
});
```

#### Exemple

```javascript
promesse.finally(() => {
  console.log('Opération terminée');
});
```

## Enchaînement des Promesses

Les promesses permettent d'enchaîner les traitements pour gérer des séquences d'opérations asynchrones.

### Exemple

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log(data);
    return data;
  })
  .catch(error => {
    console.error('Erreur:', error);
  })
  .finally(() => {
    console.log('Requête terminée');
  });
```

Les promesses simplifient la gestion des opérations asynchrones en permettant de traiter les résultats ou les erreurs à différents moments, et d'exécuter du code de nettoyage ou finalisation après que l'opération soit terminée.