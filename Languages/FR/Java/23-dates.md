# Gestion des Dates et Heures en Java

En Java, il n'existe pas de classe **Date** intégrée dans le langage, mais il est possible de manipuler des dates et des heures grâce au package `java.time`. Ce package offre une **API de date et d'heure** complète et intuitive.

## Importation du package `java.time`

Pour utiliser les classes liées à la gestion des dates et heures, vous devez importer les classes suivantes :
- `LocalDate`: pour travailler avec des dates.
- `LocalTime`: pour travailler avec des heures.
- `LocalDateTime`: pour combiner des dates et des heures.
- `DateTimeFormatter`: pour formater et personnaliser l'affichage des dates et heures.

### Exemple d'utilisation de la méthode `now()`

La méthode `now()` permet de récupérer l'heure et la date actuelles.

```java
import java.time.LocalDate;
import java.time.LocalTime;
import java.time.LocalDateTime;

public class Main {
    public static void main(String[] args) {
        LocalDate currentDate = LocalDate.now();    // Récupère la date actuelle
        LocalTime currentTime = LocalTime.now();    // Récupère l'heure actuelle
        LocalDateTime currentDateTime = LocalDateTime.now(); // Récupère la date et l'heure actuelles

        System.out.println("Date actuelle : " + currentDate);
        System.out.println("Heure actuelle : " + currentTime);
        System.out.println("Date et heure actuelles : " + currentDateTime);
    }
}
```

### Formatage des Dates et Heures avec `DateTimeFormatter`

En Java, le **formatage** des dates et heures peut être personnalisé grâce à la classe `DateTimeFormatter`. Cette classe permet de **définir un modèle spécifique** pour formater les dates et heures.

#### Exemple de formatage :

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Main {
    public static void main(String[] args) {
        LocalDateTime now = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");

        String formattedDateTime = now.format(formatter);
        System.out.println("Date et heure formatées : " + formattedDateTime);
    }
}
```

### Modèles de Formatage :

| Modèle          | Exemple            |
|-----------------|--------------------|
| `yyyy-MM-dd`    | "1988-09-29"       |
| `dd/MM/yyyy`    | "29/09/1988"       |
| `dd-MMM-yyyy`   | "29-Sep-1988"      |
| `E, MMM dd yyyy`| "Thu, Sep 29 1988" |

#### Exemple avec différents formats :

```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class Main {
    public static void main(String[] args) {
        LocalDate myBirthday = LocalDate.of(1988, 9, 29);

        // Formatages différents
        DateTimeFormatter formatter1 = DateTimeFormatter.ofPattern("yyyy-MM-dd");
        DateTimeFormatter formatter2 = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        DateTimeFormatter formatter3 = DateTimeFormatter.ofPattern("dd-MMM-yyyy");
        DateTimeFormatter formatter4 = DateTimeFormatter.ofPattern("E, MMM dd yyyy");

        System.out.println("Format 1 : " + myBirthday.format(formatter1));
        System.out.println("Format 2 : " + myBirthday.format(formatter2));
        System.out.println("Format 3 : " + myBirthday.format(formatter3));
        System.out.println("Format 4 : " + myBirthday.format(formatter4));
    }
}
```