# Programmation Modulaire en C++

La programmation modulaire est une technique qui consiste à diviser un programme en sous-programmes ou modules pour accomplir des tâches spécifiques. Cette approche permet de rendre le code plus organisé, réutilisable et plus facile à maintenir.

## Fichiers d'En-tête et Sources

### Fichiers d’En-tête (.hpp)

Les fichiers d’en-tête contiennent les déclarations des fonctions, des classes et des variables globales. Ils sont inclus dans les fichiers sources pour que le compilateur connaisse les signatures des fonctions et des classes avant la compilation.

#### Exemple de Fichier d’En-tête (add.hpp)

```cpp
// add.hpp
#ifndef ADD_HPP
#define ADD_HPP

int add(int a, int b);

#endif // ADD_HPP
```

### Fichiers Sources (.cpp)

Les fichiers sources contiennent les définitions des fonctions et des méthodes déclarées dans les fichiers d’en-tête. Ils sont compilés pour générer les fichiers objets qui seront ensuite liés pour former l'exécutable.

#### Exemple de Fichier Source (add.cpp)

```cpp
// add.cpp
#include "add.hpp"

int add(int a, int b) {
    return a + b;
}
```

## Utilisation des Fonctions dans un Programme

Pour utiliser une fonction définie dans un fichier source, vous devez inclure le fichier d’en-tête correspondant dans le fichier source principal de votre programme.

#### Exemple de Programme Principal (demo.cpp)

```cpp
// demo.cpp
#include <iostream>
#include "add.hpp"

int main() {
    int result = add(5, 3);
    std::cout << "Résultat de l'addition : " << result << std::endl;
    return 0;
}
```

## Compilation

Pour compiler un programme modulaire, vous devez inclure tous les fichiers sources nécessaires. Vous pouvez utiliser la commande `g++` pour compiler et lier les fichiers sources en un exécutable.

### Commande de Compilation

```bash
g++ -o demo.exe demo.cpp add.cpp
```

Cette commande compile `demo.cpp` et `add.cpp` et lie les fichiers objets résultants pour créer un exécutable nommé `demo.exe`.

## Protection contre les Inclusions Multiples

Pour éviter les inclusions multiples d’un fichier d’en-tête, vous utilisez des directives de préprocesseur telles que `#ifndef`, `#define`, et `#endif`. Cela garantit que le fichier d’en-tête est inclus une seule fois lors de la compilation.

#### Exemple de Protection contre les Inclusions Multiples

```cpp
// add.hpp
#ifndef ADD_HPP
#define ADD_HPP

int add(int a, int b);

#endif // ADD_HPP
```
