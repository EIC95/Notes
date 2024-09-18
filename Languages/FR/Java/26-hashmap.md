# La classe HashMap en Java

La **HashMap** fait partie du package `java.util` et est utilisée pour stocker des éléments sous forme de **paires clé-valeur**. Chaque clé est unique et associe une valeur spécifique. Contrairement aux tableaux indexés par des entiers, une **HashMap** permet d'utiliser n'importe quel type d'objet (comme un `String`) comme clé pour accéder aux valeurs.

## Méthodes principales de la classe HashMap

| Méthode             | Description                                            |
|---------------------|--------------------------------------------------------|
| `put(cle, valeur)`  | Ajoute une paire clé-valeur dans la HashMap.            |
| `get(cle)`          | Renvoie la valeur associée à une clé donnée.            |
| `remove(cle)`       | Supprime la paire clé-valeur associée à la clé donnée.  |
| `clear()`           | Vide toutes les paires clé-valeur de la HashMap.        |
| `size()`            | Retourne le nombre de paires clé-valeur dans la HashMap.|

### Exemple de base avec HashMap

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // Création d'une HashMap
        HashMap<String, Integer> population = new HashMap<>();

        // Ajout de paires clé-valeur avec la méthode put()
        population.put("France", 67000000);
        population.put("Allemagne", 83000000);
        population.put("Japon", 126000000);

        // Accès à la valeur associée à une clé avec get()
        System.out.println("Population de la France : " + population.get("France"));

        // Suppression d'une paire clé-valeur
        population.remove("Japon");
        System.out.println("Après suppression du Japon : " + population);

        // Taille de la HashMap
        System.out.println("Nombre de pays dans la HashMap : " + population.size());

        // Vider la HashMap
        population.clear();
        System.out.println("Après avoir vidé la HashMap : " + population);
    }
}
```

### Particularités

- Une **HashMap** ne conserve pas l'ordre des éléments, c'est-à-dire que l'ordre d'insertion n'est pas garanti.
- Les clés doivent être uniques. Si vous ajoutez une clé déjà existante, la valeur associée sera remplacée.
- Une **HashMap** permet des opérations rapides d'insertion, de suppression et d'accès aux éléments grâce à l'utilisation de **tables de hachage**.

### Applications de HashMap

La **HashMap** est idéale lorsque vous avez besoin d'une structure de données où vous pouvez rapidement retrouver des valeurs via une clé unique, par exemple pour :
- Stocker des résultats de calculs,
- Créer des index par clés uniques (par exemple, des noms, des identifiants),
- Associer des informations aux clés d'un dictionnaire.