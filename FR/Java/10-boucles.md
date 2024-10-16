# Boucles en Java

Les boucles sont utilisées pour répéter l'exécution d'un bloc de code tant qu'une condition est remplie. Voici les principales boucles en Java :

## 1. While

La boucle `while` continue d'exécuter le bloc de code tant que la condition spécifiée est vraie.

### Exemple :
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

Dans cet exemple, la boucle affichera les valeurs de 0 à 4 tant que `i` est inférieur à 5.

## 2. Do While

La boucle `do...while` est similaire à la boucle `while`, mais le bloc de code est exécuté au moins une fois, même si la condition est fausse dès le départ.

### Exemple :
```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```

Ici, la boucle s'exécutera et affichera 0 à 4, même si la condition est vérifiée après l'exécution du bloc.

## 3. For

La boucle `for` est utilisée lorsqu'on connaît le nombre d'itérations à l'avance.

### Exemple :
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

Cette boucle affichera également les valeurs de 0 à 4. La structure de la boucle `for` inclut l'initialisation, la condition et l'incrémentation dans une seule ligne.

## 4. For-Each

La boucle `for-each` est utilisée spécifiquement pour parcourir les éléments d'un tableau ou d'une collection.

### Exemple :
```java
String[] fruits = {"Pomme", "Banane", "Orange"};
for (String fruit : fruits) {
    System.out.println(fruit);
}
```

La boucle `for-each` parcourt chaque élément du tableau `fruits` et l'affiche. Cette boucle est pratique lorsque vous travaillez avec des collections ou des tableaux sans avoir besoin de gérer manuellement les indices.
