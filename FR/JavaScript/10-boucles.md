# Structures de Boucle en JavaScript

## `for`

Permet de répéter un bloc de code un nombre déterminé de fois.

```javascript
for (initialisation; condition; incrément) {
  // Code à exécuter à chaque itération
}
```

**Exemple :**

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Affiche les nombres de 0 à 4
```

## `for...in`

Permet de parcourir les propriétés énumérables d'un objet. Chaque itération renvoie une clé (nom de la propriété).

```javascript
for (let clé in objet) {
  // Code à exécuter pour chaque clé
}
```

**Exemple :**

```javascript
let personne = { nom: "Alice", age: 25 };

for (let clé in personne) {
  console.log(clé + ": " + personne[clé]);
}
// Affiche "nom: Alice" et "age: 25"
```

## `for...of`

Permet de parcourir les valeurs d'un objet itérable (comme un tableau, une chaîne de caractères, ou un objet Set). Chaque itération renvoie une valeur.

```javascript
for (let valeur of objetItérable) {
  // Code à exécuter pour chaque valeur
}
```

**Exemple :**

```javascript
let nombres = [1, 2, 3, 4, 5];

for (let nombre of nombres) {
  console.log(nombre);
}
// Affiche les nombres de 1 à 5
```

## `while`

Permet de répéter un bloc de code tant qu'une condition est vraie.

```javascript
while (condition) {
  // Code à exécuter tant que la condition est vraie
}
```

**Exemple :**

```javascript
let compteur = 0;

while (compteur < 5) {
  console.log(compteur);
  compteur++;
}
// Affiche les nombres de 0 à 4
```

## `do...while`

Similaire au `while`, mais garantit que le bloc de code sera exécuté au moins une fois avant de vérifier la condition.

```javascript
do {
  // Code à exécuter
} while (condition);
```

**Exemple :**

```javascript
let compteur = 0;

do {
  console.log(compteur);
  compteur++;
} while (compteur < 5);
// Affiche les nombres de 0 à 4
```                                   