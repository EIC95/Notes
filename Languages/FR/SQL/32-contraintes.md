# Les Contraintes en SQL

Les **contraintes** en SQL sont utilisées pour définir des règles sur les données des colonnes d'une table. Elles garantissent l'intégrité des données et permettent de contrôler ce qui peut ou ne peut pas être stocké dans les colonnes. Les contraintes peuvent être appliquées lors de la création de la table ou ajoutées après la création de la table via l'instruction **`ALTER TABLE`**.

## 1. NOT NULL

La contrainte **`NOT NULL`** garantit qu'une colonne ne peut pas avoir de valeur **`NULL`**.

### Exemple

```sql
CREATE TABLE Clients (
    id INT NOT NULL,
    nom VARCHAR(255) NOT NULL
);
```

Dans cet exemple, les colonnes **`id`** et **`nom`** ne peuvent pas être nulles.

## 2. UNIQUE

La contrainte **`UNIQUE`** garantit que toutes les valeurs dans une colonne sont uniques.

### Exemple

```sql
CREATE TABLE Utilisateurs (
    id INT NOT NULL,
    email VARCHAR(255) UNIQUE
);
```

La colonne **`email`** doit contenir des valeurs uniques pour chaque ligne.

## 3. PRIMARY KEY

La **clé primaire** (ou **`PRIMARY KEY`**) est une combinaison de **`NOT NULL`** et **`UNIQUE`**. Elle identifie de manière unique chaque enregistrement dans une table.

### Exemple

```sql
CREATE TABLE Commandes (
    commande_id INT PRIMARY KEY,
    produit VARCHAR(255) NOT NULL
);
```

Dans cet exemple, la colonne **`commande_id`** est une clé primaire et ne peut pas contenir de valeurs nulles ou dupliquées.

## 4. FOREIGN KEY

La contrainte **`FOREIGN KEY`** empêche les actions qui détruiraient les liens entre les tables. Elle assure l'intégrité référentielle.

### Exemple

```sql
CREATE TABLE Commandes (
    commande_id INT PRIMARY KEY,
    client_id INT,
    FOREIGN KEY (client_id) REFERENCES Clients(id)
);
```

La colonne **`client_id`** est une clé étrangère qui référence la colonne **`id`** de la table **`Clients`**.

## 5. CHECK

La contrainte **`CHECK`** garantit que les valeurs dans une colonne satisfont une condition spécifiée.

### Exemple

```sql
CREATE TABLE Employes (
    id INT PRIMARY KEY,
    age INT CHECK (age >= 18)
);
```

Cet exemple garantit que la colonne **`age`** ne contiendra que des valeurs supérieures ou égales à 18.

## 6. DEFAULT

La contrainte **`DEFAULT`** permet de définir une valeur par défaut pour une colonne si aucune valeur n'est fournie.

### Exemple

```sql
CREATE TABLE Produits (
    produit_id INT PRIMARY KEY,
    quantite INT DEFAULT 0
);
```

Si aucune valeur n'est spécifiée pour la colonne **`quantite`**, elle prendra la valeur par défaut de **`0`**.

## 7. CREATE INDEX

L'instruction **`CREATE INDEX`** est utilisée pour créer des index, qui permettent d'accélérer les opérations de recherche dans la base de données.

### Exemple

```sql
CREATE INDEX idx_nom ON Clients(nom);
```

Cet exemple crée un index sur la colonne **`nom`** de la table **`Clients`**, ce qui accélère les requêtes qui recherchent des données par le nom.
