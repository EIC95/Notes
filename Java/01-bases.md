# Bases de Java

Java est un langage de programmation orienté objet, fortement typé et sensible à la casse. Chaque programme Java doit contenir au moins une classe publique dont le nom correspond au fichier. La méthode `main` est utilisée comme point d'entrée du programme, où l'exécution commence.

## Sensibilité à la casse

En Java, la casse est très importante. Par exemple, `Main` et `main` sont considérés comme deux entités différentes. Cela s'applique aux classes, méthodes, variables et autres identificateurs.

## Structure de base d'un programme Java

Un programme Java suit une structure générale qui doit être respectée. Voici les principaux éléments :

1. **Déclaration de la classe** : Chaque programme Java doit contenir au moins une classe. Si la classe est publique, son nom doit correspondre au nom du fichier (ex : `Main.java` contient `public class Main`).
   
2. **La méthode `main`** : La méthode `main` est le point d'entrée de tout programme Java. C'est là que l'exécution commence.
   
3. **Les blocs de code** : Les instructions Java sont regroupées à l'intérieur de blocs `{}`. Par exemple, le code de la méthode `main` se trouve à l'intérieur des accolades de la classe.

4. **Les commentaires** : Il existe deux façons d'écrire des
commentaires en java. Sur une seule ligne
avec **`//`** et sur plusieurs lignes avec **`/* */`**.

### Exemple de programme Java simple :

```java
// Classe principale du programme
public class Main {

    /* Méthode principale qui est le point d'entrée du programme*/
    public static void main(String[] args) {
        // Affiche un message à l'écran
        System.out.println("Bonjour, monde !");
    }
}
```
