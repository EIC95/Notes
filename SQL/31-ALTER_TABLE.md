# Modifier une Table Existante avec ALTER TABLE

L'instruction **`ALTER TABLE`** en SQL permet d'apporter des modifications à une table existante. Elle peut être utilisée pour ajouter, supprimer ou modifier des colonnes, ainsi que pour définir ou supprimer des contraintes sur des colonnes.

## 1. Ajouter une Colonne

L'instruction **`ALTER TABLE`** peut ajouter une nouvelle colonne dans une table existante.

### Syntaxe

```sql
ALTER TABLE nom_de_la_table
ADD nom_de_la_colonne type_de_donnee;
```

### Exemple

```sql
ALTER TABLE Clients
ADD age INT;
```

Cet exemple ajoute une colonne **`age`** de type **`INT`** à la table **`Clients`**.

## 2. Supprimer une Colonne

L'instruction **`ALTER TABLE`** peut également supprimer une colonne existante.

### Syntaxe

```sql
ALTER TABLE nom_de_la_table
DROP COLUMN nom_de_la_colonne;
```

### Exemple

```sql
ALTER TABLE Clients
DROP COLUMN age;
```

Cet exemple supprime la colonne **`age`** de la table **`Clients`**.

## 3. Modifier une Colonne

Il est aussi possible de modifier une colonne existante, que ce soit pour changer son type de données ou pour renommer la colonne.

### Modifier le Type de Donnée

```sql
ALTER TABLE nom_de_la_table
MODIFY COLUMN nom_de_la_colonne nouveau_type_de_donnee;
```

### Exemple

```sql
ALTER TABLE Clients
MODIFY COLUMN age VARCHAR(3);
```

Cet exemple modifie le type de données de la colonne **`age`** pour qu'elle devienne un **`VARCHAR(3)`**.

### Renommer une Colonne

```sql
ALTER TABLE nom_de_la_table
RENAME COLUMN ancien_nom TO nouveau_nom;
```

### Exemple

```sql
ALTER TABLE Clients
RENAME COLUMN age TO age_client;
```

Cet exemple renomme la colonne **`age`** en **`age_client`**.
