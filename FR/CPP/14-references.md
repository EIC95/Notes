# Références en C++

Une référence en C++ est un alias pour une autre variable. Plutôt que de manipuler directement la variable d'origine, une référence vous permet d'interagir avec elle de manière indirecte.

## Déclaration et Initialisation

Pour déclarer une référence, utilisez le symbole `&`. Une fois qu'une référence est initialisée, elle ne peut plus être réassignée pour référencer une autre variable. De plus, une référence doit être initialisée lors de sa déclaration.

**Syntaxe :**

```cpp
type& referenceName = variableName;
```

**Exemple :**

```cpp
int x = 10;
int& ref = x;  // ref est une référence à x

ref = 20;  // modifie x à 20
std::cout << x;  // affiche 20
```

## Utilisation dans les Fonctions

Les références sont particulièrement utiles pour les fonctions afin de modifier les arguments sans les copier, ce qui peut être coûteux pour les grands objets.

**Exemple :**

```cpp
void increment(int& n) {
    n++;
}

int main() {
    int value = 5;
    increment(value);
    std::cout << value;  // affiche 6
}
```

## Références Constantes

Les références peuvent également être utilisées avec le mot-clé `const` pour éviter la copie tout en protégeant les données d'origine contre toute modification.

**Exemple :**

```cpp
void printValue(const int& n) {
    std::cout << n;
}

int main() {
    int value = 10;
    printValue(value);  // affiche 10
}
```
