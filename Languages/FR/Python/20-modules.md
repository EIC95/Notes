# Python Modules

### Qu’est-ce qu’un module ?
Un module est un fichier contenant un ensemble de fonctions, variables, ou classes que vous pouvez inclure dans votre application, semblable à une bibliothèque de code.

### Créer un module
Pour créer un module, enregistrez le code dans un fichier avec l'extension `.py`.

```python
# mymodule.py
def greeting(name):
  print("Hello, " + name)
```

### Utiliser un module
Vous pouvez importer et utiliser un module avec l'instruction `import`.

```python
import mymodule

mymodule.greeting("Jonathan")
```

### Variables dans le module
Un module peut contenir des variables en plus des fonctions.

```python
# mymodule.py
person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}
```

Vous pouvez ensuite importer et utiliser ces variables :

```python
import mymodule

a = mymodule.person1["age"]
print(a)
```

### Renommer un module
Lors de l'importation, vous pouvez renommer un module avec `as`.

```python
import mymodule as mx

a = mx.person1["age"]
print(a)
```

### Modules intégrés
Python propose plusieurs modules intégrés que vous pouvez importer directement, comme `platform`.

```python
import platform

x = platform.system()
print(x)
```

### Utilisation de `dir()`
La fonction `dir()` liste tous les attributs et méthodes d'un module.

```python
import platform

x = dir(platform)
print(x)
```

### Importer des parties spécifiques d'un module
Vous pouvez importer seulement certaines parties d’un module.

```python
from mymodule import person1

print(person1["age"])
```