# Énumérations en C

Les énumérations (`enum`) sont utilisées pour définir un ensemble de valeurs entières symboliques. Elles permettent de donner des noms significatifs aux valeurs numériques, ce qui améliore la lisibilité du code.

### Déclaration des Énumérations

Pour créer une énumération, utilisez le mot-clé `enum`, suivi du nom de l'énumération et de la liste des éléments séparés par des virgules.

#### Syntaxe :
```c
enum NomEnum {
    ELEMENT1,
    ELEMENT2,
    ELEMENT3
};
```

Par défaut, le premier élément a la valeur 0, le deuxième a la valeur 1, et ainsi de suite. Vous pouvez également attribuer des valeurs spécifiques aux éléments si nécessaire.

#### Exemple :
```c
#include <stdio.h>

// Déclaration d'une énumération
enum JourSemaine {
    LUNDI,
    MARDI,
    MERCREDI,
    JEUDI,
    VENDREDI,
    SAMEDI,
    DIMANCHE
};

int main() {
    // Création d'une variable de type enum
    enum JourSemaine aujourdHui;

    // Attribution d'une valeur à la variable
    aujourdHui = MERCREDI;

    // Affichage de la valeur associée à l'énumération
    printf("Numéro du jour : %d\n", aujourdHui); // Affiche 2

    return 0;
}
```

### Modification des Valeurs des Éléments

Vous pouvez attribuer des valeurs spécifiques aux éléments d'une énumération. Les valeurs suivantes seront ajustées en conséquence.

#### Exemple :
```c
#include <stdio.h>

// Déclaration d'une énumération avec valeurs spécifiques
enum Couleur {
    ROUGE = 1,
    VERT = 4,
    BLEU = 7
};

int main() {
    // Création d'une variable de type enum
    enum Couleur couleurChoisie;

    // Attribution d'une valeur à la variable
    couleurChoisie = VERT;

    // Affichage de la valeur associée à l'énumération
    printf("Valeur de la couleur choisie : %d\n", couleurChoisie); // Affiche 4

    return 0;
}
```

### Accès aux Éléments de l'Énumération

Pour utiliser les éléments d'une énumération, créez une variable de type `enum` et assignez-lui l'un des éléments définis. Vous pouvez également utiliser les éléments de l'énumération directement dans des expressions.

#### Exemple :
```c
#include <stdio.h>

enum Direction {
    HAUT,
    BAS,
    GAUCHE,
    DROITE
};

int main() {
    enum Direction directionActuelle = GAUCHE;

    if (directionActuelle == GAUCHE) {
        printf("La direction actuelle est GAUCHE.\n");
    }

    return 0;
}
```