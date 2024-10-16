# Python Dictionaries

Les dictionnaires en Python sont des collections non ordonnées, modifiables et indexées, qui utilisent des paires clé-valeur. Ils sont utilisés pour stocker des données qui sont associées par des clés uniques, ce qui permet un accès rapide à ces données.

### Accéder aux Éléments

Pour accéder à un élément d'un dictionnaire, utilisez la clé correspondante entre crochets ou la méthode `get()`.

**Exemple :**
```python
my_dict = {"nom": "Alice", "âge": 30, "ville": "Paris"}
print(my_dict["nom"])  # Affiche "Alice"
print(my_dict.get("âge"))  # Affiche 30
```

### Boucler sur les Dictionnaires

Vous pouvez parcourir un dictionnaire en utilisant une boucle `for`. Par défaut, la boucle itérera sur les clés.

**Exemple :**
```python
for clé in my_dict:
    print(clé, my_dict[clé])
```

Pour accéder aux valeurs, utilisez `.values()`, et pour les paires clé-valeur, utilisez `.items()`.

**Exemple :**
```python
for clé, valeur in my_dict.items():
    print(clé, valeur)
```

### Dictionnaires Imbriqués

Un dictionnaire imbriqué est un dictionnaire à l'intérieur d'un autre dictionnaire. Cela permet de créer des structures de données plus complexes.

**Exemple :**
```python
personne = {
    "nom": "Alice",
    "âge": 30,
    "adresse": {
        "rue": "123 rue Principale",
        "ville": "Paris"
    }
}
print(personne["adresse"]["ville"])  # Affiche "Paris"
```

### Méthodes de Dictionnaire

Python propose plusieurs méthodes intégrées pour manipuler les dictionnaires :

- **`get(clé)`** : Renvoie la valeur pour la clé spécifiée.

  **Exemple :**
  ```python
  print(my_dict.get("nom"))  # Affiche "Alice"
  ```

- **`keys()`** : Renvoie une vue des clés du dictionnaire.

  **Exemple :**
  ```python
  print(my_dict.keys())  # Affiche dict_keys(['nom', 'âge', 'ville'])
  ```

- **`values()`** : Renvoie une vue des valeurs du dictionnaire.

  **Exemple :**
  ```python
  print(my_dict.values())  # Affiche dict_values(['Alice', 30, 'Paris'])
  ```

- **`items()`** : Renvoie une vue des paires clé-valeur.

  **Exemple :**
  ```python
  print(my_dict.items())  # Affiche dict_items([('nom', 'Alice'), ('âge', 30), ('ville', 'Paris')])
  ```

- **`update(d)`** : Met à jour le dictionnaire avec les paires clé-valeur d'un autre dictionnaire.

  **Exemple :**
  ```python
  my_dict.update({"pays": "France"})
  print(my_dict)  # Affiche {'nom': 'Alice', 'âge': 30, 'ville': 'Paris', 'pays': 'France'}
  ```

- **`pop(clé)`** : Supprime la clé et renvoie sa valeur.

  **Exemple :**
  ```python
  age = my_dict.pop("âge")
  print(age)  # Affiche 30
  print(my_dict)  # Affiche {'nom': 'Alice', 'ville': 'Paris', 'pays': 'France'}
  ```

- **`popitem()`** : Supprime et renvoie une paire clé-valeur aléatoire.

  **Exemple :**
  ```python
  clé_valeur = my_dict.popitem()
  print(clé_valeur)  # Affiche une paire comme ('pays', 'France')
  print(my_dict)  # Affiche le dictionnaire sans cette paire
  ```

- **`clear()`** : Supprime tous les éléments du dictionnaire.

  **Exemple :**
  ```python
  my_dict.clear()
  print(my_dict)  # Affiche {}
  ```
