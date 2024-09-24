# Python Datetime

### Python Dates
En Python, les dates ne sont pas un type de données propre, mais le module `datetime` permet de travailler avec des objets date.

```python
import datetime

x = datetime.datetime.now()
print(x)
```

Lorsque ce code est exécuté, le résultat affiche la date actuelle sous la forme :

```
2024-09-24 18:40:16.780282
```

Ce format contient l'année, le mois, le jour, l'heure, la minute, la seconde et la microseconde.

### Extraire des informations
Vous pouvez extraire des parties spécifiques de la date, comme l'année ou le jour de la semaine :

```python
import datetime

x = datetime.datetime.now()

print(x.year)
print(x.strftime("%A"))  # Affiche le nom du jour de la semaine
```

### Créer des objets Date
Pour créer une date, utilisez la classe `datetime()` du module `datetime`, qui prend comme paramètres obligatoires l'année, le mois et le jour.

```python
import datetime

x = datetime.datetime(2020, 5, 17)

print(x)
```

### La méthode `strftime()`
La méthode `strftime()` formate les objets date en chaînes lisibles. Elle prend un paramètre pour spécifier le format.

```python
import datetime

x = datetime.datetime(2018, 6, 1)

print(x.strftime("%B"))  # Affiche le mois sous forme de chaîne
```

### Codes de formatage pour `strftime()`
Voici quelques codes de formatage pour personnaliser la sortie des dates :

- `%a` : Nom court du jour de la semaine (ex: Wed)
- `%A` : Nom complet du jour de la semaine (ex: Wednesday)
- `%d` : Jour du mois, 01-31 (ex: 31)
- `%b` : Nom court du mois (ex: Dec)
- `%B` : Nom complet du mois (ex: December)
- `%Y` : Année complète (ex: 2018)
- `%H` : Heure (00-23)
- `%M` : Minute (00-59)
- `%S` : Seconde (00-59)
- `%f` : Microseconde (000000-999999)
