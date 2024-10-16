# Set en JavaScript

Un `Set` est une collection d'éléments uniques en JavaScript, permettant de stocker des valeurs sans duplication. Contrairement aux tableaux, les ensembles (Sets) ne permettent pas d'avoir des éléments en double et offrent des opérations efficaces pour vérifier la présence d'un élément.

## Création d'un Set

Vous pouvez créer un `Set` en utilisant le constructeur `Set()`, qui peut accepter un tableau ou un autre objet itérable comme argument.

### Exemple

```javascript
const mySet = new Set([1, 2, 3, 4, 4]); // Le Set ignore la valeur dupliquée 4
console.log(mySet); // Set { 1, 2, 3, 4 }
```

## Méthodes du Set

### `add(value)`

Ajoute une valeur au Set. Si la valeur existe déjà, elle n'est pas ajoutée.

#### Syntaxe

```javascript
set.add(value);
```

#### Exemple

```javascript
const mySet = new Set();
mySet.add(1);
mySet.add(2);
mySet.add(1); // Ignoré, car 1 est déjà dans le Set
console.log(mySet); // Set { 1, 2 }
```

### `delete(value)`

Supprime une valeur du Set. Renvoie `true` si la valeur a été supprimée, sinon `false`.

#### Syntaxe

```javascript
set.delete(value);
```

#### Exemple

```javascript
const mySet = new Set([1, 2, 3]);
mySet.delete(2);
console.log(mySet); // Set { 1, 3 }
```

### `has(value)`

Vérifie si une valeur est présente dans le Set. Renvoie `true` ou `false`.

#### Syntaxe

```javascript
set.has(value);
```

#### Exemple

```javascript
const mySet = new Set([1, 2, 3]);
console.log(mySet.has(2)); // true
console.log(mySet.has(4)); // false
```

### `clear()`

Supprime toutes les valeurs du Set.

#### Syntaxe

```javascript
set.clear();
```

#### Exemple

```javascript
const mySet = new Set([1, 2, 3]);
mySet.clear();
console.log(mySet); // Set {}
```

### `size`

Propriété qui retourne le nombre d'éléments dans le Set.

#### Syntaxe

```javascript
set.size;
```

#### Exemple

```javascript
const mySet = new Set([1, 2, 3]);
console.log(mySet.size); // 3
```

## Itération sur les éléments d'un Set

Vous pouvez itérer sur les éléments d'un `Set` en utilisant les méthodes `forEach()` ou en utilisant des boucles `for...of`.

### Exemple avec `forEach()`

```javascript
const mySet = new Set([1, 2, 3]);

mySet.forEach(value => {
  console.log(value);
});
// Output:
// 1
// 2
// 3
```

### Exemple avec `for...of`

```javascript
const mySet = new Set([1, 2, 3]);

for (const value of mySet) {
  console.log(value);
}
// Output:
// 1
// 2
// 3
```

Les `Set` en JavaScript sont particulièrement utiles pour garantir l'unicité des éléments dans une collection et pour des opérations rapides de recherche et de suppression.