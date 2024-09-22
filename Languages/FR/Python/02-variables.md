# Python Variables

## Les Variables en Python

En Python, les variables sont créées automatiquement dès qu'on leur assigne une valeur. Le type de la variable est également déterminé automatiquement en fonction de la valeur qui lui est assignée. 

Exemples :

```python
x = 10       # Variable de type entier (int)
y = 3.14     # Variable de type flottant (float)
name = "Bob" # Variable de type chaîne de caractères (str)
is_active = True  # Variable de type booléen (bool)
```

### Changement de type automatique

Le type d'une variable peut changer si on lui assigne une nouvelle valeur d'un autre type :

```python
x = 5         # `x` est de type entier (int)
x = "Bonjour" # Maintenant, `x` est de type chaîne de caractères (str)
```

Voici la suite de tes notes sur les variables en Python, rédigées en Markdown :

## Noms de Variables

Les noms de variables en Python doivent suivre certaines règles :

- **Commencer par une lettre ou un underscore (_)**.
- **Ne pas commencer par un chiffre**.
- Peut contenir des lettres, des chiffres et des underscores (a-z, A-Z, 0-9, et _).
- Les noms de variables sont sensibles à la casse, c'est-à-dire que `age`, `Age` et `AGE` sont trois variables différentes.

Exemples :
```python
age = 25
_age = 30
age2 = 35
```

Noms de variables incorrects :
```python
2age = 25  # Commence par un chiffre (interdit)
age! = 30  # Caractère spécial interdit
```

## Attribuer Plusieurs Valeurs

Python permet d'attribuer plusieurs valeurs à plusieurs variables en une seule ligne.

- **Attribuer plusieurs valeurs** :
    ```python
    x, y, z = 1, 2, 3
    print(x, y, z)  # Affiche : 1 2 3
    ```

- **Attribuer la même valeur à plusieurs variables** :
    ```python
    a = b = c = 10
    print(a, b, c)  # Affiche : 10 10 10
    ```

## Variables Globales

Les variables déclarées en dehors d'une fonction sont globales et peuvent être utilisées n'importe où dans le programme. Si vous devez accéder ou modifier une variable globale à l'intérieur d'une fonction, utilisez le mot-clé `global`.

- **Accéder à une variable globale** :
    ```python
    x = 10  # Variable globale

    def ma_fonction():
        print(x)  # Accès à la variable globale

    ma_fonction()  # Affiche : 10
    ```

- **Modifier une variable globale dans une fonction** :
    ```python
    y = 20  # Variable globale

    def modifier_global():
        global y  # Indique que l'on veut modifier la variable globale
        y = 30

    modifier_global()
    print(y)  # Affiche : 30
    ```

- **Utiliser des variables globales et locales** :
    Les variables créées à l'intérieur d'une fonction sont locales et ne peuvent pas être utilisées en dehors de cette fonction, sauf si elles sont déclarées globales.

    ```python
    z = 5  # Variable globale

    def ma_fonction():
        z = 10  # Variable locale
        print(z)  # Affiche : 10 (variable locale)

    ma_fonction()
    print(z)  # Affiche : 5 (variable globale)
    ```