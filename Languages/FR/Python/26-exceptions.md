# Python Try Except

### Gestion des exceptions
Le bloc `try` vous permet de tester un bloc de code pour détecter des erreurs, tandis que le bloc `except` vous permet de gérer ces erreurs.

Le bloc `else` vous permet d'exécuter du code s'il n'y a pas d'erreur, et le bloc `finally` s'exécute, qu'il y ait ou non une erreur dans les blocs `try` ou `except`.

### Exemple de base

Voici un exemple simple où une exception est levée car `x` n'est pas défini :

```python
try:
  print(x)
except:
  print("Une exception s'est produite")
```

Sans le bloc `try`, le programme s'arrêterait et afficherait un message d'erreur.

### Plusieurs exceptions
Vous pouvez gérer plusieurs types d'exceptions spécifiques en utilisant plusieurs blocs `except`.

```python
try:
  print(x)
except NameError:
  print("La variable x n'est pas définie")
except:
  print("Une autre erreur s'est produite")
```

### Bloc else
Le bloc `else` s'exécute uniquement si aucune erreur n'est levée dans le bloc `try`.

```python
try:
  print("Bonjour")
except:
  print("Une erreur s'est produite")
else:
  print("Aucune erreur ne s'est produite")
```

### Bloc finally
Le bloc `finally` s'exécute toujours, que le bloc `try` lève une exception ou non.

```python
try:
  print(x)
except:
  print("Une erreur s'est produite")
finally:
  print("Le bloc 'try except' est terminé")
```

Cela est utile pour fermer des objets ou libérer des ressources.

### Lever une exception
Vous pouvez également lever une exception vous-même en utilisant le mot-clé `raise`.

#### Exemple 1 : Lever une exception si une condition est remplie

```python
x = -1

if x < 0:
  raise Exception("Désolé, aucun nombre en dessous de zéro n'est autorisé")
```

#### Exemple 2 : Lever une exception avec un type spécifique

```python
x = "bonjour"

if not type(x) is int:
  raise TypeError("Seuls les entiers sont autorisés")
```