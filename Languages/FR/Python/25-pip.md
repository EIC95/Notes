# Python PIP

### Qu'est-ce que PIP ?
PIP est un gestionnaire de paquets pour Python. Il permet d'installer, de mettre à jour et de désinstaller des paquets Python, qui sont des bibliothèques de code que vous pouvez inclure dans votre projet.

> **Remarque** : Si vous avez Python version 3.4 ou plus récente, PIP est inclus par défaut.

### Qu'est-ce qu'un paquet ?
Un paquet contient tous les fichiers nécessaires pour un module Python.

### Vérifier si PIP est installé
Pour vérifier si PIP est installé sur votre système, ouvrez une interface de ligne de commande et exécutez la commande suivante :

```bash
pip --version
```

### Installer PIP
Si PIP n'est pas installé, vous pouvez le télécharger et l'installer depuis [la page de PIP](https://pypi.org/project/pip/).

### Télécharger un paquet
Pour installer un paquet, utilisez la commande `pip install` suivie du nom du paquet.

Exemple pour télécharger un paquet nommé "camelcase" :

```bash
pip install camelcase
```

### Utiliser un paquet
Une fois installé, vous pouvez importer le paquet dans votre projet et l'utiliser.

```python
import camelcase

c = camelcase.CamelCase()
txt = "hello world"
print(c.hump(txt))
```

### Trouver des paquets
Vous pouvez trouver plus de paquets sur le site [PyPI](https://pypi.org/).

### Supprimer un paquet
Pour désinstaller un paquet, utilisez la commande `pip uninstall` suivie du nom du paquet.

Exemple pour désinstaller "camelcase" :

```bash
pip uninstall camelcase
```

### Lister les paquets installés
Pour voir tous les paquets installés sur votre système, utilisez la commande suivante :

```bash
pip list
```

Résultat :

```bash
Package         Version
-----------------------
camelcase       0.2
mysql-connector 2.1.6
pip             18.1
pymongo         3.6.1
setuptools      39.0.1
```