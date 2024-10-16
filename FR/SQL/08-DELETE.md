# Instruction DELETE en SQL

## Introduction

L'instruction `DELETE` est utilisée pour supprimer les enregistrements existants dans une table. Pour éviter de supprimer des données non souhaitées, il est crucial d'utiliser la clause `WHERE` pour spécifier les enregistrements à supprimer.

## Syntaxe de l'Instruction DELETE

```sql
DELETE FROM nom_table
WHERE condition;
```

### Exemple

```sql
DELETE FROM clients
WHERE id = 1;
```

Cette requête supprime l'enregistrement du client dont l'identifiant est `1`.

## Importance de la Clause WHERE

La clause `WHERE` est utilisée pour déterminer quels enregistrements doivent être supprimés. Si cette clause est omise, tous les enregistrements de la table seront supprimés, ce qui peut entraîner une perte de données importante et irréversible.

### Exemple Sans Clause WHERE

```sql
DELETE FROM clients;
```

Cette requête supprime tous les enregistrements de la table `clients`.
