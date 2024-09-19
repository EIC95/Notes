# Gestion des Exceptions en C++

La gestion des exceptions en C++ permet de traiter les erreurs de manière élégante en utilisant trois mots-clés principaux : `try`, `throw`, et `catch`.

## Mots-clés Principaux

### `try`

Le mot-clé `try` introduit un bloc de code dans lequel des exceptions peuvent se produire. C'est ici que vous placez le code susceptible de générer des erreurs. Si une erreur survient, l'exécution du bloc `try` est interrompue et le contrôle est transféré au bloc `catch` correspondant.

#### Exemple

```cpp
#include <iostream>
using namespace std;

int main() {
    try {
        int divisor = 0;
        int result = 10 / divisor; // Division par zéro
    } catch (const exception& e) {
        cout << "Exception attrapée : " << e.what() << endl; // Gestion de l'exception
    }

    return 0;
}
```

### `throw`

Le mot-clé `throw` est utilisé pour lancer une exception lorsqu'une condition d'erreur est rencontrée dans le bloc `try`. Cela signale qu'une erreur a eu lieu et peut être utilisé pour lancer des exceptions personnalisées.

#### Exemple

```cpp
#include <iostream>
#include <stdexcept> // Pour std::runtime_error
using namespace std;

void checkValue(int value) {
    if (value < 0) {
        throw runtime_error("La valeur ne peut pas être négative");
    }
}

int main() {
    try {
        checkValue(-1); // Lancement d'une exception
    } catch (const runtime_error& e) {
        cout << "Exception attrapée : " << e.what() << endl; // Gestion de l'exception
    }

    return 0;
}
```

### `catch`

Le mot-clé `catch` est utilisé pour attraper (ou capturer) une exception lancée par `throw`. Vous pouvez définir plusieurs blocs `catch` pour gérer différents types d'exceptions ou scénarios d'erreur.

#### Exemple

```cpp
#include <iostream>
#include <stdexcept> // Pour std::runtime_error et std::out_of_range
using namespace std;

int main() {
    try {
        int arr[3] = {1, 2, 3};
        cout << arr[5]; // Accès à un index hors limites
    } catch (const out_of_range& e) {
        cout << "Exception attrapée : " << e.what() << endl; // Gestion d'out_of_range
    } catch (const exception& e) {
        cout << "Exception attrapée : " << e.what() << endl; // Gestion des autres exceptions
    }

    return 0;
}
```

### Gestion d'Exceptions Non Spécifiées

Si vous ne connaissez pas le type d'exception qui pourrait être lancée, vous pouvez utiliser la syntaxe `...` à l'intérieur du bloc `catch`, qui gérera tout type d'exception.

#### Exemple

```cpp
#include <iostream>
using namespace std;

int main() {
    try {
        throw "Erreur générique"; // Lancement d'une chaîne de caractères comme exception
    } catch (...) {
        cout << "Exception inconnue attrapée" << endl; // Gestion des exceptions non spécifiées
    }

    return 0;
}
```

## Points Clés

- **`try`** : Déclare le bloc de code dans lequel les exceptions peuvent se produire.
- **`throw`** : Lance une exception lorsque quelque chose ne va pas.
- **`catch`** : Attrape et traite les exceptions lancées dans le bloc `try`.

