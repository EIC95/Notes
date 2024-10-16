# Entrée des Utilisateurs en C++

## Utilisation de `cin` pour la Saisie

En C++, l'objet `std::cin`, associé aux chevrons `>>`, permet de lire des informations entrées par l'utilisateur.

### Exemple

```cpp
#include <iostream>

int main() {
    int age;
    std::cout << "Entrez votre âge : ";
    std::cin >> age;
    std::cout << "Vous avez " << age << " ans." << std::endl;

    return 0;
}
```

## Utilisation de `getline()` pour Lire des Chaînes

Pour lire une ligne entière de texte, y compris les espaces, utilisez la fonction `getline()` de la bibliothèque `<string>`.

### Exemple

```cpp
#include <iostream>
#include <string>

int main() {
    std::string nom;
    std::cout << "Entrez votre nom : ";
    std::getline(std::cin, nom); // Lecture d'une ligne entière
    std::cout << "Bonjour, " << nom << " !" << std::endl;

    return 0;
}
```

## Problèmes Potentiels avec `cin` et `getline()`

Après avoir utilisé `std::cin`, le tampon peut contenir un retour à la ligne restant. Pour éviter que `getline()` ne lise ce retour à la ligne, utilisez `std::cin.ignore()` pour l'ignorer.

### Exemple avec `std::cin.ignore()`

```cpp
#include <iostream>
#include <string>

int main() {
    int age;
    std::string nom;

    std::cout << "Entrez votre âge : ";
    std::cin >> age;
    std::cin.ignore(); // Ignorer le retour à la ligne restant dans le tampon

    std::cout << "Entrez votre nom : ";
    std::getline(std::cin, nom); // Lecture d'une ligne entière
    std::cout << "Vous avez " << age << " ans et vous êtes " << nom << "." << std::endl;

    return 0;
}
```

## Fonction `cin.ignore()`

`std::cin.ignore()` est utilisé pour ignorer les caractères restants dans le tampon d'entrée après une opération de lecture. Cela prépare le flux d'entrée pour la prochaine opération de lecture en évitant les conflits avec les caractères non lus.
```