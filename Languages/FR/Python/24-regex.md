# Python RegEx

### Qu'est-ce qu'une RegEx ?
Une RegEx (expression régulière) est une séquence de caractères qui forme un modèle de recherche.

Elle est utilisée pour vérifier si une chaîne contient un motif de recherche spécifique.

### Module RegEx
Python dispose d'un module intégré appelé `re`, qui permet de travailler avec des expressions régulières.

```python
import re
```

### Exemple de RegEx en Python
Vérifier si la chaîne commence par "The" et se termine par "Spain".

```python
import re

txt = "The rain in Spain"
x = re.search("^The.*Spain$", txt)
```

### Fonctions du module `re`
Le module `re` offre plusieurs fonctions pour chercher un motif dans une chaîne :
- `findall` : retourne une liste contenant toutes les correspondances.
- `search` : retourne un objet `Match` s'il y a une correspondance.
- `split` : divise la chaîne là où il y a correspondance et retourne une liste.
- `sub` : remplace une ou plusieurs correspondances par une chaîne.

### Métacaractères
Les métacaractères sont des caractères ayant une signification spéciale dans les expressions régulières.

| Caractère | Description                 | Exemple        |
|-----------|-----------------------------|----------------|
| `[]`      | Ensemble de caractères       | `[a-m]`        |
| `\`       | Séquence spéciale            | `\d`           |
| `.`       | Tout caractère               | `he..o`        |
| `^`       | Commence par                 | `^hello`       |
| `$`       | Se termine par               | `planet$`      |
| `*`       | 0 ou plusieurs occurrences   | `he.*o`        |
| `+`       | 1 ou plusieurs occurrences   | `he.+o`        |
| `?`       | 0 ou 1 occurrence            | `he.?o`        |
| `{}`      | Nombre exact d'occurrences   | `he.{2}o`      |
| `|`       | Soit l'un, soit l'autre      | `falls|stays`  |
| `()`      | Capture et regroupe          |                |

### Séquences spéciales

| Caractère | Description                                                              | Exemple    |
|-----------|--------------------------------------------------------------------------|------------|
| `\A`      | Correspondance si les caractères sont au début de la chaîne              | `\AThe`    |
| `\b`      | Correspondance au début ou à la fin d'un mot                             | `\bain`    |
| `\B`      | Correspondance si les caractères ne sont **pas** au début ou à la fin    | `\Bain`    |
| `\d`      | Correspondance si la chaîne contient des chiffres (0-9)                  | `\d`       |
| `\D`      | Correspondance si la chaîne ne contient pas de chiffres                  | `\D`       |
| `\s`      | Correspondance avec un caractère d'espacement                            | `\s`       |
| `\S`      | Correspondance si aucun caractère d'espacement                           | `\S`       |
| `\w`      | Correspondance avec tout caractère alphabétique ou numérique             | `\w`       |
| `\W`      | Correspondance si aucun caractère alphabétique ou numérique              | `\W`       |
| `\Z`      | Correspondance si les caractères sont à la fin de la chaîne              | `Spain\Z`  |

### Ensembles

| Ensemble  | Description                                                        |
|-----------|--------------------------------------------------------------------|
| `[arn]`   | Correspondance si un des caractères est présent (a, r ou n)        |
| `[a-n]`   | Correspondance pour n'importe quelle lettre minuscule entre a et n |
| `[^arn]`  | Correspondance pour tous les caractères sauf a, r, et n            |
| `[0-9]`   | Correspondance pour tout chiffre entre 0 et 9                      |
| `[a-zA-Z]`| Correspondance pour toute lettre (minuscule ou majuscule)          |

### Fonction `findall()`
Retourne une liste de toutes les correspondances.

```python
import re

txt = "The rain in Spain"
x = re.findall("ai", txt)
print(x)
```

### Fonction `search()`
Retourne un objet `Match` si une correspondance est trouvée.

```python
import re

txt = "The rain in Spain"
x = re.search("\s", txt)
print("Premier espace trouvé à la position :", x.start())
```

### Fonction `split()`
Divise la chaîne à chaque correspondance.

```python
import re

txt = "The rain in Spain"
x = re.split("\s", txt)
print(x)
```

### Fonction `sub()`
Remplace les correspondances par une chaîne spécifiée.

```python
import re

txt = "The rain in Spain"
x = re.sub("\s", "9", txt)
print(x)
```

### Objet `Match`
Contient des informations sur la correspondance trouvée.

```python
import re

txt = "The rain in Spain"
x = re.search(r"\bS\w+", txt)
print(x.group())  # Affiche "Spain"
```
