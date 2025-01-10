# Variables et Constantes

En Java, pour créer une **variable**, vous devez en préciser le type et lui attribuer une valeur. Pour déclarer une **constante**, on utilise le mot clé `final`. Vous pouvez afficher le contenu d'une variable en utilisant la méthode `System.out.println()`.

## Règles de nommage des variables en Java :
- Elles peuvent contenir des lettres, des chiffres, des traits de soulignement (`_`) et des signes dollar (`$`).
- Elles doivent commencer par une lettre, `$` ou `_`.
- Elles doivent commencer par une lettre **minuscule** et ne peuvent pas contenir d'espaces.
- Elles sont sensibles à la **casse** (`myVar` et `myvar` sont différents).
- Les **mots réservés** (comme `int` ou `boolean`) ne peuvent pas être utilisés comme noms.

## Exemple de variables et constantes :

```java
public class Main {
    public static void main(String[] args) {
        int age = 30;               // Variable entière
        final double PI = 3.14159;  // Constante
        String name = "Alice";      // Variable chaîne de caractères

        System.out.println(age);    // Affiche 30
        System.out.println(PI);     // Affiche 3.14159
        System.out.println(name);   // Affiche Alice
    }
}
```