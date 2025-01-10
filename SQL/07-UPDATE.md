```markdown
# Instruction UPDATE en SQL

## Introduction

L'instruction `UPDATE` est utilisée pour modifier les enregistrements existants dans une table. Pour garantir que seuls les enregistrements désirés soient modifiés, il est crucial d'utiliser la clause `WHERE`.

## Syntaxe de l'Instruction UPDATE

```sql
UPDATE nom_table
SET colonne1 = valeur1, colonne2 = valeur2, ...
WHERE condition;
```

### Exemple

```sql
UPDATE clients
SET email = 'nouveau.email@example.com'
WHERE id = 1;
```

Cette requête met à jour l'adresse e-mail du client dont l'identifiant est `1`.

## Importance de la Clause WHERE

La clause `WHERE` est utilisée pour spécifier quel ou quels enregistrements doivent être mis à jour. Si vous omettez cette clause, tous les enregistrements de la table seront mis à jour, ce qui peut entraîner des modifications non désirées dans la base de données.

### Exemple Sans Clause WHERE

```sql
UPDATE clients
SET email = 'email@generique.com';
```

Cette requête mettra à jour l'adresse e-mail de tous les clients dans la table `clients`.