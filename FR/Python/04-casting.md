# Casting en Python

Le **casting** en Python consiste à convertir une valeur d'un type de données à un autre. Cela peut être fait en utilisant des fonctions constructeurs. Voici les principales fonctions de casting disponibles en Python :

### 1. `str()`

Convertit une valeur en chaîne de caractères.

```python
x = str("Hello")                  # Chaîne de caractères (str)
y = str(123)                       # Convertit un entier en chaîne "123"
```

### 2. `int()`

Convertit une valeur en entier. Peut prendre une chaîne de caractères ou un nombre à virgule flottante.

```python
x = int(20.5)                     # Convertit en entier 20
y = int("42")                     # Convertit la chaîne "42" en entier 42
```

### 3. `float()`

Convertit une valeur en nombre à virgule flottante.

```python
x = float(10)                     # Convertit l'entier 10 en 10.0
y = float("3.14")                 # Convertit la chaîne "3.14" en flottant 3.14
```

### 4. `complex()`

Convertit une valeur en nombre complexe. 
**Attention** : il n'est pas possible de convertir un nombre complexe en un autre type de données (comme `int` ou `float`).

```python
x = complex(1, 2)                 # Crée le nombre complexe 1 + 2j
y = complex(2)                    # Crée le nombre complexe 2 + 0j
```

### 5. `list()`

Convertit un itérable (comme une chaîne de caractères, un tuple ou un ensemble) en liste.

```python
x = list("abc")                   # Convertit la chaîne "abc" en ['a', 'b', 'c']
y = list((1, 2, 3))               # Convertit le tuple (1, 2, 3) en [1, 2, 3]
```

### 6. `tuple()`

Convertit un itérable en tuple.

```python
x = tuple([1, 2, 3])              # Convertit la liste [1, 2, 3] en (1, 2, 3)
y = tuple("abc")                  # Convertit la chaîne "abc" en ('a', 'b', 'c')
```

### 7. `set()`

Convertit un itérable en ensemble. Les doublons sont automatiquement supprimés.

```python
x = set([1, 2, 2, 3])              # Convertit la liste [1, 2, 2, 3] en {1, 2, 3}
y = set("hello")                   # Convertit "hello" en {'h', 'e', 'l', 'o'}
```

### 8. `frozenset()`

Convertit un itérable en un ensemble immuable.

```python
x = frozenset([1, 2, 3, 3])        # Crée un ensemble immuable {1, 2, 3}
```

### 9. `dict()`

Crée un dictionnaire à partir d'une séquence de paires clé-valeur ou d'un autre dictionnaire.

```python
x = dict([("a", 1), ("b", 2)])     # Crée un dictionnaire {'a': 1, 'b': 2}
y = dict(name="John", age=36)       # Crée un dictionnaire {'name': 'John', 'age': 36}
```

### 10. `bytes()`

Crée un objet bytes.

```python
x = bytes(5)                        # Crée un tableau d'octets de taille 5
```

### 11. `bytearray()`

Crée un tableau d'octets mutable.

```python
x = bytearray(5)                   # Crée un tableau d'octets mutable de taille 5
```

### 12. `memoryview()`

Crée une vue mémoire d'un objet bytes ou bytearray.

```python
x = memoryview(bytes(5))           # Crée une vue mémoire d'un tableau d'octets de taille 5
```

### 13. `bool()`

Convertit une valeur en booléen. Toute valeur non nulle ou non vide est considérée comme `True`.

```python
x = bool(1)                        # Convertit 1 en True
y = bool(0)                        # Convertit 0 en False
```
