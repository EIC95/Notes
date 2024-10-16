# Création et Utilisation de Fonctions en C

### Déclaration et Définition des Fonctions

Pour créer une fonction en C, définissez-la en précisant son type de retour, son nom et ses paramètres, puis fournissez le code de la fonction entre accolades.

#### Exemple :
```c
#include <stdio.h>

// Déclaration de la fonction
int additionner(int a, int b);

int main() {
    int resultat = additionner(5, 3);
    printf("Résultat : %d\n", resultat);
    return 0;
}

// Définition de la fonction
int additionner(int a, int b) {
    return a + b;
}
```

### Programmation Modulaire

La programmation modulaire consiste à diviser un programme en sous-programmes ou modules pour accomplir des tâches spécifiques. Chaque module est conçu pour être réutilisable.

#### Fichiers d'en-tête (.h) et fichiers sources (.c)

- **Fichier d’en-tête (add.h)** : Contient les prototypes des fonctions.

```c
#ifndef ADD_H
#define ADD_H

// Prototype de la fonction
int additionner(int a, int b);

#endif // ADD_H
```

- **Fichier source (add.c)** : Contient la définition des fonctions.

```c
#include "add.h"

// Définition de la fonction
int additionner(int a, int b) {
    return a + b;
}
```

- **Fichier source principal (main.c)** : Contient le code principal du programme et inclut le fichier d’en-tête.

```c
#include <stdio.h>
#include "add.h"

int main() {
    int resultat = additionner(5, 3);
    printf("Résultat : %d\n", resultat);
    return 0;
}
```

### Compilation

Pour compiler plusieurs fichiers sources en un seul exécutable, utilisez la commande `gcc` :

```sh
gcc -o main.exe main.c add.c
```

### Directives de Préprocesseur

Les lignes `#ifndef`, `#define`, et `#endif` dans les fichiers d’en-tête sont utilisées pour éviter l'inclusion multiple de ce fichier. Cela empêche les erreurs de compilation dues à des inclusions répétées.

#### Exemple :
```c
#ifndef ADD_H
#define ADD_H

int additionner(int a, int b);

#endif // ADD_H
```