# Fonctions en JavaScript

Les fonctions en JavaScript sont des blocs de code réutilisables définis avec le mot-clé `function`. Elles peuvent être créées de deux manières : avec une **déclaration de fonction** ou une **expression de fonction**.

## Déclaration de fonction

Une fonction est déclarée avec le mot-clé `function`, suivie du nom de la fonction, de paramètres entre parenthèses et du bloc de code entre accolades.

**Exemple :**

```javascript
function saluer(nom) {
    return "Bonjour " + nom;
}

console.log(saluer("Alice")); // "Bonjour Alice"
```

## Expression de fonction

Une fonction peut également être définie en tant qu'expression, et être stockée dans une variable.

**Exemple :**

```javascript
let direBonjour = function(nom) {
    return "Bonjour " + nom;
};

console.log(direBonjour("Bob")); // "Bonjour Bob"
```

## Fonctions fléchées

Les **fonctions fléchées** (introduites avec ES6) sont une syntaxe concise pour écrire des fonctions, particulièrement utile pour des fonctions simples. Elles omettent le mot-clé `function` et utilisent une flèche (`=>`) pour séparer les paramètres et le corps de la fonction.

**Exemple :**

```javascript
let multiplier = (a, b) => a * b;

console.log(multiplier(5, 3)); // 15
```

### Différences principales :

- Les **fonctions fléchées** n'ont pas leur propre `this`, elles héritent du `this` du contexte parent.
- Syntaxe plus courte, idéale pour les fonctions simples.

## Paramètres avec valeur par défaut

En JavaScript, vous pouvez définir des **valeurs par défaut** pour les paramètres d'une fonction. Si aucun argument n'est passé lors de l'appel de la fonction, la valeur par défaut est utilisée.

**Exemple :**

```javascript
function saluer(nom = "inconnu") {
    return "Bonjour " + nom;
}

console.log(saluer()); // "Bonjour inconnu"
console.log(saluer("Alice")); // "Bonjour Alice"
```

### Exemples pratiques

- **Déclaration de fonction avec un seul paramètre :**

```javascript
function double(x) {
    return x * 2;
}
console.log(double(4)); // 8
```

- **Fonction fléchée avec plusieurs paramètres :**

```javascript
let additionner = (x, y) => x + y;
console.log(additionner(2, 3)); // 5
```

- **Fonction avec des valeurs par défaut :**

```javascript
function multiplier(x, y = 1) {
    return x * y;
}
console.log(multiplier(5)); // 5 (y prend la valeur par défaut 1)
```