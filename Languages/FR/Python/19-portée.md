# Portée des Variables en Python

### Portée (Scope)
La **portée** d'une variable définit où elle est accessible dans le code. Une variable est seulement disponible à l'intérieur de la région dans laquelle elle est créée.

### Portée Locale

Une variable créée à l'intérieur d'une fonction appartient à la portée locale de cette fonction et ne peut être utilisée qu'à l'intérieur de celle-ci.

#### Exemple
```python
def myfunc():
    x = 300
    print(x)

myfunc()  # Affiche 300
```
Dans cet exemple, la variable `x` est locale à la fonction `myfunc()`.

### Fonction à l'Intérieur d'une Fonction

Une variable locale peut être accessible par une fonction interne à une autre fonction.

#### Exemple
```python
def myfunc():
    x = 300
    def myinnerfunc():
        print(x)
    myinnerfunc()

myfunc()  # Affiche 300
```
Ici, `myinnerfunc()` peut accéder à la variable `x` définie dans `myfunc()`.

### Portée Globale

Une variable créée à l'extérieur de toute fonction est une **variable globale** et peut être utilisée à la fois dans la portée globale et locale.

#### Exemple
```python
x = 300

def myfunc():
    print(x)

myfunc()  # Affiche 300
print(x)  # Affiche 300
```
La variable `x` est accessible partout, car elle est définie dans la portée globale.

### Nommage des Variables

Si vous utilisez une variable avec le même nom dans les portées locale et globale, Python les considère comme deux variables différentes.

#### Exemple
```python
x = 300

def myfunc():
    x = 200
    print(x)

myfunc()  # Affiche 200
print(x)  # Affiche 300
```
Dans cet exemple, la variable `x` à l'intérieur de `myfunc()` est locale et n'affecte pas la variable globale `x`.

### Mot-clé `global`

Le mot-clé **`global`** permet de déclarer une variable comme globale, même si elle est définie dans une fonction.

#### Exemple
```python
def myfunc():
    global x
    x = 300

myfunc()
print(x)  # Affiche 300
```
Dans cet exemple, `x` est défini comme une variable globale à l'intérieur de `myfunc()`.

Vous pouvez également utiliser le mot-clé `global` pour modifier une variable globale à partir d'une fonction.

#### Exemple
```python
x = 300

def myfunc():
    global x
    x = 200

myfunc()
print(x)  # Affiche 200
```
La variable globale `x` est modifiée dans `myfunc()`.

### Mot-clé `nonlocal`

Le mot-clé **`nonlocal`** est utilisé pour accéder à une variable définie dans une fonction extérieure à une fonction imbriquée, mais qui n'est pas globale.

#### Exemple
```python
def myfunc1():
    x = "Jane"
    def myfunc2():
        nonlocal x
        x = "hello"
    myfunc2()
    return x

print(myfunc1())  # Affiche "hello"
```
Dans cet exemple, `nonlocal` permet à `myfunc2()` de modifier la variable `x` définie dans `myfunc1()`.