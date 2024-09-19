# Fonction d'Agrégation SUM() en SQL

## Introduction

La fonction d'agrégation `SUM()` est utilisée pour calculer la somme totale des valeurs d'une colonne numérique dans une table.

## Fonction SUM()

La fonction `SUM()` renvoie la somme totale de toutes les valeurs non NULL dans une colonne spécifiée.

### Syntaxe

```sql
SELECT SUM(colonne) AS nom_description
FROM nom_table
WHERE condition;
```

### Exemple

Pour obtenir la somme totale des valeurs dans la colonne `montant` de la table `commandes` :

```sql
SELECT SUM(montant) AS total_commandes
FROM commandes;
```

Pour obtenir la somme des montants des commandes effectuées après le 1er janvier 2024 :

```sql
SELECT SUM(montant) AS total_commandes_apres_2024
FROM commandes
WHERE date_commande > '2024-01-01';
```