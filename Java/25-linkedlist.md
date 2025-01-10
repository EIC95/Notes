# La classe LinkedList en Java

La **LinkedList** fait partie du package `java.util` et, tout comme l'**ArrayList**, elle implémente l'interface `List`. Toutefois, leur différence fondamentale réside dans leur implémentation interne :

- **ArrayList** utilise un tableau dynamique qui peut être redimensionné si nécessaire.
- **LinkedList** utilise une structure en **liste chaînée** où chaque élément est lié au suivant et au précédent (en cas de liste doublement chaînée).

Ces différences influencent les performances en fonction des opérations effectuées :
- **ArrayList** est plus rapide pour l'accès aléatoire aux éléments, car elle utilise un tableau.
- **LinkedList** est plus performante pour les opérations d'insertion et de suppression au milieu de la liste, car il n'est pas nécessaire de réorganiser tout le tableau comme pour une ArrayList.

## Méthodes principales de la classe LinkedList

| Méthode         | Description                                          |
|-----------------|------------------------------------------------------|
| `addFirst()`    | Ajoute un élément au début de la liste.              |
| `addLast()`     | Ajoute un élément à la fin de la liste.              |
| `removeFirst()` | Supprime le premier élément de la liste.             |
| `removeLast()`  | Supprime le dernier élément de la liste.             |
| `getFirst()`    | Récupère le premier élément de la liste.             |
| `getLast()`     | Récupère le dernier élément de la liste.             |

### Exemple de base avec LinkedList

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        // Création d'une LinkedList de chaînes de caractères
        LinkedList<String> fruits = new LinkedList<>();

        // Ajout d'éléments au début et à la fin de la liste
        fruits.addFirst("Pomme");
        fruits.addLast("Banane");
        fruits.add("Orange"); // Ajoute à la fin par défaut

        // Accès aux premiers et derniers éléments
        System.out.println("Premier fruit : " + fruits.getFirst());
        System.out.println("Dernier fruit : " + fruits.getLast());

        // Suppression d'éléments
        fruits.removeFirst();
        System.out.println("Après suppression du premier fruit : " + fruits);
        
        fruits.removeLast();
        System.out.println("Après suppression du dernier fruit : " + fruits);
    }
}
```

## Différences de performances entre ArrayList et LinkedList

### 1. **Accès aux éléments**
   - **ArrayList** : L'accès à un élément spécifique (via l'indice) est rapide, car les éléments sont stockés dans un tableau.
   - **LinkedList** : L'accès est plus lent, car il faut parcourir les éléments un par un à partir du début ou de la fin.

### 2. **Ajout et suppression d'éléments**
   - **ArrayList** : L'ajout ou la suppression d'éléments au milieu nécessite de déplacer les éléments existants, ce qui peut être coûteux.
   - **LinkedList** : L'ajout ou la suppression d'éléments est plus efficace car seules les références des nœuds adjacents sont modifiées.

### Utilités

La classe **LinkedList** est particulièrement utile lorsque vous avez besoin d'une structure qui permet de **fréquemment insérer ou supprimer des éléments** en début, milieu ou fin de liste. Cependant, si vous avez principalement besoin d'un **accès rapide aux éléments** sans beaucoup de modifications, l'**ArrayList** est plus adaptée.