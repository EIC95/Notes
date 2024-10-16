# Variables en C

Pour créer une variable, spécifiez le type et attribuez-lui une valeur.

**ATTENTION** : Il y a des règles à respecter pour nommer une variable :
- Seules les lettres minuscules, majuscules et les chiffres sont autorisés.
- Le nom d'une variable doit commencer par une lettre.
- Les espaces sont interdits, mais vous pouvez utiliser le caractère "underscore" (`_`) pour séparer des mots.
- Les accents (`é`, `à`, `ê`, etc.) et les symboles (+, -, *, /, %, =) sont interdits.

### Types de données principaux en C :

- **int** (2 ou 4 octets) : Stocke des nombres entiers, sans décimales.
- **float** (4 octets) : Stocke des nombres fractionnaires avec une précision de 6 à 7 chiffres décimaux.
- **double** (8 octets) : Stocke des nombres fractionnaires avec une précision de 15 chiffres décimaux.
- **char** (1 octet) : Stocke un seul caractère/lettre/chiffre ou des valeurs ASCII.

#### Exemple de déclaration de variables :
```c
int age = 25;          // Variable de type entier
float temperature = 36.5;  // Variable de type flottant
double pi = 3.1415926535;  // Variable de type double
char grade = 'A';       // Variable de type caractère
```