# Clause WHERE en SQL

## Filtrage des Enregistrements

La clause `WHERE` est utilisée pour **filtrer les enregistrements** en extrayant uniquement ceux qui remplissent une condition spécifiée. Voici la syntaxe de base :

```sql
SELECT colonne1, colonne2, ...
FROM nom_table
WHERE condition;
```

### Exemples

- **Sélectionner les utilisateurs dont l'âge est supérieur à 30** :

  ```sql
  SELECT *
  FROM utilisateurs
  WHERE age > 30;
  ```