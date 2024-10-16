# Variables en C++

## Déclaration des Variables

Pour créer une variable en C++, vous devez spécifier le type de données et lui attribuer une valeur initiale. Les variables sont définies comme suit :

```cpp
#include <iostream> // Inclusion de la bibliothèque d'entrée/sortie

int main() {
    int age = 30; // Déclaration d'une variable entière et attribution d'une valeur
    float hauteur = 1.75; // Déclaration d'une variable flottante et attribution d'une valeur
    char initiale = 'A'; // Déclaration d'une variable caractère et attribution d'une valeur

    std::cout << "Âge : " << age << std::endl;
    std::cout << "Hauteur : " << hauteur << std::endl;
    std::cout << "Initiale : " << initiale << std::endl;

    return 0;
}
```

### Constantes

Pour définir une constante en C++, utilisez le mot-clé `const`. Une constante est une variable dont la valeur ne peut pas être modifiée après son initialisation.

```cpp
const int MAX_TAILLE = 100; // Déclaration d'une constante entière
```

### Règles pour les Noms de Variables

- **Minuscules et Majuscules** : Les noms de variables peuvent contenir des lettres minuscules et majuscules.
- **Chiffres** : Les chiffres peuvent être utilisés mais pas au début du nom.
- **Underscore (`_`)** : Utilisé pour séparer des mots dans le nom de la variable (par exemple, `nombre_max`).
- **Caractères Interdits** : Les accents (é, à, ê, etc.) et les symboles (comme +, -, *, /, %, =) ne sont pas autorisés.
