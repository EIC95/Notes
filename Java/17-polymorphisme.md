# Polymorphisme en Java

Le polymorphisme permet d'utiliser une seule action de différentes manières, en fonction du contexte. En Java, le polymorphisme est souvent lié à l'héritage et aux interfaces, et il se manifeste principalement de deux manières : le polymorphisme de sous-typage et le polymorphisme de surcharge.

### Polymorphisme de Sous-Typage

Le polymorphisme de sous-typage permet à une classe enfant de substituer une classe parent et d'utiliser les méthodes définies dans la classe parent, tout en fournissant une implémentation spécifique. Ce type de polymorphisme est généralement réalisé par la substitution de méthodes.

#### Exemple

```java
class Animal {
    public void makeSound() {
        System.out.println("L'animal fait un bruit");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Le chien aboie");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal myAnimal = new Dog(); // Polymorphisme de sous-typage
        myAnimal.makeSound();       // Appelle la méthode makeSound() de la classe Dog
    }
}
```

Dans cet exemple, même si `myAnimal` est de type `Animal`, il appelle la méthode `makeSound` de la classe `Dog`, grâce au polymorphisme.

### Polymorphisme de Surcharge

Le polymorphisme de surcharge permet d'avoir plusieurs méthodes avec le même nom mais des signatures différentes dans la même classe. La méthode appelée dépend des paramètres passés.

#### Exemple

```java
class Printer {
    public void print(int number) {
        System.out.println("Nombre: " + number);
    }

    public void print(String text) {
        System.out.println("Texte: " + text);
    }
}

public class Main {
    public static void main(String[] args) {
        Printer printer = new Printer();
        printer.print(10);       // Appelle la méthode print(int)
        printer.print("Hello"); // Appelle la méthode print(String)
    }
}
```

Ici, la méthode `print` est surchargée pour accepter différents types d'arguments.