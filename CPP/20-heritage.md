# Héritage en C++

L'héritage est un concept clé de la programmation orientée objet qui permet de créer une nouvelle classe basée sur une classe existante. La classe existante est appelée "classe de base" ou "classe parent", tandis que la nouvelle classe est appelée "classe dérivée" ou "classe enfant". L'héritage permet à la classe dérivée de réutiliser, d'étendre ou de modifier le comportement de la classe de base.

## Syntaxe de l'Héritage

Pour déclarer qu'une classe dérive d'une autre, utilisez le symbole `:` suivi du type d'héritage et du nom de la classe de base. La syntaxe générale est :

```cpp
class DerivedClass : AccessSpecifier BaseClass {
    // Membres de la classe dérivée
};
```

### Exemple de Base

```cpp
class Base {
public:
    int publicValue;
protected:
    int protectedValue;
private:
    int privateValue;
};
```

## Types d'Héritage

En C++, vous pouvez spécifier la visibilité des membres hérités avec différents types d'héritage : `public`, `protected`, et `private`. Voici ce que chacun signifie pour les membres de la classe dérivée :

### Héritage Public

Avec l'héritage public, les membres de la classe de base conservent leur accessibilité dans la classe dérivée :

- **Public** dans la classe de base reste **public** dans la classe dérivée.
- **Protected** dans la classe de base reste **protected** dans la classe dérivée.
- **Private** dans la classe de base reste **private** dans la classe dérivée.

```cpp
class DerivedPublic : public Base {
    // publicValue est public
    // protectedValue est protected
    // privateValue est inaccessible
};
```

### Héritage Protégé

Avec l'héritage protégé, les membres publics et protégés de la classe de base deviennent protégés dans la classe dérivée :

- **Public** devient **protected**.
- **Protected** reste **protected**.
- **Private** reste **private**.

```cpp
class DerivedProtected : protected Base {
    // publicValue devient protected
    // protectedValue reste protected
    // privateValue est inaccessible
};
```

### Héritage Privé

Avec l'héritage privé, tous les membres de la classe de base deviennent privés dans la classe dérivée :

- **Public** devient **private**.
- **Protected** devient **private**.
- **Private** reste **private**.

```cpp
class DerivedPrivate : private Base {
    // publicValue devient private
    // protectedValue devient private
    // privateValue est inaccessible
};
```

## Exemple Complet

Voici un exemple complet illustrant les différents types d'héritage :

```cpp
#include <iostream>

class Base {
public:
    int publicValue;
protected:
    int protectedValue;
private:
    int privateValue;
};

class DerivedPublic : public Base {
public:
    void accessBase() {
        // Accès aux membres publics et protégés de la classe de base
        publicValue = 10;       // Ok
        protectedValue = 20;    // Ok
        // privateValue = 30;   // Erreur : privateValue est inaccessible
    }
};

class DerivedProtected : protected Base {
public:
    void accessBase() {
        // Accès aux membres publics et protégés de la classe de base, mais tous deviennent protégés
        publicValue = 10;       // Ok
        protectedValue = 20;    // Ok
        // privateValue = 30;   // Erreur : privateValue est inaccessible
    }
};

class DerivedPrivate : private Base {
public:
    void accessBase() {
        // Accès aux membres publics et protégés de la classe de base, mais tous deviennent privés
        publicValue = 10;       // Ok
        protectedValue = 20;    // Ok
        // privateValue = 30;   // Erreur : privateValue est inaccessible
    }
};

int main() {
    DerivedPublic dp;
    dp.publicValue = 5;    // Accessible
    // dp.protectedValue = 5; // Erreur : protectedValue est inaccessible
    // dp.privateValue = 5;   // Erreur : privateValue est inaccessible

    DerivedProtected dpr;
    // dpr.publicValue = 5;  // Erreur : publicValue est protected
    // dpr.protectedValue = 5; // Erreur : protectedValue est protected
    // dpr.privateValue = 5; // Erreur : privateValue est inaccessible

    DerivedPrivate dpt;
    // dpt.publicValue = 5;  // Erreur : publicValue est private
    // dpt.protectedValue = 5; // Erreur : protectedValue est private
    // dpt.privateValue = 5; // Erreur : privateValue est inaccessible

    return 0;
}

