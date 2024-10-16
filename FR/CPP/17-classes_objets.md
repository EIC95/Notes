# Classes et Objets en C++

## Déclaration d'une Classe

Pour créer une classe, utilisez le mot-clé `class`, suivi du nom de la classe, et définissez les attributs et méthodes entre accolades.

```cpp
class Car {
public:
    std::string model;
    int year;

    void start() {
        std::cout << "Car started";
    }
};
```

## Création d'un Objet

Pour créer un objet, spécifiez le nom de la classe, suivi du nom de l'objet.

```cpp
Car myCar;
myCar.model = "Toyota";
myCar.year = 2022;
myCar.start();
```

## Définition des Méthodes

Il existe deux manières de définir des fonctions appartenant à une classe : à l'intérieur de la définition de la classe ou en dehors de celle-ci.

### Définition à l'intérieur de la classe

```cpp
class Car {
public:
    void start() {
        std::cout << "Car started";
    }
};
```

### Définition à l'extérieur de la classe

Déclarez d'abord la méthode dans la classe, puis définissez-la en dehors de celle-ci.

```cpp
class Car {
public:
    void start();
};

void Car::start() {
    std::cout << "Car started";
}
```

## Constructeur

Pour créer un constructeur, utilisez le même nom que la classe, suivi de parenthèses. Les constructeurs peuvent prendre des paramètres pour initialiser les attributs.

```cpp
class Car {
public:
    std::string model;
    int year;

    // Constructeur
    Car(std::string m, int y) : model(m), year(y) {}
};
```

## Utilisation du Constructeur

Créez un objet en passant les arguments au constructeur.

```cpp
Car myCar("Toyota", 2022);
std::cout << myCar.model; // Affiche "Toyota"
```
