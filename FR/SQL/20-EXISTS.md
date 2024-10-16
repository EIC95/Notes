# Opérateur EXISTS en SQL

L'opérateur `EXISTS` est utilisé pour tester la présence d'enregistrements dans une sous-requête. Il renvoie `TRUE` si la sous-requête retourne un ou plusieurs enregistrements, et `FALSE` sinon. Il est souvent utilisé pour vérifier la présence de données dans des tables liées.

## Syntaxe de EXISTS

```sql
SELECT colonne1, colonne2
FROM table
WHERE EXISTS (sous_requete);
```

## Exemple

Supposons que vous avez deux tables : `employes` et `departements`. Vous souhaitez trouver les départements qui ont au moins un employé. Vous pouvez utiliser `EXISTS` pour accomplir cela :

```sql
SELECT departement
FROM departements d
WHERE EXISTS (
    SELECT 1
    FROM employes e
    WHERE e.departement_id = d.id
);
```

Dans cet exemple :

- La sous-requête `SELECT 1 FROM employes e WHERE e.departement_id = d.id` vérifie s'il existe des employés dans chaque département.
- `EXISTS` renvoie `TRUE` si la sous-requête trouve des enregistrements pour le département courant, et `FALSE` sinon.
