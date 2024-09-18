# Les Packages en Java

En Java, un **package** est utilisé pour organiser les classes associées en groupes logiques. Il s'agit essentiellement d'un dossier qui regroupe des classes similaires. Les packages permettent d'éviter les conflits de noms (en particulier lors de l'utilisation de classes de différentes bibliothèques) et facilitent la maintenance du code.

## Types de Packages

1. **Packages intégrés** : Ceux qui font partie de l'API Java, disponibles gratuitement pour les développeurs.
2. **Packages définis par l'utilisateur** : Ce sont des packages que vous créez pour organiser vos propres classes.

### Packages Intégrés (API Java)

L'API Java contient une multitude de classes et packages préécrits que vous pouvez utiliser dans vos programmes. Ces packages couvrent divers aspects, notamment la gestion des entrées, la programmation réseau, les bases de données, et plus encore.

Pour utiliser une classe ou un package de l'API Java, vous devez l'importer à l'aide du mot-clé `import` :

```java
import java.util.Scanner;
```

Ici, vous importez la classe `Scanner` du package `java.util`. Vous pouvez aussi importer un package entier :

```java
import java.util.*;
```

Cela inclut toutes les classes du package `java.util`.

### Packages Définis par l'Utilisateur

Vous pouvez également créer vos propres packages pour organiser vos classes de manière logique et éviter les conflits de noms. Cela se fait avec le mot-clé `package`.

### Exemple de Création d'un Package

```java
package mypack;

public class MyPackageClass {
    public static void main(String[] args) {
        System.out.println("Bienvenue dans mon package !");
    }
}
```

- Le mot-clé `package` doit toujours être la première instruction dans votre fichier source Java.
- Enregistrez ce fichier sous le nom `MyPackageClass.java`.

### Compilation et Exécution du Package

Lorsque vous compilez ce fichier, vous devez indiquer au compilateur où enregistrer le fichier de classe compilé avec l'option `-d` :

```bash
javac -d . MyPackageClass.java
```

Cela crée un dossier **mypack** dans le répertoire actuel et y place la classe compilée.

Pour exécuter le fichier, vous devez spécifier le nom complet de la classe (c'est-à-dire le nom du package suivi du nom de la classe) :

```bash
java mypack.MyPackageClass
```

### Remarque : 
Le nom du package doit être écrit en **minuscules** pour éviter tout conflit avec les noms de classes, qui commencent souvent par une majuscule.
