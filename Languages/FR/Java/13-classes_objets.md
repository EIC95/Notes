# Classes et objets en Java

En Java, une **classe** est une structure qui définit des objets. Les objets sont des instances de classes qui contiennent des attributs et des méthodes.

## 1. Création d'une classe

Pour créer une classe en Java, on utilise le mot-clé `class` suivi du nom de la classe.

### Exemple de classe :
```java
public class Personne {
    String nom;
    int age;
}
```

## 2. Création d'un objet

Une fois la classe définie, vous pouvez créer des objets en spécifiant le nom de la classe, suivi du nom de l'objet et du mot-clé `new`.

### Exemple de création d'objet :
```java
Personne p1 = new Personne();
```

## 3. Utilisation d'un objet

Vous pouvez accéder aux attributs et méthodes d'un objet en utilisant la syntaxe **pointée** (`.`).

### Exemple d'accès aux attributs et méthodes :
```java
p1.nom = "Alice";
p1.age = 30;
System.out.println(p1.nom); // Affiche Alice
```

## 4. Le mot-clé `this`

Le mot-clé `this` fait référence à l'instance actuelle de l'objet dans une méthode. Il est souvent utilisé pour distinguer les attributs de l'objet des paramètres de méthode ayant le même nom.

### Exemple :
```java
public class Personne {
    String nom;
    int age;
    
    public void setNom(String nom) {
        this.nom = nom; // Utilisation de this pour faire référence à l'attribut nom
    }
}
```

## 5. Constructeur en Java

Un **constructeur** est une méthode spéciale utilisée pour initialiser les objets. Il porte le même nom que la classe et n'a pas de type de retour. Il peut accepter des paramètres pour initialiser les attributs d'un objet lors de sa création.

### Exemple de constructeur :
```java
public class Personne {
    String nom;
    int age;
    
    // Constructeur
    public Personne(String nom, int age) {
        this.nom = nom;
        this.age = age;
    }
}
```

### Création d'objet avec constructeur :
```java
Personne p2 = new Personne("Bob", 25);
System.out.println(p2.nom); // Affiche Bob
```

## 6. Organisation des classes

Vous pouvez organiser votre code en séparant les classes dans différents fichiers. Dans cet exemple, nous avons deux fichiers : `Main.java` et `Second.java`.

### Main.java :
```java
public class Main {
    public static void main(String[] args) {
        Second obj = new Second();
        obj.message();
    }
}
```

### Second.java :
```java
public class Second {
    public void message() {
        System.out.println("Hello from Second class!");
    }
}
```

### Résultat :
Lorsque vous exécutez `Main.java`, le message "Hello from Second class!" sera affiché à l'écran.
