# Méthodes en Java

En Java, une méthode est un bloc de code qui exécute une tâche spécifique. Les méthodes sont définies au sein des classes et permettent de réutiliser du code de manière modulaire.

## 1. Création d'une méthode

Pour créer une méthode en Java, vous devez spécifier un type de retour (qui peut être n'importe quel type de données ou `void` si la méthode ne retourne rien), un nom de méthode, une liste de paramètres entre parenthèses (qui peut être vide), et un corps de méthode délimité par des accolades `{}`.

### Exemple de méthode :
```java
public int addition(int a, int b) {
    return a + b;
}
```

Cette méthode `addition` prend deux entiers `a` et `b` en paramètres et retourne leur somme.

## 2. Appel d'une méthode

Pour appeler une méthode, il suffit d'écrire son nom suivi de parenthèses, avec les arguments appropriés si nécessaire, et un point-virgule à la fin.

### Exemple d'appel de méthode :
```java
int somme = addition(5, 10);
System.out.println(somme);  // Affiche 15
```

## 3. Surcharge de méthode

En Java, il est possible d'avoir plusieurs méthodes avec le même nom, à condition que le nombre ou le type de paramètres soit différent. C'est ce qu'on appelle la **surcharge de méthode**.

### Exemple de surcharge :
```java
public int addition(int a, int b) {
    return a + b;
}

public double addition(double a, double b) {
    return a + b;
}
```

Dans cet exemple, il y a deux méthodes `addition`, mais l'une accepte des entiers (`int`) et l'autre des nombres à virgule flottante (`double`).

## 4. Mot-clé `return`

Si une méthode doit renvoyer une valeur, on utilise le mot-clé `return` pour retourner cette valeur.

### Exemple :
```java
public String salutation(String nom) {
    return "Bonjour, " + nom;
}
```

Cette méthode `salutation` prend un nom en paramètre et renvoie un message de bienvenue.

## 5. Portée des variables

Les variables en Java ne sont accessibles que dans la région où elles sont créées, c'est-à-dire dans le bloc de code où elles sont définies. C'est ce qu'on appelle la **portée** des variables.

### Exemple de portée :
```java
public void exemple() {
    int x = 5; // x est accessible uniquement dans cette méthode
    if (x > 0) {
        int y = 10; // y est accessible uniquement dans ce bloc
    }
    // y n'est plus accessible ici
}
```
