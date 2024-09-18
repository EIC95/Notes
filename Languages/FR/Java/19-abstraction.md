# Abstraction et Interfaces en Java

L’abstraction en Java permet de masquer certains détails et de ne montrer que les fonctionnalités essentielles d’un objet. En Java, deux concepts sont utilisés pour réaliser l’abstraction : les **classes abstraites** et les **interfaces**.

## Classes Abstraites

Le mot-clé `abstract` est utilisé pour déclarer une classe ou une méthode abstraite. Une **classe abstraite** ne peut pas être instanciée directement et est utilisée pour être héritée par d'autres classes. Elle peut contenir des méthodes abstraites (sans corps) ainsi que des méthodes concrètes (avec un corps).

### Exemple d'une Classe Abstraite

```java
abstract class Animal {
    public abstract void sound(); // Méthode abstraite
    public void sleep() {
        System.out.println("L'animal dort");
    }
}

class Dog extends Animal {
    public void sound() {
        System.out.println("Le chien aboie");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // Appelle la méthode abstraite implémentée
        dog.sleep(); // Appelle la méthode concrète de la classe abstraite
    }
}
```

## Interfaces

Une autre façon de réaliser l’abstraction en Java est d'utiliser des **interfaces**. Une interface en Java est un ensemble de méthodes abstraites qui doivent être implémentées par une classe. Les interfaces permettent à une classe d’hériter de plusieurs comportements (car Java n'autorise pas l’héritage multiple avec des classes).

### Syntaxe de l'Interface

Pour utiliser une interface, on emploie le mot-clé `implements` au lieu de `extends`. Une classe peut implémenter plusieurs interfaces en les séparant par une virgule.

### Exemple d'une Interface

```java
interface Animal {
    void sound(); // Méthode abstraite
    void sleep(); // Méthode abstraite
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Le chien aboie");
    }
    public void sleep() {
        System.out.println("Le chien dort");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound(); // Appelle la méthode implémentée de l'interface
        dog.sleep();
    }
}
```

## Remarques sur les Interfaces

- Comme les **classes abstraites**, les interfaces **ne peuvent pas être instanciées** directement.
- Les méthodes dans une interface sont par **défaut abstraites et publiques**.
- Les attributs dans une interface sont par **défaut publics, statiques et finaux**.
- Les méthodes d'une interface **ne contiennent pas de corps** ; c'est à la classe "implémentante" de les définir.
- Une interface **ne peut pas avoir de constructeur** puisque son but est d'être implémentée, pas instanciée directement.
  
### Implémentation de plusieurs Interfaces

En Java, une classe peut implémenter plusieurs interfaces, ce qui permet d’ajouter plusieurs comportements à une classe.

```java
interface Animal {
    void sound();
}

interface Movable {
    void move();
}

class Dog implements Animal, Movable {
    public void sound() {
        System.out.println("Le chien aboie");
    }
    public void move() {
        System.out.println("Le chien court");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.sound();
        dog.move();
    }
}
```