# Expressions Régulières en JavaScript

Les expressions régulières (ou regex) sont des outils puissants pour la manipulation et la recherche de texte. Elles permettent de définir des motifs de recherche et de validation dans des chaînes de caractères en utilisant une syntaxe spéciale.

## Syntaxe de Base

* `.` : Correspond à n'importe quel caractère sauf les sauts de ligne.
* `^` : Indique le début de la chaîne.
* `$` : Indique la fin de la chaîne.
* `*` : Correspond à zéro ou plusieurs occurrences du caractère précédent.
* `+` : Correspond à une ou plusieurs occurrences du caractère précédent.
* `?` : Correspond à zéro ou une occurrence du caractère précédent.
* `{n}` : Correspond à exactement `n` occurrences du caractère précédent.
* `{n,}` : Correspond à `n` occurrences ou plus du caractère précédent.
* `{n,m}` : Correspond à entre `n` et `m` occurrences du caractère précédent.
* `|` : Opérateur "ou", correspond à l'une des options séparées par le pipe.
* `()` : Regroupe des parties du motif pour les capturer.
* `[]` : Définit une classe de caractères, correspondant à tout caractère inclus entre les crochets.
* `\d` : Correspond à un chiffre (équivalent à `[0-9]`).
* `\D` : Correspond à un caractère non numérique.
* `\w` : Correspond à un caractère de mot (lettre, chiffre ou underscore, équivalent à `[a-zA-Z0-9_]`).
* `\W` : Correspond à un caractère non alphanumérique.
* `\s` : Correspond à un espace blanc (espace, tabulation, saut de ligne, etc.).
* `\S` : Correspond à un caractère non espace blanc.

## Méthodes des Expressions Régulières

### `test()`

Vérifie si une chaîne correspond au motif.

#### Syntaxe

```javascript
const regex = /motif/;
const result = regex.test('chaîne');
console.log(result); // true ou false
```

#### Exemple

```javascript
const regex = /abc/;
console.log(regex.test('abcdef')); // true
console.log(regex.test('defabc')); // false
```

### `exec()`

Exécute une recherche pour le motif et retourne les résultats.

#### Syntaxe

```javascript
const regex = /motif/;
const result = regex.exec('chaîne');
console.log(result); // Tableau avec les résultats ou null
```

#### Exemple

```javascript
const regex = /(\d+)/;
const result = regex.exec('Le nombre est 123');
console.log(result); // ["123", "123"]
```

### `match()`

Trouve les correspondances dans une chaîne.

#### Syntaxe

```javascript
const result = 'chaîne'.match(/motif/);
console.log(result); // Tableau avec les résultats ou null
```

#### Exemple

```javascript
const result = 'Bonjour 123, bonjour 456'.match(/\d+/g);
console.log(result); // ["123", "456"]
```

### `replace()`

Remplace les correspondances par une nouvelle chaîne.

#### Syntaxe

```javascript
const result = 'chaîne'.replace(/motif/, 'remplacement');
console.log(result); // Nouvelle chaîne avec les remplacements
```

#### Exemple

```javascript
const result = 'Bonjour 123'.replace(/\d+/, '456');
console.log(result); // "Bonjour 456"
```

### `split()`

Divise une chaîne en un tableau de sous-chaînes basées sur le motif.

#### Syntaxe

```javascript
const result = 'chaîne'.split(/motif/);
console.log(result); // Tableau des sous-chaînes
```

#### Exemple

```javascript
const result = 'a,b,c'.split(/,/);
console.log(result); // ["a", "b", "c"]
```

