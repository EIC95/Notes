# Chaînes de Caractères en Java

La classe `String` en Java offre de nombreuses méthodes utiles pour manipuler les chaînes de caractères.

## 1. Méthodes Communes de String
- `length()` : Renvoie la longueur de la chaîne.
- `substring(int beginIndex, int endIndex)` : Extrait une sous-chaîne.
- `equals(String anotherString)` : Compare deux chaînes pour vérifier l'égalité.
- `toUpperCase()` : Convertit la chaîne en majuscules.
- `concat(String str)` : Concatène deux chaînes.

### Exemple :
```java
String s = "Hello";
int len = s.length(); // 5
String sub = s.substring(0, 2); // "He"
boolean isEqual = s.equals("Hello"); // true
String upper = s.toUpperCase(); // "HELLO"
```

## 2. Caractères Spéciaux
Les chaînes en Java peuvent inclure des caractères spéciaux pour formater le texte.

| Caractère Spécial | Description                |
|-------------------|----------------------------|
| `\n`              | Nouvelle ligne             |
| `\t`              | Tabulation                 |
| `\\`              | Barre oblique inversée     |
| `\'`              | Apostrophe                 |
| `\"`              | Guillemets doubles         |
| `\r`              | Retour chariot             |
| `\b`              | Retour arrière             |
| `\f`              | Saut de page               |

### Exemple :
```java
String special = "Ligne1\nLigne2\tTabulation";
System.out.println(special);
// Résultat : 
// Ligne1
// Ligne2    Tabulation
```
