```markdown
# Instruction SELECT INTO en SQL

L'instruction `SELECT INTO` est utilisée pour créer une nouvelle table et y copier les données d'une table existante. Cette commande est utile lorsque vous souhaitez créer une table temporaire ou une table de sauvegarde contenant une sous-sélection des données.

## Syntaxe de SELECT INTO

```sql
SELECT colonne1, colonne2, ...
INTO nouvelle_table
FROM table_existante
WHERE condition;
```

## Exemple

Supposons que vous avez une table `clients` et que vous souhaitez créer une nouvelle table `clients_2024` contenant uniquement les clients ayant effectué des achats en 2024 :

```sql
SELECT *
INTO clients_2024
FROM clients
WHERE annee_achat = 2024;
```

Dans cet exemple :

- `clients_2024` est la nouvelle table qui sera créée.
- `SELECT *` copie toutes les colonnes de la table `clients`.
- La condition `WHERE annee_achat = 2024` filtre les enregistrements pour n'inclure que ceux dont l'année d'achat est 2024.

## Points Clés

- **Création de Table** : `SELECT INTO` crée une nouvelle table et y insère les données sélectionnées.
- **Copie de Données** : Les données de la table source sont copiées dans la nouvelle table.
- **Filtrage** : Vous pouvez utiliser des conditions pour filtrer les données copiées.
- **Non Réversible** : La table créée par `SELECT INTO` n'existe que si la commande est exécutée avec succès. Elle n'affecte pas la table source.

L'instruction `SELECT INTO` est particulièrement utile pour le traitement des données, les sauvegardes et la création de tables temporaires pour des analyses spécifiques.
```