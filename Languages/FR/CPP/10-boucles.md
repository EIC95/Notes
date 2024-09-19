# Structures de Boucles en C++

Les boucles en C++ permettent d'exécuter un bloc de code de manière répétée tant qu'une condition est remplie. Voici un résumé des principales structures de boucles :

## Boucle `while`

Exécute un bloc de code tant qu'une condition est vraie.
```cpp
#include <iostream>

int main() {
    int i = 0;
    while (i < 5) {
        std::cout << i << " ";
        ++i;
    }
    return 0;
}
```

## Boucle `do...while`

Exécute un bloc de code au moins une fois, puis répète l'exécution tant qu'une condition est vraie.
```cpp
#include <iostream>

int main() {
    int i = 0;
    do {
        std::cout << i << " ";
        ++i;
    } while (i < 5);
    return 0;
}
```

## Boucle `for`

Utilisée pour itérer un nombre fixe de fois. Elle est souvent utilisée avec un compteur.
```cpp
#include <iostream>

int main() {
    for (int i = 0; i < 5; ++i) {
        std::cout << i << " ";
    }
    return 0;
}
```

## Boucle `for-each` (C++11 et ultérieur)

Parcourt les éléments d'un tableau ou d'autres conteneurs comme `std::vector`.
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> vec = {1, 2, 3, 4, 5};
    for (int x : vec) {
        std::cout << x << " ";
    }
    return 0;
}
```

## Instructions de Contrôle

- **`break`**  
  Sort de la boucle en cours, même si la condition n'est pas remplie.
  ```cpp
  for (int i = 0; i < 10; ++i) {
      if (i == 5) {
          break;
      }
      std::cout << i << " ";
  }
  ```

- **`continue`**  
  Passe à l'itération suivante de la boucle, en sautant le reste du code pour l'itération actuelle.
  ```cpp
  for (int i = 0; i < 10; ++i) {
      if (i % 2 == 0) {
          continue;
      }
      std::cout << i << " ";
  }
  ```
```