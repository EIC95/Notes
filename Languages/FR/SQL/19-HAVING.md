# Clause HAVING en SQL

La clause `HAVING` est utilisée pour filtrer les résultats après que les groupes de données ont été formés par la clause `GROUP BY`. Contrairement à la clause `WHERE`, qui filtre les lignes avant l'agrégation, `HAVING` filtre les résultats regroupés en fonction des fonctions d'agrégation.

## Syntaxe de HAVING

```sql
SELECT colonne1, fonction_aggregation(colonne2)
FROM table
GROUP BY colonne1
HAVING condition_aggregation;
```

## Exemple

Supposons que vous avez une table `ventes` avec les colonnes `produit` et `montant`. Vous souhaitez trouver les produits pour lesquels le montant total des ventes dépasse 1000 unités. Vous pouvez utiliser `HAVING` pour filtrer les résultats après avoir calculé les totaux :

```sql
SELECT produit, SUM(montant) AS total_ventes
FROM ventes
GROUP BY produit
HAVING SUM(montant) > 1000;
```

Dans cet exemple :

- `GROUP BY` regroupe les lignes par produit.
- `SUM(montant)` calcule le total des ventes pour chaque produit.
- `HAVING SUM(montant) > 1000` filtre les groupes pour ne conserver que ceux dont le total des ventes dépasse 1000.
