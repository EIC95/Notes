# Types de Données SQL Selon les Bases de Données

## 1. Types de Données Numériques

### MySQL
- **INT** : Entier, taille varie de TINYINT (1 octet) à BIGINT (8 octets).
- **FLOAT** : Nombre à virgule flottante.
- **DOUBLE** : Nombre à virgule flottante double précision.
- **DECIMAL** : Nombre décimal avec précision définie.

### SQL Server
- **INT** : Entier, tailles varient de TINYINT (1 octet) à BIGINT (8 octets).
- **FLOAT** : Nombre à virgule flottante (précision définie).
- **REAL** : Nombre à virgule flottante simple précision.
- **DECIMAL** : Nombre décimal avec précision définie (égal à NUMERIC).

### PostgreSQL
- **INTEGER** : Entier, tailles varient de SMALLINT (2 octets) à BIGINT (8 octets).
- **FLOAT4** : Nombre à virgule flottante simple précision.
- **FLOAT8** : Nombre à virgule flottante double précision.
- **NUMERIC** : Nombre décimal avec précision définie.

### Oracle
- **NUMBER** : Nombre décimal avec précision et échelle définies.
- **FLOAT** : Synonyme de NUMBER.
- **INTEGER** : Nombre entier, représenté par NUMBER.

## 2. Types de Données de Date et Heure

### MySQL
- **DATE** : Date au format AAAA-MM-JJ.
- **DATETIME** : Date et heure au format AAAA-MM-JJ HH:MI:SS.
- **TIMESTAMP** : Date et heure avec fuseau horaire.
- **YEAR** : Année au format AAAA ou AA.

### SQL Server
- **DATE** : Date au format AAAA-MM-JJ.
- **DATETIME** : Date et heure au format AAAA-MM-JJ HH:MI:SS.
- **SMALLDATETIME** : Date et heure au format AAAA-MM-JJ HH:MI:SS, avec une précision réduite.
- **DATETIME2** : Date et heure avec plus de précision que DATETIME.
- **TIMESTAMP** : Numéro unique (représente un point dans le temps, utilisé principalement pour les horodatages).

### PostgreSQL
- **DATE** : Date au format AAAA-MM-JJ.
- **TIMESTAMP** : Date et heure avec ou sans fuseau horaire.
- **TIMESTAMPTZ** : Date et heure avec fuseau horaire.
- **INTERVAL** : Intervalle de temps.

### Oracle
- **DATE** : Date et heure au format AAAA-MM-JJ HH:MI:SS.
- **TIMESTAMP** : Date et heure avec une précision supérieure à DATE.
- **TIMESTAMP WITH TIME ZONE** : Date et heure avec fuseau horaire.
- **INTERVAL** : Intervalle de temps.

## 3. Types de Données de Chaîne de Caractères

### MySQL
- **CHAR** : Chaîne de caractères fixe.
- **VARCHAR** : Chaîne de caractères variable.
- **TEXT** : Texte long (TINYTEXT, TEXT, MEDIUMTEXT, LONGTEXT).

### SQL Server
- **CHAR** : Chaîne de caractères fixe.
- **VARCHAR** : Chaîne de caractères variable.
- **TEXT** : Texte long (remplacé par VARCHAR(MAX) et NVARCHAR(MAX)).

### PostgreSQL
- **CHAR** : Chaîne de caractères fixe.
- **VARCHAR** : Chaîne de caractères variable.
- **TEXT** : Texte long.

### Oracle
- **CHAR** : Chaîne de caractères fixe.
- **VARCHAR2** : Chaîne de caractères variable.
- **CLOB** : Texte long (Character Large Object).

## 4. Types de Données Booléens

### MySQL
- **BOOLEAN** : Représente VRAI ou FAUX, stocké en tant que TINYINT(1).

### SQL Server
- **BIT** : Représente VRAI (1) ou FAUX (0).

### PostgreSQL
- **BOOLEAN** : Représente VRAI ou FAUX.

### Oracle
- **NUMBER(1)** : Représente un booléen, avec des valeurs généralement 0 et 1.

## 5. Types de Données Binaire

### MySQL
- **BINARY** : Données binaires fixes.
- **VARBINARY** : Données binaires variables.
- **BLOB** : Binary Large Object (TINYBLOB, BLOB, MEDIUMBLOB, LONGBLOB).

### SQL Server
- **BINARY** : Données binaires fixes.
- **VARBINARY** : Données binaires variables.
- **IMAGE** : BLOB (remplacé par VARBINARY(MAX)).

### PostgreSQL
- **BYTEA** : Données binaires.

### Oracle
- **RAW** : Données binaires fixes.
- **BLOB** : Binary Large Object.
