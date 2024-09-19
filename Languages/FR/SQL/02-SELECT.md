# Instructions SELECT en SQL

## Sélection de Données

L'instruction `SELECT` est utilisée pour **sélectionner des données** dans une base de données. Voici la syntaxe de base pour sélectionner des colonnes spécifiques :

```sql
SELECT colonne1, colonne2, ...
FROM nom_table;
```

### Sélection de Toutes les Colonnes

Si vous souhaitez **renvoyer toutes les colonnes** sans avoir à spécifier chaque nom de colonne, utilisez l'astérisque (*) :

```sql
SELECT * 
FROM nom_table;
```

Cela sélectionne toutes les colonnes de la table spécifiée.

## Valeurs Distinctes

Dans une table, une colonne peut contenir de nombreuses valeurs en double. Pour **répertorier uniquement les valeurs distinctes** dans une colonne, utilisez l'instruction `SELECT DISTINCT` :

```sql
SELECT DISTINCT colonne
FROM nom_table;
```

Cela renvoie uniquement les valeurs uniques pour la colonne spécifiée, éliminant les doublons.

### Exemples

- **Sélectionner toutes les colonnes de la table `utilisateurs`** :

  ```sql
  SELECT * 
  FROM utilisateurs;
  ```

- **Sélectionner uniquement les noms uniques des utilisateurs** :

  ```sql
  SELECT DISTINCT nom 
  FROM utilisateurs;
  ```