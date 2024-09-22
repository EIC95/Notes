 Opérateurs en Python

Les opérateurs sont utilisés pour effectuer des opérations sur des variables et des valeurs. Python divise les opérateurs en plusieurs groupes :

## 1. Opérateurs arithmétiques

Les opérateurs arithmétiques sont utilisés pour effectuer des opérations mathématiques courantes.

| Opérateur  | Nom             | Exemple  |
|------------|-----------------|----------|
| `+`        | Addition        | `x + y`  |
| `-`        | Soustraction     | `x - y`  |
| `*`        | Multiplication   | `x * y`  |
| `/`        | Division         | `x / y`  |
| `%`        | Modulus          | `x % y`  |
| `**`       | Exponentiation   | `x ** y` |
| `//`       | Division entière | `x // y` |

### Exemple

```python
x = 10
y = 3
print(x + y)   # Addition : 13
print(x ** y)  # Exponentiation : 1000
```

---

## 2. Opérateurs d'affectation

Les opérateurs d'affectation sont utilisés pour attribuer des valeurs aux variables.

| Opérateur | Exemple   | Équivalent              |
|-----------|-----------|-------------------------|
| `=`       | `x = 5`   | `x = 5`                 |
| `+=`      | `x += 3`  | `x = x + 3`             |
| `-=`      | `x -= 3`  | `x = x - 3`             |
| `*=`      | `x *= 3`  | `x = x * 3`             |
| `/=`      | `x /= 3`  | `x = x / 3`             |
| `%= `     | `x %= 3`  | `x = x % 3`             |
| `//=`     | `x //= 3` | `x = x // 3`            |
| `**=`     | `x **= 3` | `x = x ** 3`            |

### Exemple

```python
x = 10
x += 5
print(x)  # Résultat : 15
```

---

## 3. Opérateurs de comparaison

Les opérateurs de comparaison comparent deux valeurs.

| Opérateur  | Nom                       | Exemple  |
|------------|----------------------------|----------|
| `==`       | Égal à                     | `x == y` |
| `!=`       | Différent de               | `x != y` |
| `>`        | Supérieur à                | `x > y`  |
| `<`        | Inférieur à                | `x < y`  |
| `>=`       | Supérieur ou égal à        | `x >= y` |
| `<=`       | Inférieur ou égal à        | `x <= y` |

### Exemple

```python
x = 10
y = 5
print(x > y)  # Résultat : True
```

---

## 4. Opérateurs logiques

Les opérateurs logiques sont utilisés pour combiner des conditions.

| Opérateur  | Description                             | Exemple                 |
|------------|-----------------------------------------|-------------------------|
| `and`      | Retourne True si les deux conditions sont vraies | `x < 5 and x < 10`      |
| `or`       | Retourne True si l'une des conditions est vraie   | `x < 5 or x < 4`        |
| `not`      | Inverse le résultat : True devient False | `not(x < 5 and x < 10)` |

### Exemple

```python
x = 5
print(x > 3 and x < 10)  # Résultat : True
```

---

## 5. Opérateurs d'identité

Les opérateurs d'identité sont utilisés pour comparer les objets par leur identité (adresse mémoire).

| Opérateur  | Description                              | Exemple   |
|------------|------------------------------------------|-----------|
| `is`       | Retourne True si les deux variables sont le même objet | `x is y`  |
| `is not`   | Retourne True si les deux variables ne sont pas le même objet | `x is not y` |

### Exemple

```python
x = ["apple", "banana"]
y = ["apple", "banana"]
print(x is y)  # Résultat : False (ils ont le même contenu, mais sont des objets différents)
```

---

## 6. Opérateurs d'appartenance

Les opérateurs d'appartenance sont utilisés pour vérifier si une séquence contient une valeur.

| Opérateur  | Description                                        | Exemple   |
|------------|----------------------------------------------------|-----------|
| `in`       | Retourne True si une séquence contient une valeur  | `x in y`  |
| `not in`   | Retourne True si une séquence ne contient pas une valeur | `x not in y` |

### Exemple

```python
x = "banana"
print("a" in x)  # Résultat : True
```

---

## 7. Opérateurs binaires

Les opérateurs binaires sont utilisés pour manipuler des nombres binaires.

| Opérateur | Nom               | Description                                           | Exemple  |
|-----------|-------------------|-------------------------------------------------------|----------|
| `&`       | ET binaire        | Met chaque bit à 1 si les deux bits sont 1            | `x & y`  |
| `\|\|`       | OU binaire        | Met chaque bit à 1 si l'un des deux bits est 1        | `x \|\| y`  |
| `^`       | OU exclusif (XOR) | Met chaque bit à 1 si un seul des deux bits est 1     | `x ^ y`  |
| `~`       | NON binaire       | Inverse tous les bits                                 | `~x`     |
| `<<`      | Décalage à gauche | Décale les bits vers la gauche et ajoute des 0 à droite | `x << 2` |
| `>>`      | Décalage à droite | Décale les bits vers la droite et conserve le bit de signe | `x >> 2` |

### Exemple

```python
x = 5  # 0101 en binaire
y = 3  # 0011 en binaire
print(x & y)  # Résultat : 1 (0001 en binaire)
```