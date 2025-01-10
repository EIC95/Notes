# Boucles

## Boucle For
La boucle `for` est utilisée pour itérer sur une séquence (comme une liste, un tuple, un dictionnaire, un ensemble ou une chaîne). 

### Exemple
```python
fruits = ["pomme", "banane", "cerise"]
for fruit in fruits:
    print(fruit)
```
Ce code affiche chaque fruit dans la liste.

### Utiliser range()
La fonction `range()` génère une séquence de nombres, ce qui est utile pour effectuer des itérations un nombre spécifique de fois.

```python
for i in range(5):
    print(i)
```
Ce code affiche les nombres de 0 à 4.

## Boucle While
La boucle `while` exécute un bloc de code tant qu'une condition est vraie.

### Exemple
```python
compteur = 0
while compteur < 5:
    print(compteur)
    compteur += 1
```
Ce code affiche les nombres de 0 à 4.

## Contrôle de Flux dans les Boucles
Les instructions `break`, `continue`, et `pass` peuvent être utilisées pour contrôler le comportement des boucles.

### Break
L'instruction `break` termine la boucle lorsqu'une condition est remplie.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
# Affiche : 0, 1, 2
```

### Continue
L'instruction `continue` passe à l'itération suivante de la boucle, en sautant le code restant pour l'itération actuelle.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
# Affiche : 0, 1, 3, 4
```

### Pass
L'instruction `pass` est un espace réservé qui ne fait rien. Elle est utile lorsque vous souhaitez définir une structure de boucle sans encore ajouter de code.

```python
for i in range(5):
    pass  # En attente d'implémentation future
```

## Boucles Imbriquées
Vous pouvez également utiliser des boucles imbriquées, ce qui signifie qu'une boucle est contenue dans une autre.

### Exemple
```python
for i in range(3):
    for j in range(2):
        print(f"i = {i}, j = {j}")
```
Ce code affiche toutes les combinaisons de `i` et `j`.
