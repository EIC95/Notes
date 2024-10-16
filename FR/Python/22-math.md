# Python Math

### Fonctions mathématiques intégrées
Python dispose de plusieurs fonctions mathématiques intégrées pour effectuer des tâches sur les nombres.

#### `min()` et `max()`
Ces fonctions renvoient respectivement la valeur minimale et maximale dans un itérable.

```python
x = min(5, 10, 25)
y = max(5, 10, 25)

print(x)  # Renvoie 5
print(y)  # Renvoie 25
```

#### `abs()`
Renvoie la valeur absolue (positive) d'un nombre spécifié.

```python
x = abs(-7.25)
print(x)  # Renvoie 7.25
```

#### `pow()`
La fonction `pow(x, y)` renvoie la valeur de `x` à la puissance `y` (c'est-à-dire `x^y`).

```python
x = pow(4, 3)
print(x)  # Renvoie 64 (4 * 4 * 4)
```

### Module Math
Python dispose également d'un module mathématique intégré appelé `math`, qui étend la liste des fonctions mathématiques.

#### Fonctions du module math

- **`math.sqrt(x)`** : Renvoie la racine carrée de `x`.
  
  ```python
  math.sqrt(16)  # Renvoie 4.0
  ```

- **`math.ceil(x)`** : Arrondit `x` à l'entier supérieur le plus proche.
  
  ```python
  math.ceil(1.4)  # Renvoie 2
  ```

- **`math.floor(x)`** : Arrondit `x` à l'entier inférieur le plus proche.
  
  ```python
  math.floor(1.4)  # Renvoie 1
  ```

- **`math.pow(x, y)`** : Renvoie `x` à la puissance `y`.
  
  ```python
  math.pow(2, 3)  # Renvoie 8.0
  ```

- **`math.factorial(x)`** : Renvoie la factorielle de `x`.
  
  ```python
  math.factorial(5)  # Renvoie 120
  ```

- **`math.log(x)`** : Renvoie le logarithme naturel de `x` (base e).
  
  ```python
  math.log(10)  # Renvoie 2.302585...
  ```

- **`math.log10(x)`** : Renvoie le logarithme en base 10 de `x`.
  
  ```python
  math.log10(100)  # Renvoie 2.0
  ```

- **`math.sin(x)`** : Renvoie le sinus de `x` (en radians).
  
  ```python
  math.sin(math.pi/2)  # Renvoie 1.0
  ```

- **`math.cos(x)`** : Renvoie le cosinus de `x` (en radians).
  
  ```python
  math.cos(0)  # Renvoie 1.0
  ```

- **`math.tan(x)`** : Renvoie la tangente de `x` (en radians).
  
  ```python
  math.tan(math.pi/4)  # Renvoie 1.0
  ```

- **`math.degrees(x)`** : Convertit `x` de radians en degrés.
  
  ```python
  math.degrees(math.pi)  # Renvoie 180.0
  ```

- **`math.radians(x)`** : Convertit `x` de degrés en radians.
  
  ```python
  math.radians(180)  # Renvoie 3.14159...
  ```

#### Constantes du module math

- **`math.pi`** : La constante Pi (3,14159...).

  ```python
  math.pi  # Renvoie 3.141592653589793
  ```

- **`math.e`** : La constante e (base des logarithmes naturels, ~2,718).

  ```python
  math.e  # Renvoie 2.718281828459045
  ```

- **`math.inf`** : Représente l'infini positif.

  ```python
  math.inf  # Renvoie inf
  ```

- **`math.nan`** : Représente une valeur NaN (Not a Number).

  ```python
  math.nan  # Renvoie nan
  ```