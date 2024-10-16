# Conditions

## Instructions Conditionnelles
Les instructions conditionnelles en Python permettent d'exécer un bloc de code en fonction d'une condition. Les principales instructions conditionnelles sont `if`, `elif` et `else`.

### If
L'instruction `if` exécute un bloc de code si la condition est vraie.

```python
age = 18
if age >= 18:
    print("Vous êtes majeur.")
```

### Elif
L'instruction `elif` permet de vérifier plusieurs conditions.

```python
age = 16
if age >= 18:
    print("Vous êtes majeur.")
elif age >= 13:
    print("Vous êtes un adolescent.")
else:
    print("Vous êtes un enfant.")
```

### Else
L'instruction `else` s'exécute si aucune des conditions précédentes n'est vraie.

```python
age = 10
if age >= 18:
    print("Vous êtes majeur.")
else:
    print("Vous êtes mineur.")
```

## Match Case
Introduit dans Python 3.10, l'instruction `match` permet de comparer une valeur contre plusieurs motifs. Cela peut être considéré comme une alternative au `switch` dans d'autres langages.

```python
value = "apple"

match value:
    case "banana":
        print("C'est une banane.")
    case "apple":
        print("C'est une pomme.")
    case _:
        print("C'est un autre fruit.")
```

## Opérateurs Logiques
Vous pouvez utiliser des opérateurs logiques pour combiner des conditions :

- `and` : True si les deux conditions sont vraies.
- `or` : True si au moins une des conditions est vraie.
- `not` : Inverse le résultat d'une condition.

```python
x = 5
if x > 0 and x < 10:
    print("x est entre 0 et 10.")

if x < 0 or x > 10:
    print("x est en dehors de l'intervalle.")
```

## Break et Continue
Les instructions `break` et `continue` sont utilisées pour contrôler le flux des boucles.

### Break
L'instruction `break` termine la boucle actuelle et passe à la suite du code.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
# Affiche : 0, 1, 2
```

### Continue
L'instruction `continue` passe à l'itération suivante de la boucle, sautant le code restant dans la boucle pour l'itération actuelle.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
# Affiche : 0, 1, 3, 4
```

## Pass
L'instruction `pass` est utilisée comme un espace réservé. Elle ne fait rien et est souvent utilisée lorsque vous devez écrire une structure de code qui n'est pas encore terminée.

```python
def fonction_vide():
    pass  # En attente d'implémentation future

if True:
    pass  # Rien à faire pour le moment
```
