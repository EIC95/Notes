# Tableaux en C

### Tableaux unidimensionnels

Pour créer un tableau, définissez le type de données et spécifiez le nom du tableau suivi de crochets `[]`. Pour accéder à un élément de tableau, utilisez son index (les index commencent à 0).

#### Déclaration et initialisation :
```c
#include <stdio.h>

int main() {
    int tableau[5] = {1, 2, 3, 4, 5}; // Déclaration et initialisation
    printf("Premier élément : %d\n", tableau[0]); // Accès à l'élément avec index 0
    return 0;
}
```

### Taille d'un tableau

Pour obtenir la taille d'un tableau, utilisez l'opérateur `sizeof`, divisé par la taille d’un élément du tableau.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int tableau[5] = {1, 2, 3, 4, 5};
    size_t taille = sizeof(tableau) / sizeof(tableau[0]); // Taille du tableau
    printf("Nombre d'éléments dans le tableau : %zu\n", taille);
    return 0;
}
```

### Tableaux multidimensionnels

Pour créer un tableau multidimensionnel, déclarez un tableau avec plusieurs dimensions, comme si vous créiez un tableau de tableaux.

#### Déclaration et initialisation :
```c
#include <stdio.h>

int main() {
    int tableau[2][3] = {
        {1, 2, 3},
        {4, 5, 6}
    }; // Tableau 2x3

    // Accès à un élément
    printf("Élément à [1][2] : %d\n", tableau[1][2]); // Retourne 6

    return 0;
}
```