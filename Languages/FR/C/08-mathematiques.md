# Fonctions Mathématiques en C

Voici une liste des fonctions les plus utiles de la bibliothèque `<math.h>` en C :

### Fonctions de base :
- **`sqrt(x)`** : Retourne la racine carrée de `x`.
  ```c
  #include <math.h>
  double racine = sqrt(25.0); // Retourne 5.0
  ```

- **`pow(base, exp)`** : Retourne `base` élevé à la puissance `exp`.
  ```c
  #include <math.h>
  double puissance = pow(2.0, 3.0); // Retourne 8.0
  ```

- **`fabs(x)`** : Retourne la valeur absolue de `x`.
  ```c
  #include <math.h>
  double absolue = fabs(-4.5); // Retourne 4.5
  ```

- **`ceil(x)`** : Retourne le plus petit entier supérieur ou égal à `x`.
  ```c
  #include <math.h>
  double ciel = ceil(4.3); // Retourne 5.0
  ```

- **`floor(x)`** : Retourne le plus grand entier inférieur ou égal à `x`.
  ```c
  #include <math.h>
  double sol = floor(4.7); // Retourne 4.0
  ```

### Fonctions logarithmiques et exponentielles :
- **`exp(x)`** : Retourne `e` élevé à la puissance `x`, où `e` est la base des logarithmes naturels.
  ```c
  #include <math.h>
  double exponentielle = exp(1.0); // Retourne environ 2.71828
  ```

- **`log(x)`** : Retourne le logarithme naturel (base `e`) de `x`.
  ```c
  #include <math.h>
  double logNaturel = log(2.71828); // Retourne 1.0
  ```

- **`log10(x)`** : Retourne le logarithme en base 10 de `x`.
  ```c
  #include <math.h>
  double logBase10 = log10(100.0); // Retourne 2.0
  ```

### Fonctions trigonométriques :
- **`sin(x)`** : Retourne le sinus de `x`, où `x` est en radians.
  ```c
  #include <math.h>
  double sinus = sin(3.14159 / 2); // Retourne 1.0
  ```

- **`cos(x)`** : Retourne le cosinus de `x`, où `x` est en radians.
  ```c
  #include <math.h>
  double cosinus = cos(3.14159); // Retourne -1.0
  ```

- **`tan(x)`** : Retourne la tangente de `x`, où `x` est en radians.
  ```c
  #include <math.h>
  double tangente = tan(0.0); // Retourne 0.0
  ```