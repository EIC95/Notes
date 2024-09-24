# Python Entrée Utilisateur

### Entrée utilisateur
Python permet de demander une entrée à l'utilisateur. Cela signifie que nous pouvons demander à l'utilisateur de fournir des informations qui seront utilisées dans le programme.

La méthode d'entrée diffère entre Python 3.6 et Python 2.7.

- **Python 3.6** utilise la méthode `input()`.
- **Python 2.7** utilise la méthode `raw_input()`.

### Exemple en Python 3.6

Voici un exemple qui demande un nom d'utilisateur, et une fois saisi, l'affiche à l'écran :

```python
username = input("Entrez le nom d'utilisateur : ")
print("Le nom d'utilisateur est : " + username)
```

### Exemple en Python 2.7

```python
username = raw_input("Entrez le nom d'utilisateur : ")
print("Le nom d'utilisateur est : " + username)
```

### Comportement de l'entrée

Lorsque le programme atteint la fonction `input()`, il s'arrête et attend que l'utilisateur entre une valeur. Il continue l'exécution une fois que l'utilisateur a donné une entrée.