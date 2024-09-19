# Affichage en C++

## Utilisation de `cout` pour l'Affichage

En C++, l'objet `std::cout` est utilisé pour afficher du texte ou des valeurs à l'écran. Vous pouvez utiliser l'opérateur de flux `<<` pour envoyer des données à `std::cout`.

### Exemple d'Utilisation

```cpp
#include <iostream> // Inclusion de la bibliothèque d'entrée/sortie

int main() {
    // Affichage de texte avec std::cout et l'opérateur <<
    std::cout << "Bonjour, le monde!" << std::endl; // Utilisation de endl pour ajouter une nouvelle ligne
    
    // Affichage d'une variable
    int nombre = 42;
    std::cout << "Le nombre est : " << nombre << std::endl;

    return 0;
}
```

### Explications

- `std::cout` : Objet utilisé pour l'affichage.
- `<<` : Opérateur de flux qui envoie les données à `std::cout`.
- `std::endl` : Manipulateur qui insère un saut de ligne et vide le tampon de sortie. Il est équivalent au caractère spécial `\n`, mais il assure également que le texte est effectivement affiché immédiatement.
- `\n` : Caractère spécial qui insère un saut de ligne.

### Comparaison entre `std::endl` et `\n`

- **`std::endl`** : Insère un saut de ligne et vide le tampon de sortie, ce qui peut être utile pour s'assurer que le texte est affiché immédiatement.
- **`\n`** : Insère simplement un saut de ligne sans vider le tampon de sortie.

Utilisez `std::endl` lorsque vous avez besoin de vider le tampon immédiatement, sinon `\n` est suffisant pour insérer un saut de ligne.
```