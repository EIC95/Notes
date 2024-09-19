# Structures de Contrôle en C

### `if`
La structure `if` permet d'exécuter un bloc de code si une condition est vraie.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int age = 20;
    if (age >= 18) {
        printf("Vous êtes majeur.\n");
    }
    return 0;
}
```

### `if...else`
La structure `if...else` permet d'exécuter un bloc de code si une condition est vraie et un autre bloc si elle est fausse.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int age = 16;
    if (age >= 18) {
        printf("Vous êtes majeur.\n");
    } else {
        printf("Vous êtes mineur.\n");
    }
    return 0;
}
```

### `else if`
La structure `else if` permet de tester plusieurs conditions successivement après un `if` initial.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int note = 75;
    if (note >= 90) {
        printf("Excellente\n");
    } else if (note >= 70) {
        printf("Bien\n");
    } else if (note >= 50) {
        printf("Suffisant\n");
    } else {
        printf("Insuffisant\n");
    }
    return 0;
}
```

### `switch case`
La structure `switch` permet de choisir parmi plusieurs blocs de code à exécuter en fonction de la valeur d'une expression.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int jour = 3;
    switch (jour) {
        case 1:
            printf("Lundi\n");
            break;
        case 2:
            printf("Mardi\n");
            break;
        case 3:
            printf("Mercredi\n");
            break;
        default:
            printf("Jour invalide\n");
            break;
    }
    return 0;
}
```

### Opérateur ternaire
L'opérateur ternaire est une forme concise d'un `if...else` pour affecter une valeur en fonction d'une condition.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int age = 20;
    const char* statut = (age >= 18) ? "Majeur" : "Mineur";
    printf("Vous êtes %s.\n", statut);
    return 0;
}
```