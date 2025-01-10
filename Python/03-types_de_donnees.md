# Types de Données en Python

En Python, chaque variable a un **type de données** qui détermine la manière dont elle est manipulée. Python gère automatiquement le type de données lors de l'assignation, mais il est aussi possible de spécifier explicitement un type.

## Types de Données Intégrés

Les types de données sont classés en plusieurs catégories :

- **Type de texte** : `str` (chaîne de caractères)
    ```python
    x = "Bonjour"  # Chaîne de caractères
    ```

- **Types numériques** : `int` (entier), `float` (nombre à virgule flottante), `complex` (nombre complexe)
    ```python
    x = 42          # Entier
    y = 3.14       # Flottant
    z = 1 + 2j     # Nombre complexe
    ```

- **Types de séquence** : `list` (liste), `tuple` (tuple), `range` (intervalle)
    ```python
    fruits = ["pomme", "banane", "cerise"]  # Liste
    coordinates = (10.0, 20.0)              # Tuple
    numbers = range(5)                       # Intervalle
    ```

- **Type de mappage** : `dict` (dictionnaire)
    ```python
    person = {"nom": "Alice", "âge": 30}  # Dictionnaire
    ```

- **Types d'ensembles** : `set` (ensemble), `frozenset` (ensemble immuable)
    ```python
    unique_fruits = {"pomme", "banane"}    # Ensemble
    frozen_fruits = frozenset({"cerise", "kiwi"})  # Ensemble immuable
    ```

- **Type booléen** : `bool` (vrai/faux)
    ```python
    is_active = True   # Booléen
    ```

- **Types binaires** : `bytes` (octets), `bytearray` (tableau d'octets), `memoryview` (vue mémoire)
    ```python
    byte_data = b"Hello"              # Octets
    byte_array = bytearray(5)         # Tableau d'octets
    memory_view = memoryview(bytes(5)) # Vue mémoire
    ```

- **Aucun Type** : `NoneType` (valeur nulle)
    ```python
    x = None  # Aucun type
    ```

## Obtenir le Type de Données

Utilisez la fonction `type()` pour connaître le type d'une variable :

```python
x = 5
print(type(x))  # Affiche : <class 'int'>
```
