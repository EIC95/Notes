# Instruction GROUP BY en SQL

L'instruction `GROUP BY` est utilisée pour regrouper les lignes ayant les mêmes valeurs en lignes récapitulatives. Elle permet d'agréger les données par une ou plusieurs colonnes et est souvent utilisée en combinaison avec des fonctions d'agrégation telles que `COUNT()`, `MAX()`, `MIN()`, `SUM()`, et `AVG()` pour produire des résultats récapitulatifs.

## Syntaxe de GROUP BY

```sql
SELECT colonne1, fonction_aggregation(colonne2)
FROM table
GROUP BY colonne1;
```

## Exemple

Supposons que vous avez une table `clients` avec les colonnes `pays` et `id_client`. Vous souhaitez trouver le nombre de clients dans chaque pays. Vous pouvez utiliser `GROUP BY` avec la fonction d'agrégation `COUNT()` :

```sql
SELECT pays, COUNT(id_client) AS nombre_clients
FROM clients
GROUP BY pays;
```

Ce code regroupe les clients par pays et affiche le nombre total de clients dans chaque pays.

## Utilisation avec plusieurs Colonnes

Vous pouvez également regrouper par plusieurs colonnes. Par exemple, pour obtenir le nombre de clients par pays et par ville :

```sql
SELECT pays, ville, COUNT(id_client) AS nombre_clients
FROM clients
GROUP BY pays, ville;
```