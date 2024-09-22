# Chaînes en Python

Les chaînes en Python sont entourées de guillemets simples ou doubles.

```python
print("Hello")
print('Hello')
```

Les deux instructions ci-dessus sont équivalentes. Vous pouvez utiliser des guillemets à l'intérieur d'une chaîne, à condition qu'ils ne correspondent pas aux guillemets entourant la chaîne.

```python
print("It's alright")             # Utilisation de guillemets simples à l'intérieur
print('He is called "Johnny"')    # Utilisation de guillemets doubles à l'intérieur
```

## Chaînes Multilignes

Vous pouvez affecter une chaîne multilignes à une variable en utilisant trois guillemets simples ou trois guillemets doubles.

```python
# Avec des guillemets doubles
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""
print(a)

# Avec des guillemets simples
b = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''
print(b)
```

**Note** : Les sauts de ligne dans la chaîne sont conservés tels quels.

## Les chaînes sont des tableaux

En Python, les chaînes sont des **tableaux d'octets** représentant des caractères Unicode. Vous pouvez accéder à des éléments de la chaîne en utilisant des crochets carrés.

```python
a = "Hello, World!"
print(a[1])    # Imprime le deuxième caractère 'e'
```

## Boucle sur une chaîne

Puisque les chaînes sont des tableaux, vous pouvez parcourir les caractères avec une boucle `for`.

```python
for x in "banana":
    print(x)
```

## Longueur d'une chaîne

Pour obtenir la longueur d'une chaîne, utilisez la fonction `len()`.

```python
a = "Hello, World!"
print(len(a))  # Imprime 13
```

## Vérifier la présence d'une chaîne

Pour vérifier si une phrase ou un caractère est présent dans une chaîne, vous pouvez utiliser le mot-clé `in`.

```python
txt = "The best things in life are free!"
print("free" in txt)   # Imprime True
```

Vous pouvez aussi l'utiliser dans une condition `if` :

```python
if "free" in txt:
    print("Yes, 'free' is present.")
```

## Vérifier si une chaîne n'est PAS présente

Pour vérifier si une phrase ou un caractère **n'est pas** présent dans une chaîne, utilisez le mot-clé `not in`.

```python
txt = "The best things in life are free!"
print("expensive" not in txt)   # Imprime True
```

Exemple avec une condition `if` :

```python
if "expensive" not in txt:
    print("No, 'expensive' is NOT present.")
```

## Tranchage des Chaînes en Python (Slicing)

Le tranchage vous permet de renvoyer une portion d'une chaîne en utilisant la syntaxe d'indexation. Vous spécifiez un indice de départ et un indice de fin, séparés par un deux-points `:`, pour obtenir une partie de la chaîne.

**Exemple de base**

Obtenez les caractères de la position 2 à la position 5 (non incluse) dans la chaîne :

```python
b = "Hello, World!"
print(b[2:5])   # Affiche "llo"
```

**Remarque** : Le premier caractère a l'indice 0.

Si vous omettez l'indice de départ, la tranche commencera au premier caractère.

```python
b = "Hello, World!"
print(b[:5])    # Affiche "Hello"
```

Si vous omettez l'indice de fin, la tranche continuera jusqu'à la fin de la chaîne.

```python
b = "Hello, World!"
print(b[2:])    # Affiche "llo, World!"
```

Vous pouvez utiliser des **indices négatifs** pour commencer le tranchage à partir de la fin de la chaîne. Par exemple, pour obtenir les caractères de l'indice -5 (le "o" dans "World!") jusqu'à l'indice -2 (le "d" n'est pas inclus) :

```python
b = "Hello, World!"
print(b[-5:-2])   # Affiche "orl"
```

Avec l'indexation négative, Python compte les caractères à partir de la fin de la chaîne, où `-1` est le dernier caractère.

## Concaténer des Chaînes

Vous pouvez concaténer (joindre) des chaînes en utilisant l'opérateur `+`.

```python
a = "Bonjour"
b = " tout le monde!"
resultat = a + b                   # "Bonjour tout le monde!"
```

## Formatage des Chaînes en Python

Les f-strings ont été introduites dans Python 3.6 et sont maintenant la manière préférée de formater des chaînes. Pour spécifier une f-string, ajoutez un `f` devant la chaîne, et insérez des accolades `{}` comme des **espaces réservés** pour les variables ou les opérations.

```python
age = 36
txt = f"My name is John, I am {age}"
print(txt)   # Affiche "My name is John, I am 36"
```

Un espace réservé dans une f-string peut contenir des variables, des opérations, des fonctions, et même des modificateurs pour formater la valeur.

```python
txt = f"The price is {50 * 60} dollars"
print(txt)   # Affiche "The price is 3000 dollars"
```

Vous pouvez ajouter un **modificateur** pour formater la valeur. Par exemple, `:.2f` signifie que le nombre doit être affiché avec 2 décimales.

```python
price = 59
txt = f"The price is {price:.2f} dollars"
print(txt)   # Affiche "The price is 59.00 dollars"
```

## Caractères d'échappement en Python

Un caractère d'échappement vous permet d'insérer des caractères spéciaux qui seraient normalement illégaux dans une chaîne. Pour ce faire, vous utilisez une barre oblique inverse `\` suivie du caractère que vous souhaitez insérer.

**Exemple**

Vous ne pouvez pas inclure des guillemets doubles à l'intérieur d'une chaîne entourée de guillemets doubles sans utiliser un caractère d'échappement :

```python
# Cela provoque une erreur
txt = "We are the so-called "Vikings" from the north."

# Utilisation du caractère d'échappement
txt = "We are the so-called \"Vikings\" from the north."
print(txt)   # Affiche : We are the so-called "Vikings" from the north.
```

Voici une liste des caractères d'échappement couramment utilisés en Python :

| Code   | Résultat              |
|--------|-----------------------|
| `\'`   | Guillemets simples     |
| `\"`   | Guillemets doubles     |
| `\\`   | Barre oblique inverse  |
| `\n`   | Saut de ligne          |
| `\r`   | Retour chariot         |
| `\t`   | Tabulation             |
| `\b`   | Retour arrière         |
| `\f`   | Saut de page           |
| `\ooo` | Valeur octale          |
| `\xhh` | Valeur hexadécimale    |

# Méthodes Utiles des Chaînes en Python

Python propose un ensemble de méthodes intégrées que vous pouvez utiliser sur les chaînes. Ces méthodes ne modifient pas la chaîne d'origine, mais renvoient une nouvelle chaîne modifiée.

| Méthode        | Description                                                    |
|----------------|----------------------------------------------------------------|
| `capitalize()` | Convertit le premier caractère en majuscule                    |
| `casefold()`   | Convertit la chaîne en minuscules (plus agressif que `lower()`) |
| `center()`     | Retourne une chaîne centrée                                    |
| `count()`      | Retourne le nombre d'occurrences d'une valeur spécifiée        |
| `endswith()`   | Retourne `True` si la chaîne se termine par la valeur spécifiée|
| `find()`       | Cherche une valeur dans la chaîne et retourne la position      |
| `format()`     | Formate les valeurs spécifiées dans la chaîne                  |
| `index()`      | Comme `find()`, mais lève une erreur si la valeur n'est pas trouvée |
| `isalnum()`    | Retourne `True` si tous les caractères sont alphanumériques    |
| `isalpha()`    | Retourne `True` si tous les caractères sont alphabétiques      |
| `isdigit()`    | Retourne `True` si tous les caractères sont des chiffres       |
| `islower()`    | Retourne `True` si tous les caractères sont en minuscules      |
| `isnumeric()`  | Retourne `True` si tous les caractères sont numériques         |
| `isspace()`    | Retourne `True` si tous les caractères sont des espaces blancs |
| `istitle()`    | Retourne `True` si la chaîne suit les règles des titres (première lettre de chaque mot en majuscule) |
| `isupper()`    | Retourne `True` si tous les caractères sont en majuscules      |
| `join()`       | Joint les éléments d'un itérable à la fin de la chaîne         |
| `lower()`      | Convertit la chaîne en minuscules                              |
| `lstrip()`     | Supprime les espaces à gauche                                  |
| `replace()`    | Remplace une valeur spécifiée par une autre                    |
| `rstrip()`     | Supprime les espaces à droite                                  |
| `split()`      | Sépare la chaîne en fonction d'un séparateur spécifié          |
| `startswith()` | Retourne `True` si la chaîne commence par la valeur spécifiée  |
| `strip()`      | Supprime les espaces au début et à la fin de la chaîne         |
| `swapcase()`   | Inverse la casse des caractères (minuscule devient majuscule et vice versa) |
| `title()`      | Convertit le premier caractère de chaque mot en majuscule      |
| `upper()`      | Convertit la chaîne en majuscules                              |

**Exemple d'utilisation**

```python
# `capitalize()`
txt = "hello world"
print(txt.capitalize())  # Résultat : "Hello world"

# `find()`
txt = "Hello, world!"
print(txt.find("world"))  # Résultat : 7

# `replace()`
txt = "I like apples"
print(txt.replace("apples", "bananas"))  # Résultat : "I like bananas"
```