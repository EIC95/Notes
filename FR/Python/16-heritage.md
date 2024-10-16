# L'héritage en Python

L'héritage nous permet de définir une classe qui hérite de toutes les méthodes et propriétés d'une autre classe. La classe parente est la classe héritée, également appelée classe de base. La classe enfant est la classe qui hérite d'une autre classe, également appelée classe dérivée.

## Créer une classe enfant

Pour créer une classe qui hérite de la fonctionnalité d'une autre classe, envoyez la classe parente en tant que paramètre lors de la création de la classe enfant :

Exemple
Créer une classe nommée `Etudiant`, qui héritera des propriétés et méthodes de la classe `Personne` :

```python
class Personne:
  def __init__(self, prenom, nom):
    self.prenom = prenom
    self.nom = nom

  def afficher_nom(self):
    print(self.prenom, self.nom)

class Etudiant(Personne):
  pass
```

Note : Utilisez le mot-clé `pass` lorsque vous ne souhaitez pas ajouter d'autres propriétés ou méthodes à la classe.

Maintenant, la classe `Etudiant` a les mêmes propriétés et méthodes que la classe `Personne`.

Exemple
Utilisez la classe `Etudiant` pour créer un objet, puis exécutez la méthode `afficher_nom` :

```python
x = Etudiant("Mike", "Olsen")
x.afficher_nom()
```

## Ajouter la fonction `__init__()`

Ajoutez la fonction `__init__()` à la classe `Etudiant` :

```python
class Etudiant(Personne):
  def __init__(self, prenom, nom):
    # ajouter des propriétés, etc.
```

Lorsque vous ajoutez la fonction `__init__()`, la classe enfant n'héritera plus de la fonction `__init__()` de la classe parente.

Note : La fonction `__init__()` de la classe enfant remplace l'héritage de la fonction `__init__()` de la classe parente.

Pour conserver l'héritage de la fonction `__init__()` de la classe parente, ajoutez un appel à la fonction `__init__()` de la classe parente :

Exemple

```python
class Etudiant(Personne):
  def __init__(self, prenom, nom):
    Personne.__init__(self, prenom, nom)
```

## Utiliser la fonction `super()`

Python a également une fonction `super()` qui fera en sorte que la classe enfant hérite de toutes les méthodes et propriétés de sa classe parente :

Exemple

```python
class Etudiant(Personne):
  def __init__(self, prenom, nom):
    super().__init__(prenom, nom)
```

En utilisant la fonction `super()`, vous n'avez pas besoin d'utiliser le nom de l'élément parent, il héritera automatiquement des méthodes et propriétés de sa classe parente.

## Ajouter des propriétés

Exemple
Ajoutez une propriété appelée `annee_graduation` à la classe `Etudiant` :

```python
class Etudiant(Personne):
  def __init__(self, prenom, nom, annee):
    super().__init__(prenom, nom)
    self.annee_graduation = annee

x = Etudiant("Mike", "Olsen", 2019)
```

## Ajouter des méthodes

Exemple
Ajoutez une méthode appelée `bienvenue` à la classe `Etudiant` :

```python
class Etudiant(Personne):
  def __init__(self, prenom, nom, annee):
    super().__init__(prenom, nom)
    self.annee_graduation = annee

  def bienvenue(self):
    print("Bienvenue", self.prenom, self.nom, "à la classe de", self.annee_graduation)
```
