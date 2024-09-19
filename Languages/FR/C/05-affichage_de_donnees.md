# Affichage de données en C

Pour afficher des valeurs ou imprimer du texte en C, vous pouvez utiliser la fonction `printf()`. Pour insérer une nouvelle ligne, utilisez le caractère `\n`. Pour afficher des variables, utilisez des spécificateurs de format selon le type de données.

### Caractères d'échappement courants :
- `\t` : Crée un onglet horizontal
- `\\` : Insère un caractère barre oblique inverse (`\`)
- `\"` : Insère un guillemet double (`"`)
- `\n` : Insère un saut de ligne (retour à la ligne)
- `\r` : Insère un retour chariot (début de ligne)
- `\b` : Insère une suppression (backspace)

### Exemple d'utilisation de `printf()` :
```c
#include <stdio.h>

int main() {
    int age = 25;
    printf("Mon âge est : %d\n", age); // %d pour afficher un entier
    printf("Un exemple de tabulation :\tVoici du texte après un onglet.\n");
    printf("Un guillemet double : \"\n");
    printf("Retour chariot :\rDébut de ligne\n");
    printf("Backspace : ABC\bD\n"); // Affiche "ABD"
    return 0;
}
```