# Python Lists

Les **listes** sont l'une des structures de données les plus utilisées en Python. Elles permettent de stocker plusieurs éléments dans une seule variable. Une liste peut contenir des éléments de types différents (nombres, chaînes, booléens, etc.). Les listes sont **mutables**, ce qui signifie que vous pouvez changer leurs éléments après leur création.

### **Déclaration d'une liste** :
Une liste se déclare en plaçant ses éléments entre crochets `[]` et en les séparant par des virgules.

```python
fruits = ["apple", "banana", "cherry"]
```

### **Accéder aux éléments d'une liste** :
Les éléments d'une liste sont accessibles par leur index, en commençant par 0.

```python
print(fruits[0])  # Résultat : "apple"
```

## Loop Lists
Il existe plusieurs façons de parcourir les éléments d'une liste. Voici les plus courantes :

### **Boucle `for`** :
La boucle `for` est une méthode simple pour itérer à travers chaque élément d'une liste.

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### **Boucle avec index** :
Si vous avez besoin de l'index des éléments pendant l'itération, utilisez `range()` et `len()`.

```python
for i in range(len(fruits)):
    print(fruits[i])
```

### **Boucle `while`** :
Une boucle `while` peut également être utilisée pour parcourir les éléments d'une liste.

```python
i = 0
while i < len(fruits):
    print(fruits[i])
    i += 1
```

### **Boucle avec `enumerate()`** :
`enumerate()` permet de récupérer à la fois l'index et l'élément lors de l'itération.

```python
for i, fruit in enumerate(fruits):
    print(i, fruit)
```

## List Comprehension
Les **list comprehensions** sont une façon concise et élégante de créer des listes. Elles permettent de transformer ou de filtrer des listes existantes en une seule ligne de code.

### **Créer une nouvelle liste à partir d'une autre** :
Voici un exemple simple qui élève au carré chaque élément d'une liste.

```python
numbers = [1, 2, 3, 4, 5]
squared = [x**2 for x in numbers]
print(squared)  # Résultat : [1, 4, 9, 16, 25]
```

### **Avec condition** :
On peut ajouter des conditions pour filtrer les éléments d'une liste.

```python
even_numbers = [x for x in numbers if x % 2 == 0]
print(even_numbers)  # Résultat : [2, 4]
```

### **Transformation de chaînes de caractères** :
Les list comprehensions permettent également de transformer des chaînes de caractères.

```python
fruits = ["apple", "banana", "cherry"]
upper_fruits = [fruit.upper() for fruit in fruits]
print(upper_fruits)  # Résultat : ['APPLE', 'BANANA', 'CHERRY']
```

## Join Lists
Il existe plusieurs manières de **fusionner** deux ou plusieurs listes en Python.

### **Concaténation avec `+`** :
Utilisez l'opérateur `+` pour combiner deux listes en une seule.

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined = list1 + list2
print(combined)  # Résultat : [1, 2, 3, 4, 5, 6]
```

### **Utilisation de `extend()`** :
`extend()` ajoute tous les éléments d'une autre liste à la fin de la liste courante.

```python
list1.extend(list2)
print(list1)  # Résultat : [1, 2, 3, 4, 5, 6]
```

## 4. List Methods
Les listes en Python possèdent de nombreuses méthodes intégrées pour les manipuler. Voici les plus utiles, avec des exemples.

### **`append()`** :
Ajoute un élément à la fin de la liste.

```python
fruits.append("orange")
print(fruits)  # Résultat : ['apple', 'banana', 'cherry', 'orange']
```

### **`insert()`** :
Insère un élément à une position spécifique.

```python
fruits.insert(1, "grape")
print(fruits)  # Résultat : ['apple', 'grape', 'banana', 'cherry']
```

### **`remove()`** :
Retire le premier élément trouvé avec la valeur spécifiée.

```python
fruits.remove("banana")
print(fruits)  # Résultat : ['apple', 'grape', 'cherry']
```

### **`pop()`** :
Retire et retourne l'élément à l'index donné (par défaut, le dernier élément).

```python
fruits.pop()
print(fruits)  # Résultat : ['apple', 'grape']
```

### **`index()`** :
Retourne l'index du premier élément ayant la valeur donnée.

```python
index = fruits.index("grape")
print(index)  # Résultat : 1
```

### **`sort()`** :
Trie la liste en place dans l'ordre croissant.

```python
fruits.sort()
print(fruits)  # Résultat : ['apple', 'grape', 'orange']
```

### **`reverse()`** :
Inverse l'ordre des éléments de la liste.

```python
fruits.reverse()
print(fruits)  # Résultat : ['orange', 'grape', 'apple']
```

### **`count()`** :
Compte le nombre d'occurrences d'un élément spécifique dans la liste.

```python
count = fruits.count("apple")
print(count)  # Résultat : 1
```

### **`copy()`** :
Crée une copie indépendante de la liste.

```python
new_fruits = fruits.copy()
print(new_fruits)  # Résultat : ['orange', 'grape', 'apple']
```

### **`clear()`** :
Vide complètement la liste.

```python
fruits.clear()
print(fruits)  # Résultat : []
```