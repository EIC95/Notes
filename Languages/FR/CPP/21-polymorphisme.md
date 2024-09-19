# Polymorphisme en C++

Le polymorphisme est un concept fondamental de la programmation orientée objet qui permet à une interface unique de représenter différentes formes ou comportements. En C++, le polymorphisme est généralement réalisé via l'héritage et les méthodes virtuelles.

## Définition du Polymorphisme

Le polymorphisme permet à des objets de classes dérivées d'être traités comme des objets de la classe de base. Il permet d'utiliser une interface commune pour des objets de différentes classes, tout en permettant à chaque classe dérivée de définir son propre comportement.

## Polymorphisme par Liaison Dynamique

En C++, le polymorphisme est souvent implémenté à l'aide de la liaison dynamique (ou polymorphisme dynamique). Cela se fait généralement avec des méthodes virtuelles, ce qui permet de déterminer à l'exécution quelle méthode spécifique appeler selon le type réel de l'objet.

### Méthodes Virtuelles

Une méthode virtuelle est une méthode déclarée dans la classe de base avec le mot-clé `virtual`. Les classes dérivées peuvent redéfinir cette méthode pour fournir une implémentation spécifique.

### Exemple de Base

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() { // Méthode virtuelle
        cout << "Base class show function" << endl;
    }
};

class Derived : public Base {
public:
    void show() override { // Redéfinition de la méthode
        cout << "Derived class show function" << endl;
    }
};

int main() {
    Base* bptr;         // Pointeur de base
    Derived d;          // Objet dérivé
    bptr = &d;          // Pointeur de base pointe vers un objet dérivé
    
    bptr->show();       // Appelle la méthode show() de la classe Derived
    
    return 0;
}
```

### Explication

1. **Classe de Base** : La classe `Base` contient une méthode virtuelle `show()`.
2. **Classe Dérivée** : La classe `Derived` redéfinit la méthode `show()` pour fournir un comportement spécifique.
3. **Utilisation du Pointeur** : Un pointeur de type `Base` pointe vers un objet de type `Derived`. Lorsque la méthode `show()` est appelée via ce pointeur, la version de la méthode définie dans la classe `Derived` est exécutée, grâce à la liaison dynamique.
