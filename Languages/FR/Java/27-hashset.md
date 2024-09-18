# La classe HashSet en Java

La **HashSet** fait partie du package `java.util` et est utilisée pour stocker une collection d'éléments **uniques**. Cela signifie qu'il ne peut y avoir de doublons dans un **HashSet**. Cette structure de données est utile lorsque vous voulez garantir l'unicité des éléments.

## Méthodes principales de la classe HashSet

| Méthode               | Description                                             |
|-----------------------|---------------------------------------------------------|
| `add(element)`        | Ajoute un élément dans le HashSet.                       |
| `contains(Object o)`  | Vérifie si l'élément spécifié est présent dans le HashSet.|
| `remove(Object o)`    | Supprime l'élément spécifié du HashSet.                  |
| `clear()`             | Vide tous les éléments du HashSet.                       |
| `size()`              | Retourne le nombre d'éléments dans le HashSet.           |

### Exemple de base avec HashSet

```java
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        // Création d'un HashSet
        HashSet<String> fruits = new HashSet<>();

        // Ajout d'éléments dans le HashSet
        fruits.add("Pomme");
        fruits.add("Banane");
        fruits.add("Orange");
        fruits.add("Pomme"); // Doublon, ne sera pas ajouté

        // Vérifier si un élément est présent
        System.out.println("Contient Banane ? " + fruits.contains("Banane"));

        // Suppression d'un élément
        fruits.remove("Orange");
        System.out.println("Après suppression : " + fruits);

        // Taille du HashSet
        System.out.println("Nombre d'éléments : " + fruits.size());

        // Vider le HashSet
        fruits.clear();
        System.out.println("Après avoir vidé le HashSet : " + fruits);
    }
}
```

### Particularités

- Un **HashSet** ne conserve pas l'ordre des éléments. L'ordre d'insertion n'est pas garanti.
- Les éléments d'un **HashSet** sont uniques. Si vous tentez d'ajouter un élément déjà existant, l'ajout sera ignoré.
- Les opérations d'ajout, de suppression et de vérification sont rapides grâce à l'utilisation d'une **table de hachage**.

### Applications de HashSet

Le **HashSet** est souvent utilisé lorsque vous avez besoin d'une collection d'éléments uniques et que l'ordre n'a pas d'importance, par exemple :
- Pour stocker une liste d'éléments où les doublons ne sont pas autorisés,
- Pour réaliser des tests de présence rapide d'un élément,
- Pour implémenter des algorithmes qui nécessitent des ensembles mathématiques (comme les unions ou les intersections).