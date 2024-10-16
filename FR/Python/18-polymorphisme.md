# Polymorphisme Python

### Polymorphisme en Programmation
Le **polymorphisme** signifie "plusieurs formes". En programmation, cela fait référence à des méthodes, fonctions ou opérateurs portant le même nom, mais pouvant être exécutés sur différents objets ou classes.

### Polymorphisme des Fonctions

#### Utilisation de la fonction `len()` sur différents objets
- **Chaîne de caractères** : `len()` retourne le nombre de caractères.
  ```python
  x = "Hello World!"
  print(len(x))  # 12
  ```

- **Tuple** : `len()` retourne le nombre d'éléments.
  ```python
  mytuple = ("apple", "banana", "cherry")
  print(len(mytuple))  # 3
  ```

- **Dictionnaire** : `len()` retourne le nombre de paires clé/valeur.
  ```python
  thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}
  print(len(thisdict))  # 3
  ```

### Polymorphisme dans les Classes
Le polymorphisme est souvent utilisé dans les méthodes des classes, où plusieurs classes peuvent avoir des méthodes portant le même nom.

#### Exemple avec des classes `Car`, `Boat`, et `Plane` ayant la même méthode `move()` :
```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def move(self):
        print("Drive!")

class Boat:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def move(self):
        print("Sail!")

class Plane:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def move(self):
        print("Fly!")

car1 = Car("Ford", "Mustang")
boat1 = Boat("Ibiza", "Touring 20")
plane1 = Plane("Boeing", "747")

for vehicle in (car1, boat1, plane1):
    vehicle.move()
```
Ici, la méthode `move()` est exécutée pour chaque objet de manière polymorphique, bien qu'elle soit définie différemment dans chaque classe.

### Polymorphisme et Héritage
Les classes enfant peuvent hériter de méthodes du parent, mais elles peuvent aussi les redéfinir pour les personnaliser.

#### Exemple avec une classe parente `Vehicle` :
```python
class Vehicle:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def move(self):
        print("Move!")

class Car(Vehicle):
    pass  # Inherits from Vehicle

class Boat(Vehicle):
    def move(self):
        print("Sail!")

class Plane(Vehicle):
    def move(self):
        print("Fly!")

car1 = Car("Ford", "Mustang")
boat1 = Boat("Ibiza", "Touring 20")
plane1 = Plane("Boeing", "747")

for vehicle in (car1, boat1, plane1):
    print(vehicle.brand)
    print(vehicle.model)
    vehicle.move()
```
Dans cet exemple, la classe `Car` hérite des propriétés et méthodes de `Vehicle` sans les redéfinir, tandis que `Boat` et `Plane` redéfinissent la méthode `move()`.