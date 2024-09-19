# Allocation Dynamique en C

L'allocation dynamique permet de gérer la mémoire de manière flexible pendant l'exécution du programme. En C, cette gestion est effectuée à l'aide des fonctions de la bibliothèque standard `stdlib.h`.

### Fonctions Principales

- **`malloc(size_t size)`** : Alloue un bloc de mémoire de `size` octets et retourne un pointeur vers le début de ce bloc. La mémoire allouée n'est pas initialisée, ce qui signifie que les valeurs dans cette mémoire sont indéfinies.

  ```c
  #include <stdlib.h>

  int *ptr = (int *)malloc(10 * sizeof(int)); // Alloue mémoire pour 10 entiers
  ```

- **`calloc(size_t num, size_t size)`** : Alloue de la mémoire pour un tableau de `num` éléments, chacun de `size` octets. La mémoire allouée est initialisée à zéro.

  ```c
  #include <stdlib.h>

  int *ptr = (int *)calloc(10, sizeof(int)); // Alloue et initialise à zéro
  ```

- **`realloc(void *ptr, size_t size)`** : Réalloue un bloc de mémoire précédemment alloué à `ptr` pour avoir une nouvelle taille de `size` octets. La fonction peut déplacer le bloc de mémoire à un nouvel emplacement si nécessaire. Le pointeur `ptr` peut être modifié.

  ```c
  #include <stdlib.h>

  ptr = (int *)realloc(ptr, 20 * sizeof(int)); // Réalloue mémoire pour 20 entiers
  ```

- **`free(void *ptr)`** : Libère un bloc de mémoire précédemment alloué. Après avoir libéré la mémoire, `ptr` ne doit plus être utilisé pour éviter des accès invalides.

  ```c
  #include <stdlib.h>

  free(ptr); // Libère la mémoire allouée
  ```

### Exemples

#### Allocation et Utilisation de Mémoire

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *tableau;

    // Allocation de mémoire pour un tableau de 5 entiers
    tableau = (int *)malloc(5 * sizeof(int));
    if (tableau == NULL) {
        printf("Échec de l'allocation de mémoire.\n");
        return 1;
    }

    // Initialisation et utilisation du tableau
    for (int i = 0; i < 5; i++) {
        tableau[i] = i * 2;
        printf("%d ", tableau[i]);
    }
    printf("\n");

    // Réallocation pour augmenter la taille du tableau
    tableau = (int *)realloc(tableau, 10 * sizeof(int));
    if (tableau == NULL) {
        printf("Échec de la réallocation de mémoire.\n");
        return 1;
    }

    // Utilisation de la nouvelle mémoire allouée
    for (int i = 5; i < 10; i++) {
        tableau[i] = i * 2;
        printf("%d ", tableau[i]);
    }
    printf("\n");

    // Libération de la mémoire allouée
    free(tableau);

    return 0;
}
```

### Bonnes Pratiques

- **Vérifiez les erreurs** : Toujours vérifier si `malloc`, `calloc`, ou `realloc` renvoient `NULL`, ce qui indique un échec de l'allocation.
- **Libération de mémoire** : Assurez-vous de libérer toute mémoire allouée avec `free` lorsque vous n'en avez plus besoin pour éviter les fuites de mémoire.
- **Ne pas utiliser après libération** : Ne tentez pas d'accéder à la mémoire après l'avoir libérée.

L'allocation dynamique est essentielle pour gérer des structures de données dont la taille peut varier pendant l'exécution du programme.