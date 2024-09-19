# Les Vues en SQL

Une vue est une table virtuelle qui représente le résultat d'une instruction SQL. Contrairement aux tables physiques, les vues ne stockent pas de données elles-mêmes, mais affichent les données d'une ou plusieurs tables réelles selon la requête définie.

## Création d'une Vue

Pour créer une vue, vous utilisez l'instruction `CREATE VIEW`. Une vue peut inclure des colonnes provenant de différentes tables et peut également intégrer des instructions et des fonctions SQL pour manipuler les données.

### Syntaxe de Base

```sql
CREATE VIEW nom_vue AS
SELECT colonne1, colonne2, ...
FROM table1
JOIN table2 ON condition
WHERE condition;
```

### Exemple

Imaginons que vous ayez deux tables : `Employes` et `Departements`. Vous souhaitez créer une vue qui affiche les noms des employés et leurs départements respectifs.

```sql
CREATE VIEW VueEmployesDepartements AS
SELECT Employes.nom, Departements.nom_departement
FROM Employes
JOIN Departements ON Employes.departement_id = Departements.id;
```

Dans cet exemple, `VueEmployesDepartements` est une vue qui combine les données des tables `Employes` et `Departements` pour fournir une vue consolidée.

## Utilisation des Vues

Les vues peuvent être utilisées comme des tables dans les requêtes SQL. Vous pouvez sélectionner, filtrer et trier les données à partir d'une vue de la même manière que vous le feriez avec une table physique.

### Exemple d'Utilisation

```sql
SELECT *
FROM VueEmployesDepartements
WHERE nom_departement = 'Informatique';
```