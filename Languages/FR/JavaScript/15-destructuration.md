# La destructuration d'itérables en JavaScript

La **destructuration** permet d'extraire facilement des éléments d'un tableau (ou d'autres objets itérables) et de les assigner à des variables individuelles.

## Destructuration de tableaux

Vous pouvez assigner directement des éléments d'un tableau à des variables par leur position dans le tableau.

### Exemple basique

```javascript
let [a, b, c] = [1, 2, 3];
console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
```

## Renommer les variables

Lors de la destructuration d'objets, vous pouvez également renommer les variables que vous extrayez.

### Exemple avec renommage

```javascript
let personne = { nom: "Alice", age: 25 };
let { nom: prenom, age: annee } = personne;

console.log(prenom); // "Alice"
console.log(annee);  // 25
```

## Valeurs par défaut

Vous pouvez définir des valeurs par défaut si une variable extraite est `undefined`.

### Exemple avec valeurs par défaut

```javascript
let [x = 5, y = 7] = [10];
console.log(x); // 10
console.log(y); // 7 (car non défini dans le tableau d'origine)
```

## Ignorer des éléments

Vous pouvez ignorer certains éléments d'un tableau en laissant des espaces vides dans la liste de variables.

### Exemple d'éléments ignorés

```javascript
let [premier, , troisieme] = [1, 2, 3];
console.log(premier);   // 1
console.log(troisieme); // 3
```

## Destructuration imbriquée

Vous pouvez destructurer des tableaux ou objets imbriqués.

### Exemple de destructuration imbriquée

```javascript
let tableau = [1, [2, 3]];
let [a, [b, c]] = tableau;
console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
```
