# Opérateur UNION en SQL

L'opérateur `UNION` est utilisé pour combiner les ensembles de résultats de deux ou plusieurs instructions `SELECT`. Il est important que chaque instruction `SELECT` ait le même nombre de colonnes avec des types de données similaires et dans le même ordre. Par défaut, `UNION` sélectionne uniquement des valeurs distinctes. Pour inclure les valeurs en double, utilisez `UNION ALL`.

## Syntaxe de UNION

```sql
SELECT colonne1, colonne2, ...
FROM table1
UNION
SELECT colonne1, colonne2, ...
FROM table2;
```

## Exemple

Supposons que vous avez deux tables, `clients` et `fournisseurs`, avec des colonnes similaires. Vous pouvez combiner les résultats de deux `SELECT` comme suit :

```sql
SELECT nom, ville
FROM clients
UNION
SELECT nom, ville
FROM fournisseurs;
```

Ce code combine les résultats de la table `clients` et de la table `fournisseurs` tout en supprimant les doublons.

## UNION ALL

Si vous souhaitez inclure toutes les valeurs, y compris les doublons, utilisez `UNION ALL` :

```sql
SELECT nom, ville
FROM clients
UNION ALL
SELECT nom, ville
FROM fournisseurs;
```
