# L'Incrémentation Automatique en SQL

L'incrémentation automatique permet de générer automatiquement un numéro unique pour chaque nouvel enregistrement inséré dans une table. Cette fonctionnalité est souvent utilisée pour les colonnes de **clé primaire**, où un identifiant unique est nécessaire.

### Fonctionnement

Lorsque l'incrémentation automatique est activée sur une colonne, vous n'avez pas besoin de fournir de valeur pour cette colonne lors de l'insertion d'un nouvel enregistrement. La base de données générera automatiquement un nombre unique, généralement en commençant à **1** et en l'incrémentant de **1** pour chaque nouvel enregistrement.

### Syntaxe Selon les Bases de Données

- **MySQL / SQL Server** : Utilise **`AUTO_INCREMENT`**.
- **PostgreSQL** : Utilise **`SERIAL`**.
- **Oracle** : Utilise les **`SEQUENCES`**.
- **MS Access** : Utilise **`AUTONUMBER`**.

## 1. MySQL / SQL Server - AUTO_INCREMENT

En MySQL et SQL Server, la colonne incrémentée est définie avec l'attribut **`AUTO_INCREMENT`**.

### Exemple

```sql
CREATE TABLE Clients (
    client_id INT AUTO_INCREMENT,
    nom VARCHAR(255) NOT NULL,
    PRIMARY KEY (client_id)
);
```

Dans cet exemple, la colonne **`client_id`** s'incrémentera automatiquement chaque fois qu'un nouvel enregistrement sera ajouté dans la table **`Clients`**.

Lors de l'insertion de données, il est possible d'ignorer la colonne **`client_id`** :

```sql
INSERT INTO Clients (nom) VALUES ('Jean Dupont');
```

## 2. PostgreSQL - SERIAL

En PostgreSQL, l'incrémentation automatique est gérée par le type de données **`SERIAL`**.

### Exemple

```sql
CREATE TABLE Employes (
    employe_id SERIAL,
    nom VARCHAR(255) NOT NULL,
    PRIMARY KEY (employe_id)
);
```

Dans cet exemple, la colonne **`employe_id`** s'incrémentera automatiquement.

## 3. Oracle - SEQUENCE

Oracle n'a pas de type **`AUTO_INCREMENT`**, mais utilise les **`SEQUENCES`** pour générer des identifiants uniques.

### Exemple

1. Créez une séquence :

```sql
CREATE SEQUENCE emp_seq START WITH 1 INCREMENT BY 1;
```

2. Utilisez la séquence dans une insertion :

```sql
INSERT INTO Employes (employe_id, nom)
VALUES (emp_seq.NEXTVAL, 'Pierre Martin');
```

## 4. MS Access - AUTONUMBER

En MS Access, la colonne incrémentée est définie avec le type de données **`AUTONUMBER`**.

### Exemple

```sql
CREATE TABLE Clients (
    client_id AUTONUMBER,
    nom VARCHAR(255) NOT NULL,
    PRIMARY KEY (client_id)
);
```
