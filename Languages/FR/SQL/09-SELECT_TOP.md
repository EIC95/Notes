# Clause SELECT TOP en SQL

## Introduction

La clause `SELECT TOP` est utilisée pour spécifier le nombre d'enregistrements à renvoyer à partir d'une requête. Elle est particulièrement utile lorsque vous travaillez avec de grandes tables contenant des milliers d'enregistrements et que vous souhaitez limiter le nombre de résultats retournés.

## Syntaxe de la Clause SELECT TOP

La syntaxe de `SELECT TOP` peut varier en fonction du système de gestion de base de données (SGBD) que vous utilisez.

### Exemple pour SQL Server

```sql
SELECT TOP (nombre) colonne1, colonne2, ...
FROM nom_table;
```

**Exemple** : Pour obtenir les 5 premiers enregistrements de la table `clients` :

```sql
SELECT TOP (5) *
FROM clients;
```

### Exemple pour MySQL et PostgreSQL

Pour MySQL et PostgreSQL, la syntaxe utilise la clause `LIMIT` :

```sql
SELECT colonne1, colonne2, ...
FROM nom_table
LIMIT nombre;
```

**Exemple** : Pour obtenir les 5 premiers enregistrements de la table `clients` :

```sql
SELECT *
FROM clients
LIMIT 5;
```

### Exemple pour Oracle

Pour Oracle, vous utilisez la clause `ROWNUM` ou la fonction `FETCH FIRST` :

```sql
SELECT colonne1, colonne2, ...
FROM nom_table
WHERE ROWNUM <= nombre;
```

**Exemple** : Pour obtenir les 5 premiers enregistrements de la table `clients` :

```sql
SELECT *
FROM clients
WHERE ROWNUM <= 5;
```

Ou avec `FETCH FIRST` (Oracle 12c et versions ultérieures) :

```sql
SELECT *
FROM clients
FETCH FIRST nombre ROWS ONLY;
```

**Exemple** : 

```sql
SELECT *
FROM clients
FETCH FIRST 5 ROWS ONLY;
```
