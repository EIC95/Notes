# Saisie de l'utilisateur en C

### Fonction `scanf()`

Pour obtenir la saisie de l'utilisateur, vous pouvez utiliser la fonction `scanf()`. Cette fonction prend deux arguments : le spécificateur de format de la variable (par exemple, `%d` pour un entier) et l'opérateur de référence (`&variable`), qui stocke l'adresse mémoire de la variable.

#### Exemple :
```c
#include <stdio.h>

int main() {
    int age;
    printf("Entrez votre âge : ");
    scanf("%d", &age);  // %d pour un entier, &age pour stocker la valeur
    printf("Votre âge est : %d\n", age);
    return 0;
}
```

### Fonction `fgets()`

La fonction `fgets()` lit une ligne de texte à partir d'un flux de fichier (souvent `stdin` pour la saisie utilisateur) et la stocke dans un tampon. Elle lit jusqu'à `n-1` caractères, ou jusqu'à ce qu'une nouvelle ligne soit rencontrée, en ajoutant un caractère nul (`\0`) à la fin de la chaîne pour terminer.

#### Exemple :
```c
#include <stdio.h>

int main() {
    char nom[50];
    printf("Entrez votre nom : ");
    fgets(nom, sizeof(nom), stdin);  // Lit jusqu'à 49 caractères
    printf("Votre nom est : %s", nom);
    return 0;
}
```

La fonction `fgets()` retourne un pointeur vers le tampon en cas de succès, ou `NULL` en cas d'erreur ou si la fin du fichier est atteinte avant la lecture.