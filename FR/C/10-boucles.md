# Boucles en C

### `while`
La boucle `while` continue à exécuter un bloc de code tant que la condition spécifiée est vraie.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int compteur = 0;
    while (compteur < 5) {
        printf("Compteur : %d\n", compteur);
        compteur++;
    }
    return 0;
}
```

### `do...while`
La boucle `do...while` exécute un bloc de code au moins une fois, puis continue tant que la condition spécifiée est vraie.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int compteur = 0;
    do {
        printf("Compteur : %d\n", compteur);
        compteur++;
    } while (compteur < 5);
    return 0;
}
```

### `for`
La boucle `for` est souvent utilisée pour itérer un nombre fixe de fois, en spécifiant une initialisation, une condition et une mise à jour dans une seule ligne.

#### Exemple :
```c
#include <stdio.h>

int main() {
    for (int i = 0; i < 5; i++) {
        printf("i : %d\n", i);
    }
    return 0;
}
```