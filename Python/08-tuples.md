# Les tuples en Python

Les **tuples** en Python sont similaires aux listes, à la différence qu'ils sont **immuables**, c'est-à-dire que vous ne pouvez pas modifier, ajouter ou supprimer des éléments une fois qu'ils sont créés. Les tuples sont souvent utilisés pour stocker des données qui ne doivent pas être modifiées. Comme les listes, les tuples peuvent contenir des éléments de types différents.

### Déclaration d'un tuple
Un tuple se déclare en plaçant les éléments entre parenthèses `()`.

```python
fruits = ("apple", "banana", "cherry")
```

Un tuple avec un seul élément doit inclure une virgule pour éviter qu'il soit interprété comme une simple variable.

```python
single_element_tuple = ("apple",)  # Notez la virgule
```

### Accéder aux éléments d'un tuple
Les éléments d'un tuple sont accessibles par leur index, comme les listes.

```python
print(fruits[0])  # Résultat : "apple"
```

## Déballer des Tuples (Unpack Tuples)
Le déballage (unpacking) de tuples permet d'affecter les éléments du tuple à des variables individuelles.

### Déballer un tuple
Vous pouvez affecter chaque élément d'un tuple à une variable distincte.

```python
fruits = ("apple", "banana", "cherry")
(first, second, third) = fruits
print(first)  # Résultat : "apple"
print(second)  # Résultat : "banana"
print(third)  # Résultat : "cherry"
```

### Déballage avec `*` (reste des éléments)
Si vous avez plus d'éléments dans le tuple que de variables, vous pouvez utiliser `*` pour affecter le reste des éléments à une liste.

```python
fruits = ("apple", "banana", "cherry", "orange")
(first, *rest) = fruits
print(first)  # Résultat : "apple"
print(rest)  # Résultat : ['banana', 'cherry', 'orange']
```

## Boucle à Travers les Tuples (Loop Tuples)
Les tuples peuvent être parcourus de la même manière que les listes, en utilisant une boucle `for` ou `while`.

### Boucle `for`
La manière la plus courante de parcourir un tuple est d'utiliser une boucle `for`.

```python
fruits = ("apple", "banana", "cherry")
for fruit in fruits:
    print(fruit)
```

### Boucle avec index
Si vous avez besoin de l'index, vous pouvez utiliser la fonction `range()` en combinaison avec `len()`.

```python
for i in range(len(fruits)):
    print(fruits[i])
```

### Boucle avec `enumerate()`
`enumerate()` permet de récupérer à la fois l'index et l'élément.

```python
for i, fruit in enumerate(fruits):
    print(i, fruit)
```

## Joindre des Tuples (Join Tuples)
Comme les listes, les tuples peuvent être **fusionnés** (concaténés) en utilisant l'opérateur `+`.

### Concaténer deux tuples
Vous pouvez utiliser l'opérateur `+` pour combiner deux tuples en un seul.

```python
tuple1 = (1, 2, 3)
tuple2 = (4, 5, 6)
combined = tuple1 + tuple2
print(combined)  # Résultat : (1, 2, 3, 4, 5, 6)
```

### Multiplier un tuple
Un tuple peut être multiplié pour répéter ses éléments plusieurs fois.

```python
multiplied = tuple1 * 2
print(multiplied)  # Résultat : (1, 2, 3, 1, 2, 3)
```

## Méthodes de Tuples (Tuple Methods)
Les tuples possèdent moins de méthodes que les listes, en raison de leur immuabilité. Cependant, certaines méthodes utiles sont disponibles.

### `count()`
Retourne le nombre d'occurrences d'un élément dans le tuple.

```python
fruits = ("apple", "banana", "cherry", "apple")
count = fruits.count("apple")
print(count)  # Résultat : 2
```

### `index()`
Retourne l'index du premier élément ayant la valeur donnée.

```python
index = fruits.index("cherry")
print(index)  # Résultat : 2
```

### `copy()` (avec conversion)
Bien que les tuples soient immuables, vous pouvez copier un tuple en le convertissant temporairement en liste, puis en tuple.

```python
fruits = ("apple", "banana", "cherry")
copy_fruits = tuple(list(fruits))
print(copy_fruits)  # Résultat : ('apple', 'banana', 'cherry')
```
