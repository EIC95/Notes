# Les ensembles en Pyhton

Les **ensembles** (sets) en Python sont une collection non ordonnée d'éléments uniques. Un ensemble est une collection qui est **non ordonnée**, **immutable** (les éléments ne peuvent pas être changés après la création), et **non indexée**. Cependant, il est possible de retirer des éléments et d'en ajouter de nouveaux.


### Déclaration d'un ensemble
Un ensemble se déclare en plaçant les éléments entre accolades.

```python
fruits = {"apple", "banana", "cherry"}
```

Pour créer un ensemble vide, vous devez utiliser la fonction `set()`.

```python
empty_set = set()
```

## Accéder aux Éléments
Contrairement aux listes et aux tuples, vous ne pouvez pas accéder directement aux éléments d'un ensemble par leur index. Cependant, vous pouvez utiliser une boucle pour parcourir les éléments d'un ensemble.

## Boucle à Travers les Ensembles (Loop Sets)
Vous pouvez parcourir un ensemble en utilisant une boucle `for`. Étant donné que les ensembles sont non ordonnés, l'ordre des éléments lors de l'itération n'est pas garanti.

### Boucle `for`
Voici comment vous pouvez parcourir un ensemble :

```python
fruits = {"apple", "banana", "cherry"}
for fruit in fruits:
    print(fruit)
```

## Joindre des Ensembles (Join Sets)
Les ensembles peuvent être fusionnés en utilisant les méthodes `union()` ou l'opérateur `|`. Cela permet de créer un nouvel ensemble qui contient tous les éléments des ensembles d'origine.

### Utilisation de `union()`
La méthode `union()` retourne un nouvel ensemble contenant tous les éléments de deux ensembles.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
joined_set = set1.union(set2)
print(joined_set)  # Résultat : {1, 2, 3, 4, 5}
```

### Utilisation de l'opérateur `|`
Vous pouvez également utiliser l'opérateur `|` pour réaliser la même opération.

```python
joined_set = set1 | set2
print(joined_set)  # Résultat : {1, 2, 3, 4, 5}
```

## Méthodes d'Ensembles (Set Methods)
Les ensembles possèdent plusieurs méthodes utiles pour effectuer des opérations sur leurs éléments.

### `add()`
Ajoute un élément à l'ensemble. Si l'élément existe déjà, il ne sera pas ajouté.

```python
fruits = {"apple", "banana"}
fruits.add("cherry")
print(fruits)  # Résultat : {"apple", "banana", "cherry"}
```

### `remove()`
Supprime un élément de l'ensemble. Si l'élément n'existe pas, cela provoquera une erreur.

```python
fruits.remove("banana")
print(fruits)  # Résultat : {"apple", "cherry"}
```

### `discard()`
Supprime un élément de l'ensemble sans provoquer d'erreur si l'élément n'existe pas.

```python
fruits.discard("banana")  # Aucun effet, pas d'erreur
print(fruits)  # Résultat : {"apple", "cherry"}
```

### `clear()`
Supprime tous les éléments de l'ensemble.

```python
fruits.clear()
print(fruits)  # Résultat : set()
```

### `pop()`
Supprime et retourne un élément aléatoire de l'ensemble. Si l'ensemble est vide, cela provoquera une erreur.

```python
fruits = {"apple", "banana", "cherry"}
fruit = fruits.pop()
print(fruit)  # Résultat : un des éléments aléatoires, par exemple "banana"
```

### `intersection()`
Retourne un nouvel ensemble contenant les éléments communs entre deux ensembles.

```python
set1 = {1, 2, 3}
set2 = {2, 3, 4}
common_elements = set1.intersection(set2)
print(common_elements)  # Résultat : {2, 3}
```

### `difference()`
Retourne un nouvel ensemble contenant les éléments qui sont dans le premier ensemble mais pas dans le second.

```python
difference_set = set1.difference(set2)
print(difference_set)  # Résultat : {1}
```

### `symmetric_difference()`
Retourne un nouvel ensemble contenant les éléments qui sont dans un des ensembles mais pas dans les deux.

```python
sym_diff = set1.symmetric_difference(set2)
print(sym_diff)  # Résultat : {1, 4}
```