# Encapsulation en C++

L'encapsulation est un concept fondamental en programmation orientée objet qui vise à protéger les données sensibles et à exposer uniquement les fonctionnalités nécessaires aux utilisateurs d'une classe. Elle permet de regrouper les données (attributs) et les méthodes (fonctions) qui manipulent ces données dans une même unité, la classe.

## Objectif de l'Encapsulation

L'encapsulation vise à garantir que les données internes d'un objet sont protégées contre les modifications directes non souhaitées et que seules les opérations contrôlées sont autorisées. En utilisant l'encapsulation, vous pouvez éviter des modifications accidentelles des données et assurer que l'objet reste dans un état valide.

## Déclaration des Attributs comme `private`

Pour mettre en œuvre l'encapsulation, les variables ou attributs d'une classe doivent être déclarés comme `private`. Cela signifie que ces membres ne sont accessibles que depuis l'intérieur de la classe. Cela empêche les utilisateurs de modifier directement les données et assure un contrôle total sur la manière dont les données sont accédées ou modifiées.

### Exemple

```cpp
#include <iostream>

class Person {
private:
    std::string name;
    int age;

public:
    // Constructeur pour initialiser les données
    Person(std::string n, int a) : name(n), age(a) {}

    // Méthode pour obtenir le nom
    std::string getName() const {
        return name;
    }

    // Méthode pour définir le nom
    void setName(const std::string& n) {
        name = n;
    }

    // Méthode pour obtenir l'âge
    int getAge() const {
        return age;
    }

    // Méthode pour définir l'âge
    void setAge(int a) {
        if (a >= 0) {  // Validation de l'âge
            age = a;
        }
    }
};

int main() {
    Person person("Alice", 30);
    std::cout << "Name: " << person.getName() << ", Age: " << person.getAge() << std::endl;

    // Modification des données via les méthodes publiques
    person.setName("Bob");
    person.setAge(25);
    std::cout << "Updated Name: " << person.getName() << ", Updated Age: " << person.getAge() << std::endl;

    // Les lignes suivantes seraient incorrectes car `name` et `age` sont privés
    // std::cout << person.name;  // Erreur : `name` est privé
    // person.age = 35;           // Erreur : `age` est privé

    return 0;
}
```

## Méthodes `get` et `set`

Pour permettre l'accès aux données privées, vous pouvez fournir des méthodes publiques appelées "getters" et "setters". Les getters permettent de lire les valeurs des attributs privés, tandis que les setters permettent de les modifier. Les setters peuvent également inclure des validations pour s'assurer que les données restent valides.
