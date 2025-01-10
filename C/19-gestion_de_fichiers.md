# Gestion des Fichiers en C

La gestion des fichiers en C vous permet d'ouvrir, lire, écrire et fermer des fichiers. Voici un résumé des opérations principales et des modes d'ouverture des fichiers.

### Opérations Principales

- **`fopen(nom_fichier, mode)`** : Ouvre un fichier dans le mode spécifié. Retourne un pointeur vers le fichier ou `NULL` en cas d'erreur.

  ```c
  FILE *fichier = fopen("exemple.txt", "r");
  ```

- **`fread(buffer, taille, nombre, fichier)`** : Lit des données depuis un fichier binaire. `buffer` est le tampon où les données seront stockées, `taille` est la taille d'un élément, et `nombre` est le nombre d'éléments à lire.

  ```c
  size_t result = fread(buffer, sizeof(char), taille, fichier);
  ```

- **`fgets(buffer, taille, fichier)`** : Lit une ligne de texte depuis un fichier. `buffer` est le tampon où la ligne sera stockée, et `taille` est la taille du tampon.

  ```c
  fgets(buffer, taille, fichier);
  ```

- **`fwrite(buffer, taille, nombre, fichier)`** : Écrit des données dans un fichier binaire. `buffer` est le tampon contenant les données, `taille` est la taille d'un élément, et `nombre` est le nombre d'éléments à écrire.

  ```c
  fwrite(buffer, sizeof(char), nombre, fichier);
  ```

- **`fprintf(fichier, format, ...)`** : Écrit du texte formaté dans un fichier.

  ```c
  fprintf(fichier, "Nombre : %d\n", nombre);
  ```

- **`fclose(fichier)`** : Ferme un fichier ouvert, libérant ainsi les ressources associées.

  ```c
  fclose(fichier);
  ```

- **`fseek(fichier, offset, origine)`** : Déplace le curseur de lecture/écriture à une position spécifique. `offset` est le nombre d'octets à déplacer, et `origine` peut être `SEEK_SET`, `SEEK_CUR`, ou `SEEK_END`.

  ```c
  fseek(fichier, 0, SEEK_SET);  // Déplace le curseur au début du fichier
  ```

- **`ftell(fichier)`** : Retourne la position actuelle du curseur dans le fichier.

  ```c
  long position = ftell(fichier);
  ```

- **`feof(fichier)`** : Vérifie si la fin du fichier a été atteinte.

  ```c
  if (feof(fichier)) {
      // Fin de fichier atteinte
  }
  ```

- **`ferror(fichier)`** : Détecte les erreurs de lecture/écriture.

  ```c
  if (ferror(fichier)) {
      // Une erreur est survenue
  }
  ```

- **`clearerr(fichier)`** : Réinitialise les indicateurs d'erreur pour le fichier.

  ```c
  clearerr(fichier);
  ```

### Modes d'Ouverture des Fichiers

- **`"r"`** : Lecture seule. Ouvre le fichier pour lecture. Le fichier doit exister.

  ```c
  FILE *fichier = fopen("exemple.txt", "r");
  ```

- **`"w"`** : Écriture seule. Crée un nouveau fichier ou écrase un fichier existant.

  ```c
  FILE *fichier = fopen("exemple.txt", "w");
  ```

- **`"a"`** : Ajout seule. Ouvre le fichier pour écriture à la fin du fichier. Crée le fichier s'il n'existe pas.

  ```c
  FILE *fichier = fopen("exemple.txt", "a");
  ```

- **`"r+"`** : Lecture et écriture. Ouvre le fichier pour lecture et écriture. Le fichier doit exister.

  ```c
  FILE *fichier = fopen("exemple.txt", "r+");
  ```

- **`"w+"`** : Lecture et écriture. Crée un nouveau fichier ou écrase un fichier existant, et permet la lecture et l'écriture.

  ```c
  FILE *fichier = fopen("exemple.txt", "w+");
  ```

- **`"a+"`** : Lecture et écriture. Ouvre le fichier pour lecture et écriture à la fin du fichier. Crée le fichier s'il n'existe pas.

  ```c
  FILE *fichier = fopen("exemple.txt", "a+");
  ```
