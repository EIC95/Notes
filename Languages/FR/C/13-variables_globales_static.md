# Variables et Fonctions Globales en C

### Variables Globales

Les variables globales sont déclarées en dehors de toutes les fonctions et sont accessibles depuis tout le code dans le fichier source où elles sont définies.

#### Exemple :
```c
#include <stdio.h>

int variableGlobale = 10; // Variable globale

int main() {
    printf("Variable globale : %d\n", variableGlobale);
    return 0;
}
```

### Variables et Fonctions `static`

Pour créer une variable ou une fonction qui est accessible uniquement dans le fichier où elle est définie, utilisez le mot-clé `static`. Cela limite la portée de la variable ou de la fonction au fichier source, empêchant son utilisation dans d'autres fichiers.

#### Exemple de variable `static` :
```c
#include <stdio.h>

static int variableLocale = 20; // Variable globale, mais uniquement accessible dans ce fichier

int main() {
    printf("Variable locale : %d\n", variableLocale);
    return 0;
}
```

#### Exemple de fonction `static` :
```c
#include <stdio.h>

static void fonctionLocale() { // Fonction uniquement accessible dans ce fichier
    printf("Fonction locale appelée\n");
}

int main() {
    fonctionLocale(); // Appel de la fonction locale
    return 0;
}
```

L'utilisation du mot-clé `static` permet d'encapsuler les variables et les fonctions pour éviter les conflits de nom et les effets secondaires indésirables dans des programmes plus complexes.