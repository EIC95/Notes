# Conversion de Types en JavaScript

Il existe deux types principaux de conversion de type en JavaScript : implicite et explicite.

## Conversion Implicite

La conversion implicite, ou automatique, se produit lorsque JavaScript convertit automatiquement une valeur d'un type à un autre lorsque nécessaire, par exemple, lors d'opérations mathématiques ou de comparaisons.

- **En Nombre**  
  JavaScript convertit automatiquement des chaînes ou d'autres types en nombres lorsque c'est nécessaire.

  ```javascript
  let str = "123";
  let num = Number(str);
  console.log(num); // 123 (en tant que nombre)
  ```

- **`parseInt(value, base)`**  
  Convertit une chaîne en entier selon la base spécifiée (généralement base 10).

  ```javascript
  let str = "123";
  let num = parseInt(str, 10);
  console.log(num); // 123
  ```

- **`parseFloat(value)`**  
  Convertit une chaîne en nombre flottant.

  ```javascript
  let str = "123.45";
  let num = parseFloat(str);
  console.log(num); // 123.45
  ```

## Conversion Explicite

La conversion explicite, ou casting, se fait manuellement en utilisant des méthodes ou des opérateurs pour transformer une valeur d'un type à un autre.

- **En Chaîne**  
  Convertit un nombre ou d'autres types en chaîne de caractères.

  ```javascript
  let num = 123;
  let str = String(num);
  console.log(str); // "123"
  ```

  ```javascript
  let num = 123;
  let str = num.toString();
  console.log(str); // "123"
  ```

- **En Booléen**  
  Convertit une valeur en booléen (`true` ou `false`). Tous les types peuvent être convertis en booléen, sauf `0`, `null`, `undefined`, `NaN`, et `""` (chaîne vide), qui deviennent `false`.

  ```javascript
  let str = "hello";
  let bool = Boolean(str);
  console.log(bool); // true
  ```

  ```javascript
  let num = 1;
  let bool = !!num;
  console.log(bool); // true
  ```