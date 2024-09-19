# Chaînes de Caractères en C

### Représentation des Chaînes de Caractères

Une chaîne de caractères en C est une séquence de caractères stockée dans une région de mémoire contiguë, représentée sous forme de tableau de `char`. Elle est terminée par un caractère spécial appelé "caractère de fin de chaîne" (`\0`), qui indique la fin de la chaîne. 

#### Exemple :
```c
#include <stdio.h>

int main() {
    char chaine[] = "Bonjour"; // Chaîne de caractères
    printf("Chaîne : %s\n", chaine);
    return 0;
}
```

### Taille des Tableaux pour les Chaînes

Pour stocker une chaîne de `n` caractères, le tableau doit avoir une taille de `n + 1` pour inclure le caractère de fin de chaîne.

#### Exemple :
```c
#include <stdio.h>

int main() {
    char chaine[8] = "Bonjour"; // Taille 8 pour 7 caractères + '\0'
    printf("Chaîne : %s\n", chaine);
    return 0;
}
```

### Fonctions de la Bibliothèque `string.h`

La bibliothèque `<string.h>` fournit de nombreuses fonctions pour manipuler les chaînes de caractères.

#### Fonctions courantes :

- **`strlen(s)`** : Retourne la longueur de la chaîne `s` (sans le caractère nul).

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char chaine[] = "Bonjour";
      size_t longueur = strlen(chaine);
      printf("Longueur de la chaîne : %zu\n", longueur);
      return 0;
  }
  ```

- **`strcpy(dest, src)`** : Copie la chaîne `src` dans `dest`.

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char source[] = "Bonjour";
      char destination[20];
      strcpy(destination, source);
      printf("Chaîne copiée : %s\n", destination);
      return 0;
  }
  ```

- **`strcat(dest, src)`** : Concatène la chaîne `src` à la fin de `dest`.

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char destination[20] = "Bonjour";
      char source[] = " tout le monde";
      strcat(destination, source);
      printf("Chaîne concaténée : %s\n", destination);
      return 0;
  }
  ```

- **`strcmp(s1, s2)`** : Compare les chaînes `s1` et `s2`. Retourne 0 si elles sont égales, un nombre négatif si `s1` est avant `s2`, ou un nombre positif si `s1` est après `s2`.

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char chaine1[] = "Bonjour";
      char chaine2[] = "Bonsoir";
      int resultat = strcmp(chaine1, chaine2);
      printf("Résultat de la comparaison : %d\n", resultat);
      return 0;
  }
  ```

- **`strchr(s, c)`** : Retourne un pointeur vers la première occurrence du caractère `c` dans `s`.

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char chaine[] = "Bonjour";
      char *pointeur = strchr(chaine, 'j');
      if (pointeur != NULL) {
          printf("Caractère trouvé à : %s\n", pointeur);
      }
      return 0;
  }
  ```

- **`strstr(haystack, needle)`** : Retourne un pointeur vers la première occurrence de la sous-chaîne `needle` dans `haystack`.

  ```c
  #include <stdio.h>
  #include <string.h>

  int main() {
      char chaine[] = "Bonjour tout le monde";
      char *pointeur = strstr(chaine, "tout");
      if (pointeur != NULL) {
          printf("Sous-chaîne trouvée à : %s\n", pointeur);
      }
      return 0;
  }
  ```