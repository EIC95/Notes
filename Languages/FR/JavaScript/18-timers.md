# Timers en JavaScript

Les timers en JavaScript permettent de programmer l'exécution de code après un certain délai ou de manière répétée à intervalles réguliers. Les deux principales méthodes sont `setTimeout` et `setInterval`.

## `setTimeout`

`setTimeout` exécute une fonction une seule fois après un délai spécifié en millisecondes.

### Syntaxe

```javascript
setTimeout(callback, delay);
```

- **callback** : La fonction à exécuter.
- **delay** : Le délai avant l'exécution de la fonction (en millisecondes).

### Exemple

```javascript
setTimeout(() => {
  console.log("Exécuté après 2 secondes");
}, 2000);
```

## `setInterval`

`setInterval` exécute une fonction de manière répétée à intervalles réguliers spécifiés en millisecondes.

### Syntaxe

```javascript
setInterval(callback, interval);
```

- **callback** : La fonction à exécuter.
- **interval** : L'intervalle de temps entre chaque exécution (en millisecondes).

### Exemple

```javascript
const intervalId = setInterval(() => {
  console.log("Exécuté toutes les 3 secondes");
}, 3000);
```

## Annuler les Timers

### `clearTimeout`

`clearTimeout` annule un timer créé avec `setTimeout`.

### Syntaxe

```javascript
clearTimeout(timeoutId);
```

- **timeoutId** : L'identifiant du timer retourné par `setTimeout`.

### Exemple

```javascript
const timeoutId = setTimeout(() => {
  console.log("Cette fonction ne sera pas exécutée");
}, 5000);

clearTimeout(timeoutId);
```

### `clearInterval`

`clearInterval` annule un timer créé avec `setInterval`.

### Syntaxe

```javascript
clearInterval(intervalId);
```

- **intervalId** : L'identifiant du timer retourné par `setInterval`.

### Exemple

```javascript
const intervalId = setInterval(() => {
  console.log("Cette fonction sera arrêtée");
}, 3000);

clearInterval(intervalId);
```

En utilisant ces méthodes, vous pouvez contrôler le timing de l'exécution de votre code en JavaScript de manière précise et flexible.