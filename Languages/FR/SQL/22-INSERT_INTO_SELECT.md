# Instruction INSERT INTO SELECT en SQL

L'instruction `INSERT INTO SELECT` est utilisée pour copier des données d'une table existante et les insérer dans une autre table. Cette opération est utile pour transférer ou dupliquer des données entre tables. Il est important que les types de données des colonnes dans les tables source et cible correspondent pour éviter les erreurs lors de l'insertion.

## Syntaxe de INSERT INTO SELECT

```sql
INSERT INTO table_cible (colonne1, colonne2, ...)
SELECT colonne1, colonne2, ...
FROM table_source
WHERE condition;
```

## Exemple

Supposons que vous avez une table `clients_2023` contenant des informations sur les clients de 2023, et vous souhaitez copier ces informations dans la table `clients_archives` :

```sql
INSERT INTO clients_archives (nom, email, annee_achat)
SELECT nom, email, annee_achat
FROM clients_2023
WHERE annee_achat = 2023;
```

Dans cet exemple :

- `clients_archives` est la table cible où les données seront insérées.
- `SELECT nom, email, annee_achat FROM clients_2023` sélectionne les colonnes à copier depuis la table source `clients_2023`.
- La condition `WHERE annee_achat = 2023` filtre les données à insérer.