# Itérateurs Python

### Introduction aux itérateurs
Un **itérateur** est un objet qui contient un nombre dénombrable de valeurs et permet de parcourir ces valeurs une par une. En Python, un itérateur est un objet qui implémente les méthodes `__iter__()` et `__next__()`.

### Itérateurs vs Itérables
- Un **itérable** est un objet sur lequel on peut itérer, comme les listes, tuples, dictionnaires ou chaînes.
- Un **itérateur** est un objet qui renvoie les éléments d'un itérable un à un. Vous pouvez obtenir un itérateur en appelant `iter()` sur un itérable.

### Exemple d'utilisation avec un tuple
```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit))  # apple
print(next(myit))  # banana
print(next(myit))  # cherry
```

### Exemple d'utilisation avec une chaîne
```python
mystr = "banana"
myit = iter(mystr)

print(next(myit))  # b
print(next(myit))  # a
print(next(myit))  # n
```

### Utilisation de la boucle `for` avec un itérateur
Python permet d'utiliser la boucle `for` pour parcourir un itérable sans avoir à gérer explicitement les appels à `next()`.

Exemple avec un tuple :
```python
mytuple = ("apple", "banana", "cherry")
for x in mytuple:
    print(x)
```

Exemple avec une chaîne :
```python
mystr = "banana"
for x in mystr:
    print(x)
```

### Créer un itérateur personnalisé
Vous pouvez créer une classe d'itérateur en définissant les méthodes `__iter__()` et `__next__()`.

Exemple d'itérateur qui retourne des nombres croissants :
```python
class MyNumbers:
    def __iter__(self):
        self.a = 1
        return self

    def __next__(self):
        x = self.a
        self.a += 1
        return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))  # 1
print(next(myiter))  # 2
print(next(myiter))  # 3
```

### Utilisation de `StopIteration`
L'itération peut être arrêtée après un certain nombre d'éléments en levant l'exception `StopIteration`.

Exemple qui limite l'itération à 20 éléments :
```python
class MyNumbers:
    def __iter__(self):
        self.a = 1
        return self

    def __next__(self):
        if self.a <= 20:
            x = self.a
            self.a += 1
            return x
        else:
            raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

for x in myiter:
    print(x)
```