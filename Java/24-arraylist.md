# La classe ArrayList en Java

L'**ArrayList** est une classe du package `java.util` qui implémente une **liste redimensionnable**, contrairement aux tableaux intégrés dont la taille est fixe. Avec une `ArrayList`, vous pouvez ajouter, supprimer ou modifier des éléments à tout moment sans avoir à créer un nouveau tableau.

## Méthodes principales de la classe ArrayList

| Méthode                | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| `add(element)`          | Ajoute un élément à la fin de la liste.                                      |
| `add(index, element)`   | Insère un élément à une position spécifique.                                 |
| `get(index)`            | Retourne l'élément à la position spécifiée.                                  |
| `set(index, element)`   | Remplace l'élément à la position spécifiée.                                  |
| `remove(index)`         | Supprime l'élément à la position spécifiée.                                  |
| `remove(element)`       | Supprime la première occurrence de l'élément spécifié.                       |
| `clear()`               | Supprime tous les éléments de la liste.                                      |
| `size()`                | Retourne le nombre d'éléments dans la liste.                                 |
| `isEmpty()`             | Vérifie si la liste est vide.                                                |

### Exemple de base avec ArrayList

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        // Création d'une ArrayList de chaînes de caractères
        ArrayList<String> fruits = new ArrayList<>();

        // Ajout d'éléments à l'ArrayList
        fruits.add("Pomme");
        fruits.add("Banane");
        fruits.add("Orange");

        // Accès à un élément
        System.out.println("Premier fruit : " + fruits.get(0));

        // Modification d'un élément
        fruits.set(1, "Fraise");
        System.out.println("Deuxième fruit modifié : " + fruits.get(1));

        // Suppression d'un élément
        fruits.remove(2);
        System.out.println("Liste après suppression : " + fruits);

        // Taille de la liste
        System.out.println("Nombre de fruits : " + fruits.size());
    }
}
```

## Trier une ArrayList avec la classe Collections

La classe `Collections` offre diverses méthodes utilitaires pour manipuler les collections, notamment la méthode `sort()` pour trier une `ArrayList` en ordre croissant ou alphabétique.

### Exemple de tri :

```java
import java.util.ArrayList;
import java.util.Collections;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Pomme");
        fruits.add("Banane");
        fruits.add("Orange");

        // Tri de l'ArrayList
        Collections.sort(fruits);
        System.out.println("Fruits triés : " + fruits);

        // Tri dans l'ordre inverse
        Collections.sort(fruits, Collections.reverseOrder());
        System.out.println("Fruits triés en ordre inverse : " + fruits);
    }
}
```

## Utilisation des classes Wrapper

En Java, les éléments d'une `ArrayList` doivent être des objets. Cela signifie que les types primitifs (comme `int`, `boolean`, `char`) ne peuvent pas être directement utilisés dans une `ArrayList`. Pour contourner cela, Java propose des **classes wrapper** qui encapsulent les types primitifs.

| Type primitif | Classe Wrapper |
|---------------|----------------|
| `int`         | `Integer`      |
| `boolean`     | `Boolean`      |
| `char`        | `Character`    |
| `double`      | `Double`       |

### Exemple avec des nombres entiers (Integer) :

```java
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        // Création d'une ArrayList d'entiers
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(10);
        numbers.add(20);
        numbers.add(30);

        System.out.println("Liste des nombres : " + numbers);
    }
}
```

### Utilités

La classe `ArrayList` est extrêmement utile pour gérer des collections d'objets avec une taille dynamique en Java. Grâce à ses méthodes variées et à l'intégration avec la classe `Collections`, elle permet de manipuler efficacement des listes d'objets tout en garantissant une gestion simplifiée des types de données.