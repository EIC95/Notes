# Gestion des Exceptions en Java

Lors de l'exécution de code Java, des erreurs peuvent se produire, telles que des erreurs de codage ou des entrées incorrectes. Java gère ces erreurs à l'aide du mécanisme des exceptions. Voici un aperçu des principales fonctionnalités pour la gestion des exceptions en Java.

## Instructions Try et Catch

- **try** : Le bloc `try` contient le code que vous souhaitez tester pour des erreurs.
- **catch** : Le bloc `catch` contient le code qui sera exécuté si une erreur survient dans le bloc `try`. Vous pouvez avoir plusieurs blocs `catch` pour gérer différents types d'exceptions.

```java
try {
    // Code susceptible de générer une exception
} catch (ExceptionType e) {
    // Code pour gérer l'exception
}
```

## Instruction Finally

- **finally** : Le bloc `finally` est utilisé pour exécuter du code après les blocs `try` et `catch`, qu'une exception soit survenue ou non. Il est généralement utilisé pour libérer des ressources, comme fermer des fichiers ou des connexions réseau.

```java
try {
    // Code susceptible de générer une exception
} catch (ExceptionType e) {
    // Code pour gérer l'exception
} finally {
    // Code à exécuter après le try et le catch
}
```

## Création d'Erreurs Personnalisées

- **throw** : Utilisé pour lancer une exception spécifique dans le code. Cela permet de créer des erreurs personnalisées et de signaler des conditions d'erreur spécifiques.

```java
throw new ExceptionType("Message d'erreur");
```

## Types d'Exceptions Communes

Java dispose de nombreux types d'exceptions intégrées, dont voici quelques exemples :

- **ArithmeticException** : Lancée pour des erreurs arithmétiques, comme la division par zéro.
- **FileNotFoundException** : Lancée lorsqu'un fichier requis n'est pas trouvé.
- **ArrayIndexOutOfBoundsException** : Lancée lorsqu'un indice de tableau est en dehors des limites du tableau.
- **SecurityException** : Lancée pour les violations de sécurité.
