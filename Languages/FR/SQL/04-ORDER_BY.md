# Mot-clé ORDER BY en SQL

## Trier les Résultats

Le mot-clé `ORDER BY` est utilisé pour **trier l’ensemble des résultats** d'une requête. Vous pouvez trier les enregistrements par ordre croissant ou décroissant.

### Syntaxe

```sql
SELECT colonne1, colonne2, ...
FROM nom_table
ORDER BY colonne1 [ASC|DESC], colonne2 [ASC|DESC], ...;
```

- **Ordre Croissant (ASC)** : C'est l'ordre par défaut. Les valeurs sont triées de la plus petite à la plus grande.
- **Ordre Décroissant (DESC)** : Les valeurs sont triées de la plus grande à la plus petite.

### Exemples

- **Trier les utilisateurs par âge en ordre croissant** :

  ```sql
  SELECT *
  FROM utilisateurs
  ORDER BY age ASC;
  ```

- **Trier les produits par prix en ordre décroissant** :

  ```sql
  SELECT *
  FROM produits
  ORDER BY prix DESC;
  ```

- **Trier les employés par département en ordre croissant puis par salaire en ordre décroissant** :

  ```sql
  SELECT *
  FROM employes
  ORDER BY departement ASC, salaire DESC;
  ```