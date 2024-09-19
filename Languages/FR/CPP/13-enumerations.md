# Énumérations en C++

## Création et Utilisation

Pour créer une énumération, utilisez le mot-clé `enum`, suivi du nom de l'énumération et déclarez les éléments séparés par des virgules. Les énumérations définissent des constantes entières sous un nom unique, facilitant ainsi la gestion des ensembles de valeurs liées.

### Déclaration d'une Énumération

**Syntaxe :**

```cpp
enum NomEnum {
    Element1,
    Element2,
    Element3,
    // Ajoutez d'autres éléments si nécessaire
};
```

**Exemple :**

```cpp
enum Couleur {
    ROUGE,
    VERT,
    BLEU
};
```

### Création et Utilisation d'une Variable d'Énumération

Pour utiliser une énumération, créez une variable de type de l'énumération et attribuez-lui une valeur parmi les éléments définis.

**Exemple :**

```cpp
Couleur maCouleur = VERT;

// Utiliser la variable d'énumération
if (maCouleur == VERT) {
    std::cout << "La couleur est verte." << std::endl;
}
```

### Valeurs d'Énumération

Par défaut, les éléments d'une énumération commencent à 0 et sont incrémentés automatiquement. Vous pouvez attribuer des valeurs spécifiques aux éléments, et les suivants seront ajustés en conséquence.

**Exemple :**

```cpp
enum JourSemaine {
    LUNDI = 1,
    MARDI,
    MERCREDI,
    JEUDI,
    VENDREDI,
    SAMEDI,
    DIMANCHE
};

// La valeur de DIMANCHE sera 7
```
