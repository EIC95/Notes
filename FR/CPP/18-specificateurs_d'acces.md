# Spécificateurs d'Accès en C++

## `public`

Les membres déclarés comme publics sont accessibles depuis l'extérieur de la classe. Ils peuvent être modifiés et consultés directement à partir d'objets de la classe.

### Exemple

```cpp
#include <iostream>

class Car {
public:
    std::string brand;
    void honk() {
        std::cout << "Honk! Honk!" << std::endl;
    }
};

int main() {
    Car myCar;
    myCar.brand = "Toyota";  // Accès direct à un membre public
    std::cout << "Brand: " << myCar.brand << std::endl;
    myCar.honk();  // Appel d'une méthode publique
    return 0;
}
```

## `private`

Les membres déclarés comme privés ne sont accessibles que depuis l'intérieur de la classe elle-même. Ils ne peuvent pas être accédés directement depuis l'extérieur de la classe.

### Exemple

```cpp
#include <iostream>

class BankAccount {
private:
    double balance;

public:
    BankAccount(double initialBalance) : balance(initialBalance) {}

    void deposit(double amount) {
        balance += amount;
    }

    void displayBalance() {
        std::cout << "Balance: $" << balance << std::endl;
    }
};

int main() {
    BankAccount account(1000.0);
    account.deposit(500.0);
    account.displayBalance();  // Affiche le solde
    // std::cout << account.balance;  // Erreur : 'balance' est privé
    return 0;
}
```

## `protected`

Les membres déclarés comme protégés sont accessibles dans les classes dérivées mais pas depuis l'extérieur. Ils sont utilisés pour permettre l'accès dans des classes qui héritent de la classe de base.

### Exemple

```cpp
#include <iostream>

class Base {
protected:
    int protectedValue;

public:
    Base(int value) : protectedValue(value) {}
};

class Derived : public Base {
public:
    Derived(int value) : Base(value) {}

    void showValue() {
        std::cout << "Protected Value: " << protectedValue << std::endl;
    }
};

int main() {
    Derived obj(42);
    obj.showValue();  // Accès au membre protégé à travers une classe dérivée
    // std::cout << obj.protectedValue;  // Erreur : 'protectedValue' est protégé
    return 0;
}
```

## `static`

Le mot-clé `static` déclare des membres de classe et des méthodes qui appartiennent à la classe elle-même plutôt qu'aux instances spécifiques. Ces membres sont partagés par toutes les instances de la classe.

### Exemple

```cpp
#include <iostream>

class Counter {
public:
    static int count;

    Counter() {
        count++;
    }

    static void displayCount() {
        std::cout << "Count: " << count << std::endl;
    }
};

int Counter::count = 0;  // Initialisation du membre static

int main() {
    Counter c1;
    Counter c2;
    Counter::displayCount();  // Accès à un membre static sans créer d'instance
    return 0;
}
```
