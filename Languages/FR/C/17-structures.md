# Structures en C

Les structures (ou `structs`) sont des collections de variables regroupées sous un même nom. Chaque variable dans une structure est appelée un membre. Contrairement aux tableaux, les structures peuvent contenir différents types de données.

### Déclaration des Structures

Pour déclarer une structure, utilisez le mot-clé `struct` suivi du nom de la structure et des membres entre accolades. 

#### Exemple :
```c
#include <stdio.h>

// Déclaration d'une structure
struct Personne {
    char nom[50];
    int age;
    float taille;
};

int main() {
    // Création d'une instance de la structure
    struct Personne personne1;

    // Initialisation des membres de la structure
    personne1.age = 25;
    personne1.taille = 1.75;
    strcpy(personne1.nom, "Alice");

    // Accès aux membres de la structure
    printf("Nom : %s\n", personne1.nom);
    printf("Âge : %d\n", personne1.age);
    printf("Taille : %.2f\n", personne1.taille);

    return 0;
}
```

### Accès aux Membres de la Structure

Pour accéder aux membres d'une structure, utilisez la syntaxe à points (`.`).

#### Exemple :
```c
#include <stdio.h>

struct Point {
    int x;
    int y;
};

int main() {
    struct Point p1;
    
    // Affectation des valeurs aux membres de la structure
    p1.x = 10;
    p1.y = 20;

    // Accès et affichage des membres de la structure
    printf("Coordonnées : (%d, %d)\n", p1.x, p1.y);

    return 0;
}
```

### Structures et Pointeurs

Vous pouvez également utiliser des pointeurs vers des structures. Dans ce cas, vous utilisez l'opérateur `->` pour accéder aux membres.

#### Exemple :
```c
#include <stdio.h>

struct Rectangle {
    int largeur;
    int hauteur;
};

int main() {
    struct Rectangle rect;
    struct Rectangle *ptr = &rect; // Pointeur vers la structure

    // Utilisation du pointeur pour accéder aux membres
    ptr->largeur = 10;
    ptr->hauteur = 20;

    printf("Largeur : %d\n", ptr->largeur);
    printf("Hauteur : %d\n", ptr->hauteur);

    return 0;
}
```
