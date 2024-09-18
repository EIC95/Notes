# Modules en JavaScript

Les modules en JavaScript permettent de structurer et d'organiser le code en séparant les fonctionnalités en unités indépendantes. Vous pouvez importer et exporter des éléments entre différents fichiers pour améliorer la modularité et la réutilisabilité du code.

## Exportation

### Exportation Nommée

Permet d'exporter plusieurs éléments depuis un fichier.

#### Syntaxe

```javascript
// fichier.js
export const nomVariable = "valeur";
export function nomFonction() {
  // code
}
```

#### Importation

```javascript
// autreFichier.js
import { nomVariable, nomFonction } from './fichier.js';
```

### Exportation par Défaut

Permet d'exporter un seul élément par fichier.

#### Syntaxe

```javascript
// fichier.js
export default function nomFonction() {
  // code
}
```

#### Importation

```javascript
// autreFichier.js
import nomFonction from './fichier.js';
```

## Importation

### Importation Nommée

Permet d'importer des éléments spécifiques depuis un module.

#### Syntaxe

```javascript
// autreFichier.js
import { nomVariable, nomFonction } from './fichier.js';
```

### Importation par Défaut

Permet d'importer l'élément exporté par défaut d'un module.

#### Syntaxe

```javascript
// autreFichier.js
import nomFonction from './fichier.js';
```

### Renommer des Imports

Vous pouvez renommer des éléments lors de l'importation pour éviter les conflits de noms ou pour des raisons de clarté.

#### Syntaxe

```javascript
// fichier.js
export const nomOriginal = "valeur";

// autreFichier.js
import { nomOriginal as nouveauNom } from './fichier.js';
```

## Exemples

### Exportation Nommée

```javascript
// mathUtils.js
export const PI = 3.14;
export function add(a, b) {
  return a + b;
}
```

```javascript
// app.js
import { PI, add } from './mathUtils.js';
console.log(PI); // 3.14
console.log(add(2, 3)); // 5
```

### Exportation par Défaut

```javascript
// greet.js
export default function greet(name) {
  return `Hello, ${name}!`;
}
```

```javascript
// app.js
import greet from './greet.js';
console.log(greet('Alice')); // Hello, Alice!
```