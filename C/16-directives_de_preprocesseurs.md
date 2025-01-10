# Directives de Préprocesseur en C

Les directives de préprocesseur en C sont des commandes qui sont traitées avant la compilation du code. Elles commencent par le symbole `#` et permettent de contrôler divers aspects du processus de compilation.

### Directives de Préprocesseur

- **`#include`** : Inclut le contenu d'un fichier dans le fichier source. Utilisé pour inclure des fichiers d'en-tête ou d'autres fichiers sources.

  ```c
  #include <stdio.h>  // Inclut la bibliothèque standard d'entrée/sortie
  ```

- **`#define`** : Définit une macro. Les macros sont des constantes ou des expressions qui sont remplacées par le préprocesseur avant la compilation.

  ```c
  #define PI 3.14159
  #define CARRE(x) ((x) * (x))
  ```

- **`#undef`** : Annule la définition d'une macro.

  ```c
  #undef PI
  ```

- **`#ifdef`** : Vérifie si une macro est définie.

  ```c
  #ifdef DEBUG
  // Code spécifique pour le mode débogage
  #endif
  ```

- **`#ifndef`** : Vérifie si une macro n'est pas définie.

  ```c
  #ifndef PI
  #define PI 3.14159
  #endif
  ```

- **`#else`** : Fournit une alternative dans une section conditionnelle.

  ```c
  #ifdef DEBUG
  // Code pour le mode débogage
  #else
  // Code pour le mode normal
  #endif
  ```

- **`#endif`** : Termine une section conditionnelle commencée par `#ifdef`, `#ifndef`, ou `#if`.

  ```c
  #ifdef DEBUG
  // Code spécifique pour le mode débogage
  #endif
  ```

- **`#if`** : Évalue une expression conditionnelle. Permet d'inclure du code conditionnel en fonction de la valeur d'une expression.

  ```c
  #if VERSION >= 2
  // Code pour les versions >= 2
  #endif
  ```

- **`#error`** : Génère un message d'erreur pendant le prétraitement. Utilisé pour indiquer des erreurs dans le code de prétraitement.

  ```c
  #if !defined(VERSION)
  #error "VERSION must be defined"
  #endif
  ```

- **`#pragma`** : Donne des instructions spécifiques au compilateur. Les instructions `#pragma` sont utilisées pour fournir des directives spécifiques à l'implémentation du compilateur.

  ```c
  #pragma once  // Assure que le fichier d'en-tête est inclus une seule fois
  ```

### Constantes Prédéfinies

Le préprocesseur offre des constantes prédéfinies qui fournissent des informations sur le code source :

- **`__LINE__`** : Numéro de la ligne actuelle dans le fichier source.

  ```c
  printf("Ligne actuelle : %d\n", __LINE__);
  ```

- **`__FILE__`** : Nom du fichier source actuel.

  ```c
  printf("Nom du fichier : %s\n", __FILE__);
  ```

- **`__DATE__`** : Date de la compilation au format "Mmm JJ AAAA".

  ```c
  printf("Date de compilation : %s\n", __DATE__);
  ```

- **`__TIME__`** : Heure de la compilation au format "HH:MM:SS".

  ```c
  printf("Heure de compilation : %s\n", __TIME__);
  ```