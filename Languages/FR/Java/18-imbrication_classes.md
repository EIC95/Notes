# Classes imbriquées en Java

En Java, il est possible de définir des classes imbriquées, c'est-à-dire des classes déclarées à l'intérieur d'une autre classe. Les classes imbriquées sont utilisées pour regrouper des classes qui sont étroitement liées et améliorent la lisibilité et la maintenabilité du code.

### Types de Classes Imbriquées

1. **Classe Interne (Non-Static)**
   
   Une classe interne est une classe qui est déclarée à l'intérieur d'une autre classe. Par défaut, une classe interne a accès aux membres (attributs et méthodes) de la classe externe, même si ces membres sont privés.

   #### Exemple

   ```java
   public class OuterClass {
       private String outerField = "Attribut de la classe externe";

       class InnerClass {
           public void display() {
               System.out.println("Accès depuis la classe interne : " + outerField);
           }
       }

       public static void main(String[] args) {
           OuterClass outer = new OuterClass();
           OuterClass.InnerClass inner = outer.new InnerClass();
           inner.display(); // Affiche l'attribut de la classe externe
       }
   }
   ```

2. **Classe Interne Static**

   Une classe interne statique est une classe imbriquée qui est marquée avec le mot-clé `static`. Contrairement aux classes internes non-statiques, les classes internes statiques ne peuvent pas accéder aux membres non-statiques de la classe externe.

   #### Exemple

   ```java
   public class OuterClass {
       private static String staticOuterField = "Attribut statique de la classe externe";

       static class StaticInnerClass {
           public void display() {
               System.out.println("Accès depuis la classe interne statique : " + staticOuterField);
           }
       }

       public static void main(String[] args) {
           OuterClass.StaticInnerClass inner = new OuterClass.StaticInnerClass();
           inner.display(); // Affiche l'attribut statique de la classe externe
       }
   }
   ```

3. **Classe Locale**

   Une classe locale est déclarée à l'intérieur d'une méthode. Elle est accessible uniquement dans la méthode où elle est définie.

   #### Exemple

   ```java
   public class OuterClass {
       public void method() {
           class LocalClass {
               public void display() {
                   System.out.println("Classe locale");
               }
           }

           LocalClass local = new LocalClass();
           local.display(); // Affiche le message depuis la classe locale
       }

       public static void main(String[] args) {
           OuterClass outer = new OuterClass();
           outer.method();
       }
   }
   ```

4. **Classe Anonyme**

   Une classe anonyme est une classe sans nom, généralement utilisée pour créer une instance d'une classe avec une implémentation spécifique, souvent dans les cas où vous avez besoin d'une classe temporaire.

   #### Exemple

   ```java
   public class OuterClass {
       public void method() {
           Runnable runnable = new Runnable() {
               @Override
               public void run() {
                   System.out.println("Classe anonyme");
               }
           };

           new Thread(runnable).start(); // Exécute la classe anonyme
       }

       public static void main(String[] args) {
           OuterClass outer = new OuterClass();
           outer.method();
       }
   }
   ```

### Avantages des Classes Imbriquées

- **Encapsulation** : Les classes imbriquées permettent de regrouper des classes qui sont logiquement liées, ce qui facilite leur gestion et leur encapsulation.
- **Accès aux Membres de la Classe Externe** : Les classes internes non-statiques ont accès aux membres de la classe externe, ce qui peut simplifier le code.
- **Organisation** : Les classes imbriquées permettent de maintenir un code plus organisé et lisible en regroupant des classes étroitement liées.