# Modificateurs en Java

En Java, les **modificateurs** sont utilisés pour définir le niveau d'accès des classes, attributs, méthodes et constructeurs. Ils se divisent en deux catégories : **modificateurs d'accès** et **modificateurs de non-accès**.

## 1. Modificateurs d'accès

Les modificateurs d'accès contrôlent le niveau de visibilité et d'accessibilité des classes, méthodes, et attributs.

### Pour les Classes :

- **public** : La classe est accessible par toutes les autres classes.
- **default** *(aucun modificateur)* : La classe est accessible uniquement par les classes du même package.

### Pour les Attributs, Méthodes et Constructeurs :

- **public** : Le code est accessible par toutes les classes.
- **private** : Le code est accessible uniquement dans la classe où il est déclaré.
- **default** *(aucun modificateur)* : Le code est accessible uniquement dans le même package.
- **protected** : Le code est accessible dans le même package et par les sous-classes.

## 2. Modificateurs de Non-Accès

Les modificateurs de non-accès fournissent des fonctionnalités supplémentaires mais ne contrôlent pas le niveau d'accès.

### Pour les Classes :

- **final** : La classe ne peut pas être héritée par d'autres classes.
- **abstract** : La classe ne peut pas être utilisée pour créer des objets (doit être héritée pour être utilisée).

### Pour les Attributs et Méthodes :

- **final** : Les attributs et méthodes ne peuvent pas être surchargés ou modifiés.
- **static** : Les attributs et méthodes appartiennent à la classe plutôt qu'à une instance spécifique (objet).
- **transient** : Les attributs sont ignorés lors de la sérialisation de l'objet.
- **synchronized** : Les méthodes ne peuvent être accédées que par un thread à la fois.
- **volatile** : La valeur d'un attribut n'est pas mise en cache par les threads et est toujours lue dans la mémoire principale.

## Exemple de Modificateurs en Java :

### Modificateur d'accès - `public` et `private` :
```java
public class Voiture {
    private String marque;
    
    public Voiture(String marque) {
        this.marque = marque;
    }

    public String getMarque() {
        return marque;
    }
}
```

### Modificateur de Non-Accès - `final` et `static` :
```java
public class MathUtil {
    public static final double PI = 3.14159;
    
    public static double aireCercle(double rayon) {
        return PI * rayon * rayon;
    }
}
```

Dans cet exemple, `PI` est une constante (`final`) et une variable partagée par toutes les instances de la classe (`static`).