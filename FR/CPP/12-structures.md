# Structures en C++

## Création et Utilisation

Pour créer une structure en C++, utilisez le mot-clé `struct` suivi du nom de la structure et déclarez chacun de ses membres entre accolades. Après la déclaration, vous pouvez créer des variables de ce type de structure.

### Déclaration d'une Structure

**Syntaxe :**

```cpp
struct NomStructure {
    TypeMembre1 membre1;
    TypeMembre2 membre2;
    // Ajoutez d'autres membres si nécessaire
};
```

**Exemple :**

```cpp
struct Personne {
    std::string nom;
    int age;
    float taille;
};
```

### Création d'une Variable de Structure

Après avoir défini la structure, vous pouvez créer des variables de ce type comme suit :

**Exemple :**

```cpp
Personne personne1;
```

### Accès aux Membres

Pour accéder aux membres d'une structure, utilisez l'opérateur `.` (point).

**Exemple :**

```cpp
personne1.nom = "Alice";
personne1.age = 30;
personne1.taille = 1.75f;

// Accéder aux membres
std::cout << "Nom: " << personne1.nom << std::endl;
std::cout << "Age: " << personne1.age << std::endl;
std::cout << "Taille: " << personne1.taille << " m" << std::endl;
```