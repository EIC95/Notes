# Supprimer une Table ou des Données

En SQL, il existe plusieurs méthodes pour supprimer une table ou les données qu'elle contient.

## 1. Supprimer une Table

L'instruction **`DROP TABLE`** est utilisée pour supprimer une table existante ainsi que toutes les données qu'elle contient.

### Syntaxe

```sql
DROP TABLE nom_de_la_table;
```

### Exemple

```sql
DROP TABLE Clients;
```

Cet exemple supprime la table **`Clients`** et toutes ses données de la base de données.

### Points Clés

- **`DROP TABLE`** supprime complètement la table de la base de données.
- Toutes les données et la structure de la table sont définitivement perdues.

## 2. Supprimer les Données d'une Table

L'instruction **`TRUNCATE TABLE`** est utilisée pour supprimer toutes les lignes d'une table, mais sans supprimer la table elle-même. La structure de la table reste intacte.

### Syntaxe

```sql
TRUNCATE TABLE nom_de_la_table;
```

### Exemple

```sql
TRUNCATE TABLE Clients;
```

Cet exemple supprime toutes les données de la table **`Clients`**, mais conserve la table pour une utilisation future.

### Différences entre `DROP TABLE` et `TRUNCATE TABLE`

| **Opération**      | **`DROP TABLE`**                | **`TRUNCATE TABLE`**              |
|--------------------|---------------------------------|-----------------------------------|
| Supprime la table  | Oui                             | Non                              |
| Supprime les données | Oui                             | Oui                              |
| Peut être annulée  | Non                             | Non                              |
| Conserve la structure | Non                             | Oui                              |
