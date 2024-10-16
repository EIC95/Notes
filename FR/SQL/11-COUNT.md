# Fonction d'Agrégation COUNT() en SQL

## Introduction

La fonction d'agrégation `COUNT()` est utilisée pour obtenir le nombre de lignes correspondant à un critère spécifié dans une table. Elle ne compte pas les valeurs NULL.

## Fonction COUNT()

La fonction `COUNT()` renvoie le nombre de lignes dans une table ou le nombre de lignes qui répondent à une condition donnée.

### Syntaxe

```sql
SELECT COUNT(colonne) AS nom_description
FROM nom_table
WHERE condition;
```

### Exemple

Pour obtenir le nombre total d'enregistrements dans la table `clients` :

```sql
SELECT COUNT(*) AS nombre_clients
FROM clients;
```

Pour obtenir le nombre d'enregistrements où la colonne `age` est supérieure à 30 :

```sql
SELECT COUNT(age) AS nombre_clients_age_superieur_30
FROM clients
WHERE age > 30;
```