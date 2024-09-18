# Gestion des erreurs en JavaScript

JavaScript permet de gérer les erreurs à l'aide de blocs `try...catch`. Cela permet de capturer et traiter des exceptions qui pourraient survenir lors de l'exécution d'un programme.

## Syntaxe de base

### Exemple d'utilisation de `try...catch`

```javascript
try {
  // Code susceptible de provoquer une erreur
  let result = x / 0; 
  console.log(result);
} catch (error) {
  // Gérer l'erreur
  console.log("Une erreur est survenue : " + error.message);
}
```

Dans cet exemple, si une erreur survient dans le bloc `try`, le bloc `catch` s'exécute et affiche le message d'erreur.

## Utilisation de `throw`

Le mot-clé `throw` est utilisé pour générer une exception manuellement. Cela interrompt l'exécution du code normal et transfère le contrôle au bloc `catch`.

### Exemple avec `throw`

```javascript
try {
  let age = -1;
  if (age < 0) {
    throw new Error("L'âge ne peut pas être négatif");
  }
} catch (error) {
  console.log(error.message);
}
```

Dans cet exemple, une exception est déclenchée manuellement avec `throw` si la condition est remplie, et elle est gérée dans le bloc `catch`.

## Utilisation de `finally`

Le bloc `finally` est exécuté après les blocs `try` et `catch`, qu'une exception ait été levée ou non. Cela est utile pour effectuer des opérations de nettoyage, comme fermer des fichiers ou des connexions.

### Exemple avec `finally`

```javascript
try {
  let x = 5;
  let y = 0;
  console.log(x / y); // Cela provoque une erreur (division par zéro)
} catch (error) {
  console.log("Erreur détectée : " + error.message);
} finally {
  console.log("Le bloc finally s'exécute toujours.");
}
```

Le bloc `finally` est toujours exécuté, même si aucune erreur n'est survenue ou si une exception a été capturée.

### Récapitulatif
- `try`: Contient le code qui pourrait provoquer une erreur.
- `catch`: Gère l'erreur si une exception est levée dans `try`.
- `throw`: Génère une exception manuellement.
- `finally`: Exécute du code quel que soit le résultat du bloc `try`.