# Types de Données Date/Heure en SQL

SQL offre différents types de données pour stocker des valeurs de date et d'heure. Selon la base de données utilisée, il existe des variations dans le format et la gestion des dates.

## Types de Données en MySQL

- **DATE** : Stocke une date au format `AAAA-MM-JJ`.
- **DATETIME** : Stocke une date et une heure au format `AAAA-MM-JJ HH:MI:SS`.
- **TIMESTAMP** : Similaire à **DATETIME**, au format `AAAA-MM-JJ HH:MI:SS`. Il est également utilisé pour enregistrer automatiquement les dates de modification.
- **YEAR** : Stocke une année au format `AAAA` ou `AA`.

### Exemple MySQL

```sql
CREATE TABLE Evenements (
    id INT AUTO_INCREMENT,
    titre VARCHAR(255),
    date_event DATE,
    heure_event DATETIME,
    PRIMARY KEY (id)
);
```

## Types de Données en SQL Server

- **DATE** : Stocke une date au format `AAAA-MM-JJ`.
- **DATETIME** : Stocke une date et une heure au format `AAAA-MM-JJ HH:MI:SS`.
- **SMALLDATETIME** : Similaire à **DATETIME**, mais avec une précision moindre.
- **TIMESTAMP** : Stocke un numéro unique qui est mis à jour automatiquement à chaque modification de la ligne (différent du **TIMESTAMP** MySQL).

### Exemple SQL Server

```sql
CREATE TABLE Commandes (
    id INT PRIMARY KEY,
    date_commande DATE,
    heure_commande DATETIME
);
```

## Remarque

- Les types de données **DATE** et **DATETIME** sont définis lors de la création de la table.
- **Astuce** : Si les composants temporels ne sont pas nécessaires, il est recommandé de ne pas les utiliser afin de simplifier les requêtes.
