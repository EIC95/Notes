# Structures de Contrôle en JavaScript

## `if`

Permet d'exécuter un bloc de code si une condition est vraie.

```javascript
if (condition) {
  // Code à exécuter si la condition est vraie
}
```

**Exemple :**

```javascript
if (age >= 18) {
  console.log("Vous êtes adulte.");
}
```

## `if...else`

Permet d'exécuter un bloc de code si une condition est vraie, et un autre bloc si la condition est fausse.

```javascript
if (condition) {
  // Code à exécuter si la condition est vraie
} else {
  // Code à exécuter si la condition est fausse
}
```

**Exemple :**

```javascript
if (age >= 18) {
  console.log("Vous êtes adulte.");
} else {
  console.log("Vous êtes mineur.");
}
```

## `else if`

Permet de tester plusieurs conditions successivement si la première condition est fausse.

```javascript
if (condition1) {
  // Code à exécuter si condition1 est vraie
} else if (condition2) {
  // Code à exécuter si condition2 est vraie
} else {
  // Code à exécuter si aucune des conditions précédentes n'est vraie
}
```

**Exemple :**

```javascript
if (note >= 90) {
  console.log("A");
} else if (note >= 80) {
  console.log("B");
} else if (note >= 70) {
  console.log("C");
} else {
  console.log("D");
}
```

## `switch`

Permet de sélectionner l'un parmi plusieurs blocs de code à exécuter en fonction de la valeur d'une expression.

```javascript
switch (expression) {
  case valeur1:
    // Code à exécuter si expression === valeur1
    break;
  case valeur2:
    // Code à exécuter si expression === valeur2
    break;
  default:
    // Code à exécuter si aucune des valeurs ne correspond
}
```

**Exemple :**

```javascript
switch (jour) {
  case 1:
    console.log("Lundi");
    break;
  case 2:
    console.log("Mardi");
    break;
  case 3:
    console.log("Mercredi");
    break;
  default:
    console.log("Jour invalide");
}
```