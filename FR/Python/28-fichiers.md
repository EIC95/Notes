# Gestion des fichiers en Python

La gestion des fichiers en Python permet de lire, écrire et supprimer des fichiers de manière efficace.

## Ouvrir des fichiers

### Modes d'ouverture

Pour ouvrir un fichier en Python, vous utilisez la fonction `open()`. Les modes d'ouverture définissent comment vous pouvez interagir avec le fichier :

| Mode d'ouverture | Signification                                     |
|------------------|--------------------------------------------------|
| `'r'`            | Lecture (read) - Ouvre le fichier pour lire. Si le fichier n'existe pas, une erreur sera levée. |
| `'w'`            | Écriture (write) - Ouvre le fichier pour écrire. Si le fichier existe, son contenu est écrasé. |
| `'a'`            | Ajout (append) - Ouvre le fichier pour ajouter du contenu à la fin. Si le fichier n'existe pas, il est créé. |
| `'r+'`           | Lecture et écriture (read and write) - Ouvre le fichier pour lire et écrire. Le fichier doit exister. |
| `'wb'`           | Écriture binaire (write binary) - Ouvre le fichier pour écrire en mode binaire. |
| `'rb'`           | Lecture binaire (read binary) - Ouvre le fichier pour lire en mode binaire. |
| `'w+'`           | Lecture et écriture (create if not exists) - Ouvre le fichier pour lire et écrire. Le fichier est créé s'il n'existe pas. |
| `'rU'`           | Lecture universelle (universal read) - Permet de lire des fichiers texte en ignorant les différences de saut de ligne entre les systèmes d'exploitation. |

### Exemple d'ouverture d'un fichier

Voici des exemples d'utilisation de la méthode `open()` pour lire et écrire des fichiers :

#### Lecture d'un fichier
```python
# Ouvrir un fichier en mode lecture
with open('example.txt', 'r') as file:
    content = file.read()  # Lire tout le contenu
    print(content)

# Lire ligne par ligne
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())  # Afficher chaque ligne sans espace en début et fin
```

#### Écriture dans un fichier
```python
# Écrire dans un fichier
with open('example.txt', 'w') as file:
    file.write("Ceci est une ligne.\n")
    file.write("Ceci est une autre ligne.\n")

# Ajouter du contenu à un fichier existant
with open('example.txt', 'a') as file:
    file.write("Ceci est une ligne ajoutée.\n")
```

## Supprimer des fichiers

Pour supprimer un fichier, vous devez utiliser le module `os`. Voici comment procéder :

### Exemple de suppression d'un fichier
```python
import os

# Supprimer un fichier
if os.path.exists("example.txt"):
    os.remove("example.txt")
    print("Le fichier a été supprimé.")
else:
    print("Le fichier n'existe pas.")
```
