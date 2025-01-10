# Fonctions d'Agrégation MIN() et MAX() en SQL

## Introduction

Les fonctions d'agrégation `MIN()` et `MAX()` sont utilisées pour obtenir la valeur minimale et maximale d'une colonne dans une table. Ces fonctions sont particulièrement utiles pour résumer des données numériques ou chronologiques.

## Fonction MIN()

La fonction `MIN()` renvoie la plus petite valeur d'une colonne sélectionnée.

### Syntaxe

```sql
SELECT MIN(colonne) AS nom_description
FROM nom_table;
```

### Exemple

Pour obtenir la plus petite valeur de la colonne `prix` dans la table `produits`, vous pouvez utiliser :

```sql
SELECT MIN(prix) AS prix_minimum
FROM produits;
```

## Fonction MAX()

La fonction `MAX()` renvoie la plus grande valeur d'une colonne sélectionnée.

### Syntaxe

```sql
SELECT MAX(colonne) AS nom_description
FROM nom_table;
```

### Exemple

Pour obtenir la plus grande valeur de la colonne `prix` dans la table `produits`, vous pouvez utiliser :

```sql
SELECT MAX(prix) AS prix_maximum
FROM produits;
```
