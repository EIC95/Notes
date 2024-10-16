# Fonctions Lambda en Python

Une fonction lambda est une petite fonction anonyme. Elle peut prendre un nombre quelconque d'arguments mais ne peut contenir qu'une seule expression.

## Syntaxe
```python
lambda arguments : expression
```
L'expression est exécutée et le résultat est retourné.

### Exemple
Ajoutez 10 à l'argument `a` et renvoyez le résultat :
```python
x = lambda a : a + 10
print(x(5))  # Résultat: 15
```

Les fonctions lambda peuvent prendre plusieurs arguments.

### Exemple
Multipliez l'argument `a` par l'argument `b` et renvoyez le résultat :
```python
x = lambda a, b : a * b
print(x(5, 6))  # Résultat: 30
```

### Exemple
Additionnez les arguments `a`, `b` et `c` :
```python
x = lambda a, b, c : a + b + c
print(x(5, 6, 2))  # Résultat: 13
```

## Pourquoi Utiliser les Fonctions Lambda ?
La puissance des fonctions lambda est plus évidente lorsqu'elles sont utilisées comme fonction anonyme dans une autre fonction. Par exemple, une fonction qui prend un argument et multiplie cet argument par un nombre inconnu.

### Exemple
Définissez une fonction qui retourne une fonction lambda pour multiplier un nombre par `n` :
```python
def ma_fonction(n):
    return lambda a : a * n

mon_doubleur = ma_fonction(2)

print(mon_doubleur(11))  # Résultat: 22
```

Dans cet exemple, la fonction `ma_fonction` crée une fonction qui double n'importe quel nombre passé.

### Exemple
Utilisez la même fonction pour tripler un nombre :
```python
def ma_fonction(n):
    return lambda a : a * n

mon_tripleur = ma_fonction(3)

print(mon_tripleur(11))  # Résultat: 33
```

### Exemple
Vous pouvez créer les deux fonctions dans le même programme :
```python
def ma_fonction(n):
    return lambda a : a * n

mon_doubleur = ma_fonction(2)
mon_tripleur = ma_fonction(3)

print(mon_doubleur(11))  # Résultat: 22
print(mon_tripleur(11))  # Résultat: 33
```             