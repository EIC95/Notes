# Les Énumérations en Java

En Java, une **énumération** (ou `enum`) est un type spécial de classe qui représente un ensemble fixe de constantes. Une énumération est souvent utilisée lorsque vous avez besoin d'un ensemble de valeurs prédéfinies qui ne changent pas, comme des jours de la semaine, des directions, ou des niveaux de priorité.

## Syntaxe d'une Énumération

Pour créer une énumération, utilisez le mot-clé `enum`. Les constantes d'une énumération doivent être écrites en lettres majuscules, et elles sont séparées par des virgules.

### Exemple d'une Énumération Simple

```java
enum Day {
    LUNDI, MARDI, MERCREDI, JEUDI, VENDREDI, SAMEDI, DIMANCHE
}

public class Main {
    public static void main(String[] args) {
        Day day = Day.LUNDI;
        System.out.println(day); // Affiche LUNDI
    }
}
```

## Accès aux Constantes d'une Énumération

Vous pouvez accéder à une constante d'énumération en utilisant l'opérateur point (`.`) :

```java
Day day = Day.JEUDI;
```

## Parcourir les Constantes d'une Énumération

L'énumération fournit une méthode `values()` qui renvoie un tableau de toutes les constantes définies. Cela permet de parcourir facilement les valeurs d'une énumération.

### Exemple de Parcours d'une Énumération

```java
public class Main {
    public static void main(String[] args) {
        for (Day day : Day.values()) {
            System.out.println(day);
        }
    }
}
```

### Sortie :
```
LUNDI
MARDI
MERCREDI
JEUDI
VENDREDI
SAMEDI
DIMANCHE
```

## Ajout d'Attributs et de Méthodes à une Énumération

Tout comme une classe, une énumération peut avoir des attributs et des méthodes. Les constantes d'une énumération sont implicitement **public**, **static** et **final**, ce qui signifie qu'elles ne peuvent pas être modifiées une fois définies. Cependant, vous pouvez ajouter des constructeurs, des méthodes et des attributs pour enrichir les énumérations.

### Exemple d'Énumération avec Attributs et Méthodes

```java
enum Color {
    ROUGE("Rouge"),
    VERT("Vert"),
    BLEU("Bleu");

    private String name;

    // Constructeur de l'énumération
    Color(String name) {
        this.name = name;
    }

    // Méthode pour obtenir le nom
    public String getName() {
        return name;
    }
}

public class Main {
    public static void main(String[] args) {
        Color color = Color.ROUGE;
        System.out.println(color.getName()); // Affiche "Rouge"
    }
}
```

## Remarques sur les Énumérations

1. **Immutabilité** : Les constantes d'une énumération sont inchangeables (ne peuvent pas être modifiées).
2. **Héritage limité** : Les énumérations ne peuvent pas hériter d'autres classes, mais elles peuvent implémenter des interfaces.
3. **Classe interne** : Une énumération peut être déclarée à l'intérieur d'une classe comme n'importe quel autre type de classe.
  
### Exemple d'Énumération Interne

```java
public class Main {
    enum Niveau {
        BAS, MOYEN, HAUT
    }

    public static void main(String[] args) {
        Niveau niveau = Niveau.HAUT;
        System.out.println(niveau); // Affiche HAUT
    }
}
```