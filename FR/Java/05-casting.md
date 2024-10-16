# Conversion de Types (Casting)

En Java, il existe deux types de **casting** :

## 1. Conversion par élargissement (Widening Casting)
C'est la conversion automatique d'un type de plus petite taille en un type de plus grande taille. Ce type de casting ne nécessite aucune intervention manuelle.

**Ordre des types :**
`byte -> short -> char -> int -> long -> float -> double`

### Exemple de conversion par élargissement :

```java
int a = 10;
double b = a;  // Conversion automatique de int à double
System.out.println(b);  // Affiche 10.0
```

## 2. Conversion par rétrécissement (Narrowing Casting)
C'est la conversion manuelle d'un type de plus grande taille en un type de plus petite taille. Ce type de casting doit être effectué explicitement par le programmeur.

**Ordre des types :**
`double -> float -> long -> int -> char -> short -> byte`

### Exemple de conversion par rétrécissement :

```java
double x = 10.5;
int y = (int) x;  // Conversion explicite de double à int
System.out.println(y);  // Affiche 10
```