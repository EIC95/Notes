# Tableaux et Vecteurs en C++

## 1. Tableaux

### 1.1 Déclaration et Initialisation

Pour déclarer un tableau, définissez le type de la variable, spécifiez le nom du tableau suivi de crochets, et indiquez le nombre d'éléments qu'il doit stocker. 

**Exemple :**

```cpp
int tableau[5];  // Tableau d'entiers avec 5 éléments
```

Pour déclarer un tableau multidimensionnel, ajoutez des crochets supplémentaires pour chaque dimension.

**Exemple :**

```cpp
int tableau2D[3][4];  // Tableau 2D avec 3 lignes et 4 colonnes
```

### 1.2 Taille d'un Tableau

Utilisez l'opérateur `sizeof()` pour obtenir la taille totale du tableau en octets, puis divisez par la taille d'un élément pour obtenir le nombre d'éléments.

**Exemple :**

```cpp
int tableau[10];
size_t taille = sizeof(tableau) / sizeof(tableau[0]);
```

## 2. Vecteurs (`std::vector`)

Un vecteur est un conteneur dynamique qui permet de stocker une collection d'éléments de même type et dont la taille peut être modifiée dynamiquement. Il est défini dans la bibliothèque `<vector>`.

**Inclure la bibliothèque :**

```cpp
#include <vector>
```

### 2.1 Méthodes Utiles

- **`push_back(value)`**  
  Ajoute un élément à la fin du vecteur.
  ```cpp
  std::vector<int> vec;
  vec.push_back(10);
  ```

- **`pop_back()`**  
  Supprime l'élément à la fin du vecteur.
  ```cpp
  vec.pop_back();
  ```

- **`at(index)`**  
  Accède à l'élément à l'indice spécifié avec vérification des limites.
  ```cpp
  int valeur = vec.at(2);
  ```

- **`size()`**  
  Retourne le nombre d'éléments dans le vecteur.
  ```cpp
  size_t taille = vec.size();
  ```

- **`std::sort(begin, end)`**  
  Trie les éléments du vecteur entre les itérateurs `begin` et `end` en utilisant l'opérateur `<`.
  ```cpp
  #include <algorithm>
  std::sort(vec.begin(), vec.end());
  ```
```