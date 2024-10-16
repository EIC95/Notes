# Structures Conditionnelles en Java

Java offre plusieurs façons de gérer les conditions dans votre programme. Voici les principales structures conditionnelles :

## 1. If

L'instruction `if` permet d'exécuter un bloc de code si une condition est remplie.

### Exemple :
```java
int a = 10;
if (a > 5) {
    System.out.println("a est supérieur à 5");
}
```

## 2. If...Else

La structure `if...else` permet d'exécuter un bloc de code si la condition est vraie, et un autre bloc si la condition est fausse.

### Exemple :
```java
int a = 10;
if (a > 5) {
    System.out.println("a est supérieur à 5");
} else {
    System.out.println("a est inférieur ou égal à 5");
}
```

## 3. If...Else If...Else

Cette structure est utilisée pour tester plusieurs conditions dans l'ordre.

### Exemple :
```java
int a = 10;
if (a > 10) {
    System.out.println("a est supérieur à 10");
} else if (a == 10) {
    System.out.println("a est égal à 10");
} else {
    System.out.println("a est inférieur à 10");
}
```

## 4. Opérateur Ternaire

L'opérateur ternaire est une version condensée de l'instruction `if...else`. Il prend la forme :
```java
condition ? valeur_si_vrai : valeur_si_faux;
```

### Exemple :
```java
int a = 10;
String result = (a > 5) ? "a est supérieur à 5" : "a est inférieur ou égal à 5";
System.out.println(result);
```

## 5. Switch Case

La structure `switch` permet de sélectionner l'une des nombreuses options possibles, basée sur la valeur d'une variable.

### Exemple :
```java
int day = 2;
switch (day) {
    case 1:
        System.out.println("Lundi");
        break;
    case 2:
        System.out.println("Mardi");
        break;
    case 3:
        System.out.println("Mercredi");
        break;
    default:
        System.out.println("Jour inconnu");
        break;
}
```

Le `switch` compare la variable à chaque `case` et exécute le code du bloc correspondant. Le mot clé `break` est utilisé pour sortir de la structure `switch` une fois qu'un cas est exécuté.
