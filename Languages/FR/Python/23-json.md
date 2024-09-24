# Python JSON

### Qu'est-ce que JSON ?
JSON est une syntaxe pour stocker et échanger des données. Il est écrit en notation d'objet JavaScript.

### JSON en Python
Python dispose d'un module intégré appelé `json`, qui permet de travailler avec des données JSON.

```python
import json
```

### Convertir du JSON en Python
La méthode `json.loads()` permet de convertir une chaîne JSON en un dictionnaire Python.

```python
import json

# une chaîne JSON
x = '{ "name":"John", "age":30, "city":"New York"}'

# conversion en dictionnaire Python
y = json.loads(x)

print(y["age"])  # Affiche 30
```

### Convertir de Python en JSON
La méthode `json.dumps()` permet de convertir un objet Python en une chaîne JSON.

```python
import json

# un dictionnaire Python
x = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# conversion en chaîne JSON
y = json.dumps(x)

print(y)
```

### Objets Python compatibles avec JSON
Les objets Python suivants peuvent être convertis en JSON :
- `dict`
- `list`
- `tuple`
- `str`
- `int`
- `float`
- `True`, `False`
- `None`

### Exemple de conversion d'objets Python en JSON

```python
import json

print(json.dumps({"name": "John", "age": 30}))
print(json.dumps(["apple", "bananas"]))
print(json.dumps(("apple", "bananas")))
print(json.dumps("hello"))
print(json.dumps(42))
print(json.dumps(31.76))
print(json.dumps(True))
print(json.dumps(False))
print(json.dumps(None))
```

### Équivalences entre Python et JSON
| Python   | JSON      |
|----------|-----------|
| dict     | Object    |
| list     | Array     |
| tuple    | Array     |
| str      | String    |
| int      | Number    |
| float    | Number    |
| True     | true      |
| False    | false     |
| None     | null      |

### Conversion d'un objet Python contenant plusieurs types

```python
import json

x = {
  "name": "John",
  "age": 30,
  "married": True,
  "divorced": False,
  "children": ("Ann", "Billy"),
  "pets": None,
  "cars": [
    {"model": "BMW 230", "mpg": 27.5},
    {"model": "Ford Edge", "mpg": 24.1}
  ]
}

print(json.dumps(x))
```

### Formatage du résultat
Pour rendre le résultat JSON plus lisible, utilisez le paramètre `indent` pour ajouter des indentations.

```python
json.dumps(x, indent=4)
```

### Changer les séparateurs
Utilisez le paramètre `separators` pour définir des séparateurs personnalisés.

```python
json.dumps(x, indent=4, separators=(". ", " = "))
```

### Trier les clés
Le paramètre `sort_keys=True` permet de trier les clés dans le résultat JSON.

```python
json.dumps(x, indent=4, sort_keys=True)
```