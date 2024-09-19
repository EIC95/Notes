# Pointeurs en C

### Déclaration des Pointeurs

Un pointeur est une variable qui stocke l'adresse mémoire d'une autre variable. Pour déclarer un pointeur, utilisez le symbole `*`.

#### Exemple de déclaration :
```c
int *pointeur; // Déclare un pointeur vers un entier
```

### Initialisation des Pointeurs

Les pointeurs doivent être du même type que la variable qu'ils pointent. Vous pouvez initialiser un pointeur en lui assignant l'adresse d'une variable avec l'opérateur `&`. Un pointeur peut aussi être nul, ce qui signifie qu'il ne pointe vers aucune adresse valide. Utilisez la constante `NULL` pour initialiser un pointeur nul.

#### Exemple d'initialisation :
```c
#include <stdio.h>

int main() {
    int variable = 5;
    int *pointeur = &variable; // Pointeur vers variable
    int *pointeurNul = NULL;   // Pointeur nul

    printf("Adresse de variable : %p\n", (void*)pointeur);
    printf("Valeur pointée : %d\n", *pointeur); // Accède à la valeur de variable via le pointeur

    return 0;
}
```

### Accès et Modification via les Pointeurs

Utilisez l'opérateur `*` pour accéder ou modifier la valeur pointée par le pointeur.

#### Exemple de modification :
```c
#include <stdio.h>

int main() {
    int variable = 10;
    int *pointeur = &variable;

    printf("Avant modification : %d\n", *pointeur);

    *pointeur = 20; // Modifie la valeur de variable via le pointeur

    printf("Après modification : %d\n", *pointeur);
    printf("Valeur de variable : %d\n", variable);

    return 0;
}
```

### Utilisation des Pointeurs

Les pointeurs sont couramment utilisés pour :
- **Modifier les arguments d'une fonction** : Passer des variables par référence pour les modifier directement dans la fonction.
- **Gérer des tableaux dynamiques** : Allouer et manipuler des tableaux en utilisant la mémoire dynamique.

#### Exemple de modification via une fonction :
```c
#include <stdio.h>

void modifierValeur(int *p) {
    *p = 100; // Modifie la valeur pointée
}

int main() {
    int variable = 10;
    modifierValeur(&variable); // Passe l'adresse de variable

    printf("Valeur après modification : %d\n", variable);
    return 0;
}
```