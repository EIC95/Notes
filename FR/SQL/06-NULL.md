# Gestion des Valeurs NULL en SQL

## Introduction

En SQL, un champ avec une valeur `NULL` représente un champ sans valeur. Pour tester si un champ est `NULL` ou non, vous devez utiliser les opérateurs `IS NULL` et `IS NOT NULL`.

## Opérateur IS NULL

L'opérateur `IS NULL` est utilisé pour vérifier si une colonne a une valeur `NULL`.

### Syntaxe

```sql
SELECT colonne1, colonne2
FROM nom_table
WHERE colonne1 IS NULL;
```

### Exemple

```sql
SELECT nom, email
FROM clients
WHERE email IS NULL;
```

Ce requête sélectionne les noms et les e-mails des clients pour lesquels l'adresse e-mail est `NULL`.

## Opérateur IS NOT NULL

L'opérateur `IS NOT NULL` est utilisé pour vérifier si une colonne n'a pas de valeur `NULL`.

### Syntaxe

```sql
SELECT colonne1, colonne2
FROM nom_table
WHERE colonne1 IS NOT NULL;
```

### Exemple

```sql
SELECT nom, email
FROM clients
WHERE email IS NOT NULL;
```

Cette requête sélectionne les noms et les e-mails des clients pour lesquels l'adresse e-mail n'est pas `NULL`.
