# Héritage en Java

L'héritage permet à une classe de dériver les propriétés et les méthodes d'une autre classe. Cela favorise la réutilisation du code et permet d'organiser les classes de manière hiérarchique. En Java, pour hériter d'une classe, on utilise le mot-clé `extends`.

### Syntaxe de l'héritage

```java
class Parent {
    // Attributs et méthodes de la classe Parent
}

class Child extends Parent {
    // La classe Child hérite des attributs et méthodes de la classe Parent
}
```

### Exemple d'héritage

```java
public class Animal {
    public void makeSound() {
        System.out.println("L'animal fait un bruit");
    }
}

public class Dog extends Animal {
    public void bark() {
        System.out.println("Le chien aboie");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound();  // Méthode héritée de la classe Animal
        dog.bark();       // Méthode propre à la classe Dog
    }
}
```

Dans cet exemple, la classe `Dog` hérite de la classe `Animal` et peut accéder à la méthode `makeSound`.