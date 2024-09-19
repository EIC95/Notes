# Utilisation des Alias en SQL

## Introduction

Les alias SQL sont utilisés pour attribuer des noms temporaires à des tables ou des colonnes pour la durée d'une requête. Les alias rendent les noms de colonnes et de tables plus lisibles et facilitent la rédaction des requêtes, notamment lorsqu'il s'agit de jointures ou de sous-requêtes complexes.

## Création d'un Alias

Les alias sont créés en utilisant le mot-clé `AS`. Cependant, dans de nombreux systèmes de bases de données, le mot-clé `AS` est optionnel et peut être omis. Vous pouvez également utiliser des guillemets (`""`) ou des crochets (`[]`) pour encadrer le nom de l'alias dans certaines bases de données.

### Syntaxe

#### Avec `AS`

```sql
SELECT colonne AS alias
FROM table;
```

#### Sans `AS`

```sql
SELECT colonne alias
FROM table;
```

### Exemple de Création d'Alias

1. **Alias pour une Colonne**

   Donne un nom plus lisible à une colonne dans la sortie de la requête.

   ```sql
   SELECT nom AS nom_client
   FROM clients;
   ```

   Ou sans `AS` :

   ```sql
   SELECT nom nom_client
   FROM clients;
   ```

2. **Alias pour une Table**

   Utilisé pour simplifier les jointures et les références aux tables.

   ```sql
   SELECT c.nom, o.date_commande
   FROM clients AS c
   INNER JOIN commandes AS o ON c.id_client = o.id_client;
   ```

   Ou sans `AS` :

   ```sql
   SELECT c.nom, o.date_commande
   FROM clients c
   INNER JOIN commandes o ON c.id_client = o.id_client;
   ```

3. **Utilisation des Guillemets ou Crochets**

   Certains systèmes de bases de données comme SQL Server permettent l'utilisation de crochets ou guillemets pour encadrer les alias.

   ```sql
   SELECT nom AS [Nom du Client]
   FROM clients;
   ```

   Ou avec des guillemets :

   ```sql
   SELECT nom AS "Nom du Client"
   FROM clients;
   ```
