# Tableaux en Java

En Java, un tableau est une structure de données qui permet de stocker plusieurs valeurs du même type. Voici comment déclarer et utiliser des tableaux en Java :

## 1. Déclaration d'un tableau

Pour déclarer un tableau, vous devez définir le type de variable suivi de crochets `[]`, puis initialiser le tableau avec des valeurs ou une taille fixe.

### Exemple de déclaration :
```java
int[] nombres = {1, 2, 3, 4, 5};
```

Dans cet exemple, le tableau `nombres` contient 5 éléments. Vous pouvez accéder à un élément du tableau en utilisant son index (commençant par 0).

## 2. Propriété `length`

La propriété `length` d'un tableau permet de connaître le nombre d'éléments qu'il contient.

### Exemple :
```java
System.out.println("Taille du tableau : " + nombres.length);
```

Cela affichera la taille du tableau, qui est 5 dans cet exemple.

## 3. Tableaux à deux dimensions

En Java, un tableau à deux dimensions est un tableau de tableaux. Pour déclarer un tableau à deux dimensions, vous devez ajouter un deuxième ensemble de crochets `[][]`.

### Exemple :
```java
int[][] matrice = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

Ici, `matrice` est un tableau à deux dimensions contenant trois tableaux de trois éléments. Vous pouvez accéder à un élément spécifique en utilisant deux indices : un pour la ligne et un pour la colonne.

### Accéder à un élément d'un tableau 2D :
```java
System.out.println(matrice[1][2]); // Affiche 6
```

Ce code accède à l'élément de la deuxième ligne et troisième colonne, qui est `6`.
