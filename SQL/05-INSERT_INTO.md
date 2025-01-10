# Instruction INSERT INTO en SQL

## Introduction

L'instruction `INSERT INTO` est utilisée pour **insérer de nouveaux enregistrements** dans une table. Vous pouvez rédiger la déclaration `INSERT INTO` de deux manières différentes.

## Méthode 1 : Spécification des Colonnes

Cette méthode permet d'insérer des valeurs dans des colonnes spécifiques de la table.

### Syntaxe

```sql
INSERT INTO nom_table (colonne1, colonne2, colonne3, ...)
VALUES (valeur1, valeur2, valeur3, ...);
```

### Exemple

```sql
INSERT INTO clients (nom, email, age)
VALUES ('Jean Dupont', 'jean.dupont@example.com', 30);
```

## Méthode 2 : Sans Spécification des Colonnes

Cette méthode permet d'insérer des valeurs dans toutes les colonnes de la table, dans l'ordre où elles ont été définies dans la table.

### Syntaxe

```sql
INSERT INTO nom_table
VALUES (valeur1, valeur2, valeur3, ...);
```

### Exemple

```sql
INSERT INTO clients
VALUES (1, 'Jean Dupont', 'jean.dupont@example.com', 30);
```

**Remarque** : Lorsque vous utilisez la deuxième méthode, assurez-vous que l'ordre des valeurs correspond à l'ordre des colonnes dans la table et que toutes les colonnes non nulles sont fournies avec des valeurs.
