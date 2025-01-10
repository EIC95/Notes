# Fonction d'Agrégation AVG() en SQL

## Introduction

La fonction d'agrégation `AVG()` est utilisée pour calculer la valeur moyenne des valeurs d'une colonne numérique dans une table.

## Fonction AVG()

La fonction `AVG()` renvoie la moyenne des valeurs non NULL dans une colonne spécifiée.

### Syntaxe

```sql
SELECT AVG(colonne) AS nom_description
FROM nom_table
WHERE condition;
```

### Exemple

Pour obtenir la valeur moyenne des montants dans la colonne `montant` de la table `commandes` :

```sql
SELECT AVG(montant) AS moyenne_commandes
FROM commandes;
```

Pour obtenir la valeur moyenne des montants des commandes effectuées après le 1er janvier 2024 :

```sql
SELECT AVG(montant) AS moyenne_commandes_apres_2024
FROM commandes
WHERE date_commande > '2024-01-01';
```