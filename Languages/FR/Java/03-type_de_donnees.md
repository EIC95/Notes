# Types de données

En Java, les types de données se divisent en deux catégories : **primitifs** et **références (objets)**. 

- **Types primitifs** : Ils sont prédéfinis et ont toujours une valeur. Ils commencent toujours par une lettre **minuscule**.
- **Types de référence** : Ce sont des objets créés par les programmeurs. Ils peuvent être **null** et commencent par une lettre **majuscule**. Ces types incluent les **Strings**, les **tableaux**, les **classes** et les **interfaces**, et permettent d'appeler des méthodes pour effectuer des opérations.

## Liste des types primitifs :

| Type     | Bits | Exemple             | Lettre (si nécessaire) |
|----------|------|---------------------|------------------------|
| `byte`   | 8    | `byte b = 10;`       | -                      |
| `short`  | 16   | `short s = 1000;`    | -                      |
| `int`    | 32   | `int i = 100000;`    | -                      |
| `long`   | 64   | `long l = 100000L;`  | `L`                    |
| `float`  | 32   | `float f = 10.5F;`   | `F`                    |
| `double` | 64   | `double d = 10.5;`   | `D` (optionnel)        |
| `char`   | 16   | `char c = 'A';`      | -                      |
| `boolean`| 1    | `boolean flag = true;`| -                      |
| `String` | -    | `String s = "Hello";`| -                      |

## Exemple :
```java
public class Main {
    public static void main(String[] args) {
        int i = 100000;
        float f = 10.5F;
        boolean flag = true;
        String s = "Hello";
        
        System.out.println(i);   // 100000
        System.out.println(f);   // 10.5
        System.out.println(flag);// true
        System.out.println(s);   // Hello
    }
}
```