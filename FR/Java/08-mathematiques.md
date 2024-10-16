# Classe Math en Java

La classe `Math` de Java (`java.lang.Math`) fournit des méthodes pour effectuer des opérations mathématiques courantes.

## Méthodes de Math

- `max(x, y)` : Renvoie le plus grand des deux nombres `x` et `y`.
- `min(x, y)` : Renvoie le plus petit des deux nombres `x` et `y`.
- `sqrt(x)` : Renvoie la racine carrée de `x`.
- `pow(x, y)` : Renvoie `x` élevé à la puissance `y`.
- `exp(x)` : Renvoie `e` élevé à la puissance `x`.
- `log(x)` : Renvoie le logarithme naturel (base `e`) de `x`.
- `log10(x)` : Renvoie le logarithme en base 10 de `x`.
- `sin(x)`, `cos(x)`, `tan(x)` : Renvoie le sinus, cosinus ou tangente de `x` (en radians).

### Exemple :
```java
double a = 16;
double b = 4;
double maxVal = Math.max(a, b); // 16.0
double sqrtVal = Math.sqrt(a); // 4.0
double powVal = Math.pow(a, b); // 65536.0
double expVal = Math.exp(1); // 2.718281828459045
double logVal = Math.log(a); // 2.772588722239781
double log10Val = Math.log10(a); // 1.20411998265592
double sinVal = Math.sin(Math.PI / 2); // 1.0
```
