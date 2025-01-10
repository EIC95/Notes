# Pointeurs en C++

Un pointeur est une variable qui stocke l'adresse mémoire d'une autre variable. 

## Déclaration et Initialisation

Pour déclarer un pointeur, utilisez le symbole `*`. Les pointeurs doivent être du même type que la variable qu'ils pointent. 

**Syntaxe :**

```cpp
type* pointerName;
```

**Exemple :**

```cpp
int x = 10;
int* p = &x;  // p est un pointeur vers x
```

## Initialisation Nulle

Un pointeur peut être nul, ce qui signifie qu'il ne pointe vers aucune adresse valide. Utilisez la constante `nullptr` pour initialiser un pointeur nul.

**Exemple :**

```cpp
int* p = nullptr;  // p est un pointeur nul
```

## Accès à la Valeur

Utilisez l'opérateur `*` pour accéder ou modifier la valeur pointée par le pointeur.

**Exemple :**

```cpp
int x = 10;
int* p = &x;
*p = 20;  // modifie x à 20
std::cout << x;  // affiche 20
```

## Utilisation des Pointeurs

Les pointeurs permettent de modifier les arguments d'une fonction ou de gérer des tableaux dynamiques.

**Exemple de fonction :**

```cpp
void increment(int* n) {
    (*n)++;
}

int main() {
    int value = 5;
    increment(&value);
    std::cout << value;  // affiche 6
}
```

**Exemple avec tableau dynamique :**

```cpp
int* arr = new int[5];  // allocation dynamique d'un tableau de 5 entiers
delete[] arr;  // libération de la mémoire
```