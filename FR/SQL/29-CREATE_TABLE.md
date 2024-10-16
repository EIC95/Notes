# Créer une Table

L'instruction **`CREATE TABLE`** est utilisée pour créer une nouvelle table dans une base de données SQL. Vous devez spécifier le nom de la table ainsi que les colonnes avec leurs types de données.

## Syntaxe

```sql
CREATE TABLE nom_de_la_table (
    nom_de_colonne1 type_de_donnee,
    nom_de_colonne2 type_de_donnee,
    ...
);
```

### Exemple

```sql
CREATE TABLE Clients (
    ID INT,
    Nom VARCHAR(100),
    Email VARCHAR(255),
    DateNaissance DATE
);
```

Cet exemple crée une table **`Clients`** avec quatre colonnes : **`ID`**, **`Nom`**, **`Email`**, et **`DateNaissance`**.

## Créer une Copie d'une Table Existant

Vous pouvez également créer une copie d'une table existante à l'aide de **`CREATE TABLE`**. Les structures et les données de la table existante seront dupliquées.

### Syntaxe

```sql
CREATE TABLE nouvelle_table AS
SELECT * FROM table_existante;
```

### Exemple

```sql
CREATE TABLE ClientsArchive AS
SELECT * FROM Clients;
```

Cette commande crée une nouvelle table **`ClientsArchive`** en copiant toutes les colonnes et les données de la table **`Clients`**.
