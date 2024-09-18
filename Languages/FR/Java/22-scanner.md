# Classe Scanner en Java

La classe **Scanner** est utilisée pour obtenir des **entrées de l'utilisateur** dans les programmes Java. Elle fait partie du package `java.util` et doit être importée avant utilisation.

Pour utiliser la classe `Scanner`, vous devez :
1. Créer un objet de la classe `Scanner`.
2. Utiliser une des méthodes de l'objet `Scanner` pour lire les données de l'utilisateur.

Voici un exemple d'importation et d'utilisation de `Scanner` :

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in); // Création d'un objet Scanner

        System.out.println("Entrez votre nom : ");
        String nom = scanner.nextLine();  // Utilisation de nextLine pour lire une chaîne

        System.out.println("Bonjour " + nom);
    }
}
```

Dans cet exemple, `nextLine()` est utilisé pour lire une **chaîne de caractères** saisie par l'utilisateur.

## Méthodes de la Classe Scanner

Voici quelques méthodes couramment utilisées avec `Scanner` pour lire différentes **types de données** :

| Méthode          | Description                                   |
|------------------|-----------------------------------------------|
| `nextBoolean()`  | Lit une valeur **booléenne** de l'utilisateur  |
| `nextByte()`     | Lit une valeur de type **byte** de l'utilisateur |
| `nextDouble()`   | Lit une valeur de type **double** de l'utilisateur |
| `nextFloat()`    | Lit une valeur de type **float** de l'utilisateur |
| `nextInt()`      | Lit une valeur de type **int** de l'utilisateur |
| `nextLine()`     | Lit une **chaîne de caractères** de l'utilisateur |
| `nextLong()`     | Lit une valeur de type **long** de l'utilisateur |
| `nextShort()`    | Lit une valeur de type **short** de l'utilisateur |

## Exemple avec plusieurs types d'entrée :

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Entrez votre âge : ");
        int age = scanner.nextInt();  // Utilisation de nextInt pour lire un entier

        System.out.println("Entrez votre taille (en mètres) : ");
        double taille = scanner.nextDouble();  // Utilisation de nextDouble pour lire un nombre à virgule flottante

        System.out.println("Vous avez " + age + " ans et mesurez " + taille + " m.");
    }
}
```

Dans cet exemple, on utilise `nextInt()` pour lire un entier et `nextDouble()` pour lire un nombre décimal.

## Remarque :
- Le **Scanner** lit les données à partir de la console (par défaut `System.in`).
- Après avoir utilisé des méthodes comme `nextInt()` ou `nextDouble()`, si vous souhaitez lire une chaîne avec `nextLine()`, vous devez parfois gérer les sauts de ligne en ajoutant un `scanner.nextLine()` supplémentaire.
