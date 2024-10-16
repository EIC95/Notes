# Expressions Lambda en Java

Les expressions lambda, introduites dans Java 8, permettent de créer des blocs de code concis qui peuvent être utilisés comme des instances de fonctions anonymes. Elles offrent une manière plus expressive et fonctionnelle de travailler avec des fonctions et des collections en Java.

## Syntaxe des Expressions Lambda

Une expression lambda est constituée d'un ou plusieurs paramètres, d'une flèche (`->`), et d'une expression ou d'un bloc de code qui définit le corps de la fonction. 

### Syntaxe de Base

- **Expression Lambda Simple** : Contient un seul paramètre et une seule expression.
  ```java
  (param) -> expression
  ```

  Exemple :
  ```java
  x -> x * x
  ```

- **Expression Lambda avec Plusieurs Paramètres** : Les paramètres doivent être placés entre parenthèses.
  ```java
  (param1, param2) -> expression
  ```

  Exemple :
  ```java
  (x, y) -> x + y
  ```

### Blocs de Code

- **Bloc de Code Lambda** : Utilisé pour des opérations plus complexes. Les accolades `{}` sont nécessaires, et une instruction `return` est requise si une valeur doit être renvoyée.
  ```java
  (param1, param2) -> {
      // Instructions
      return result;
  }
  ```

  Exemple :
  ```java
  (x, y) -> {
      int sum = x + y;
      return sum;
  }
  ```

## Utilisation des Expressions Lambda

Les expressions lambda sont souvent transmises en tant que paramètres à des méthodes ou à des interfaces fonctionnelles, telles que celles définies dans le package `java.util.function`. Elles sont particulièrement utiles pour les opérations sur des collections avec les API de flux (`Stream API`).

### Exemple d'Utilisation avec `ArrayList`

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>();
        names.add("Alice");
        names.add("Bob");
        names.add("Charlie");

        // Utilisation de lambda pour parcourir la liste
        names.forEach(name -> System.out.println(name));
    }
}
```

### Exemple d'Utilisation avec `Stream`

```java
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // Utilisation de lambda pour filtrer et afficher les nombres pairs
        numbers.stream()
               .filter(n -> n % 2 == 0)
               .forEach(n -> System.out.println(n));
    }
}
```

## Limitations des Expressions Lambda

- **Retour de Valeur** : Les expressions lambda doivent renvoyer immédiatement une valeur lorsqu'elles sont utilisées comme expressions.
- **Pas d'Instructions Complexes** : Les expressions lambda ne peuvent pas contenir de variables, d'affectations ou d'instructions comme `if` ou `for` à moins d'utiliser un bloc de code.
- **Ne Peuvent pas Contenir de Variables Locales** : Elles ne peuvent pas introduire de variables locales ni de logique complexe sans passer à un bloc de code.

Les expressions lambda améliorent la concision et la lisibilité du code en Java, particulièrement dans les contextes où les opérations fonctionnelles sont courantes.
