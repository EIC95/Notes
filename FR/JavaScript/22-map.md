# Map en JavaScript

En JavaScript, un `Map` est une collection d'éléments où chaque élément est une paire clé-valeur. Les clés et les valeurs peuvent être de n'importe quel type, y compris des objets. Contrairement aux objets, les clés d'un `Map` sont ordonnées et peuvent être de n'importe quel type.

## Création d'un Map

Vous pouvez créer un `Map` en utilisant le constructeur `Map()`, qui peut accepter un tableau de paires clé-valeur pour initialiser le `Map`.

### Exemple

```javascript
const map = new Map([
  ['clé1', 'valeur1'],
  ['clé2', 'valeur2']
]);
```

## Méthodes du Map

### `set(key, value)`

Ajoute ou met à jour une paire clé-valeur dans le `Map`.

#### Syntaxe

```javascript
map.set('clé', 'valeur');
```

#### Exemple

```javascript
map.set('nom', 'Alice');
map.set('âge', 25);
```

### `get(key)`

Retourne la valeur associée à la clé spécifiée.

#### Syntaxe

```javascript
const valeur = map.get('clé');
```

#### Exemple

```javascript
const nom = map.get('nom'); // "Alice"
```

### `has(key)`

Vérifie si une clé est présente dans le `Map`. Renvoie `true` ou `false`.

#### Syntaxe

```javascript
const existe = map.has('clé');
```

#### Exemple

```javascript
const aNom = map.has('nom'); // true
const aAdresse = map.has('adresse'); // false
```

### `delete(key)`

Supprime la paire clé-valeur associée à la clé spécifiée. Renvoie `true` si la clé a été supprimée, sinon `false`.

#### Syntaxe

```javascript
const supprimé = map.delete('clé');
```

#### Exemple

```javascript
const supprimé = map.delete('nom'); // true
```

### `clear()`

Supprime toutes les paires clé-valeur du `Map`.

#### Syntaxe

```javascript
map.clear();
```

#### Exemple

```javascript
map.clear(); // Efface toutes les entrées du Map
```

### `size`

Propriété qui retourne le nombre d'éléments dans le `Map`.

#### Syntaxe

```javascript
const taille = map.size;
```

#### Exemple

```javascript
const taille = map.size; // 1, après avoir supprimé une entrée
```

## Itération sur un Map

Vous pouvez itérer sur les éléments d'un `Map` en utilisant `forEach()` ou en utilisant des boucles `for...of`.

### Exemple avec `forEach()`

```javascript
map.forEach((valeur, clé) => {
  console.log(`${clé}: ${valeur}`);
});
```

### Exemple avec `for...of`

```javascript
for (const [clé, valeur] of map) {
  console.log(`${clé}: ${valeur}`);
}
```

Le `Map` est une structure de données flexible et puissante pour gérer des collections de paires clé-valeur en JavaScript, offrant des opérations efficaces et une gestion ordonnée des clés.