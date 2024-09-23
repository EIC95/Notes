# Fonctions Python

Une fonction est un bloc de code qui ne s'exécute que lorsqu'elle est appelée. Vous pouvez passer des données, appelées paramètres, à une fonction, et une fonction peut renvoyer des données en tant que résultat.

## Créer une Fonction
Pour définir une fonction en Python, utilisez le mot-clé `def` :

### Exemple
```python
def ma_fonction():
    print("Bonjour depuis une fonction")
```

## Appeler une Fonction
Pour appeler une fonction, utilisez son nom suivi de parenthèses :

### Exemple
```python
def ma_fonction():
    print("Bonjour depuis une fonction")

ma_fonction()
```

## Arguments
Les informations peuvent être passées aux fonctions sous forme d'arguments. Les arguments sont spécifiés après le nom de la fonction, à l'intérieur des parenthèses.

### Exemple
```python
def ma_fonction(prénom):
    print(prénom + " Refsnes")

ma_fonction("Emil")
ma_fonction("Tobias")
ma_fonction("Linus")
```

## Nombre d'Arguments
Par défaut, une fonction doit être appelée avec le bon nombre d'arguments.

### Exemple
```python
def ma_fonction(prénom, nom):
    print(prénom + " " + nom)

ma_fonction("Emil", "Refsnes")
```

## Arguments Arbitraries, *args
Si vous ne savez pas combien d'arguments seront passés à votre fonction, ajoutez un `*` avant le nom du paramètre.

### Exemple
```python
def ma_fonction(*enfants):
    print("Le plus jeune enfant est " + enfants[2])

ma_fonction("Emil", "Tobias", "Linus")
```

## Arguments Clés
Vous pouvez également envoyer des arguments avec la syntaxe `clé = valeur`.

### Exemple
```python
def ma_fonction(enfant3, enfant2, enfant1):
    print("Le plus jeune enfant est " + enfant3)

ma_fonction(enfant1="Emil", enfant2="Tobias", enfant3="Linus")
```

## Arguments Clés Arbitraries, **kwargs
Pour accepter un nombre inconnu d'arguments clés, ajoutez deux astérisques `**` avant le nom du paramètre.

### Exemple
```python
def ma_fonction(**enfant):
    print("Son nom de famille est " + enfant["nom"])

ma_fonction(prénom="Tobias", nom="Refsnes")
```

## Valeur Par Défaut des Paramètres
Vous pouvez définir une valeur par défaut pour un paramètre.

### Exemple
```python
def ma_fonction(pays="Norvège"):
    print("Je viens de " + pays)

ma_fonction("Suède")
ma_fonction("Inde")
ma_fonction()
```

## Passer une Liste en Argument
Vous pouvez envoyer n'importe quel type de données à une fonction.

### Exemple
```python
def ma_fonction(nourriture):
    for x in nourriture:
        print(x)

fruits = ["pomme", "banane", "cerise"]
ma_fonction(fruits)
```

## Valeurs de Retour
Pour renvoyer une valeur d'une fonction, utilisez l'instruction `return`.

### Exemple
```python
def ma_fonction(x):
    return 5 * x

print(ma_fonction(3))
```

## Instruction Pass
Les définitions de fonction ne peuvent pas être vides ; utilisez l'instruction `pass` pour éviter une erreur.

### Exemple
```python
def ma_fonction():
    pass
```

## Arguments Positifs Seulement
Vous pouvez spécifier qu'une fonction n'accepte que des arguments positionnels.

### Exemple
```python
def ma_fonction(x, /):
    print(x)

ma_fonction(3)
```

## Arguments Clés Seulement
Pour qu'une fonction n'accepte que des arguments clés, ajoutez un `*` avant les arguments.

### Exemple
```python
def ma_fonction(*, x):
    print(x)

ma_fonction(x=3)
```

## Combiner Arguments Positifs et Clés
Vous pouvez combiner les deux types d'arguments dans la même fonction.

### Exemple
```python
def ma_fonction(a, b, /, *, c, d):
    print(a + b + c + d)

ma_fonction(5, 6, c=7, d=8)
```