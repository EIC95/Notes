# Encapsulation en Java

L'encapsulation est un principe fondamental de la programmation orientée objet en Java, qui consiste à cacher les données "sensibles" aux utilisateurs. Pour y parvenir, on suit les étapes suivantes :

1. **Déclarer les attributs de classe comme `private`** : Cela empêche l'accès direct aux données depuis l'extérieur de la classe.
2. **Fournir des méthodes publiques `get` et `set`** : Ces méthodes permettent de lire et modifier les variables privées, tout en contrôlant leur accès et leur modification.

### Exemple d'encapsulation

```java
public class Person {
    private String name;  // Attribut privé

    // Méthode pour accéder à la variable privée
    public String getName() {
        return name;
    }

    // Méthode pour modifier la variable privée
    public void setName(String name) {
        this.name = name;
    }
}
```

Dans cet exemple, l'attribut `name` est déclaré comme privé et on utilise les méthodes `getName` et `setName` pour accéder et modifier sa valeur.