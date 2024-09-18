# Mathématiques en JavaScript

JavaScript fournit 8 constantes mathématiques accessibles en tant que propriétés de l'objet `Math` :

- **`Math.E`** : retourne le nombre d'Euler (~2.718)
- **`Math.PI`** : retourne PI (~3.14159)
- **`Math.SQRT2`** : retourne la racine carrée de 2 (~1.414)
- **`Math.SQRT1_2`** : retourne la racine carrée de 1/2 (~0.707)
- **`Math.LN2`** : retourne le logarithme naturel de 2 (~0.693)
- **`Math.LN10`** : retourne le logarithme naturel de 10 (~2.303)
- **`Math.LOG2E`** : retourne le logarithme en base 2 de E (~1.442)
- **`Math.LOG10E`** : retourne le logarithme en base 10 de E (~0.434)

## Méthodes Mathématiques

- **`Math.abs(x)`**  
  Retourne la valeur absolue de `x`.

  ```javascript
  console.log(Math.abs(-5)); // 5
  ```

- **`Math.ceil(x)`**  
  Retourne le plus petit entier supérieur ou égal à `x`.

  ```javascript
  console.log(Math.ceil(4.2)); // 5
  ```

- **`Math.floor(x)`**  
  Retourne le plus grand entier inférieur ou égal à `x`.

  ```javascript
  console.log(Math.floor(4.7)); // 4
  ```

- **`Math.round(x)`**  
  Retourne l'entier le plus proche de `x`.

  ```javascript
  console.log(Math.round(4.5)); // 5
  console.log(Math.round(4.4)); // 4
  ```

- **`Math.max(a, b, ...)`**  
  Retourne le plus grand des arguments fournis.

  ```javascript
  console.log(Math.max(1, 2, 3, 4)); // 4
  ```

- **`Math.min(a, b, ...)`**  
  Retourne le plus petit des arguments fournis.

  ```javascript
  console.log(Math.min(1, 2, 3, 4)); // 1
  ```

- **`Math.random()`**  
  Retourne un nombre pseudo-aléatoire entre 0 (inclus) et 1 (exclus).

  ```javascript
  console.log(Math.random()); // Par exemple, 0.456
  ```

- **`Math.pow(base, exponent)`**  
  Retourne `base` élevé à la puissance `exponent`.

  ```javascript
  console.log(Math.pow(2, 3)); // 8
  ```

- **`Math.sqrt(x)`**  
  Retourne la racine carrée de `x`.

  ```javascript
  console.log(Math.sqrt(16)); // 4
  ```