# Procédures Stockées en SQL

## Qu'est-ce qu'une Procédure Stockée ?

Une procédure stockée est un ensemble de commandes SQL précompilées qui sont stockées dans une base de données. Elle est conçue pour être réutilisée plusieurs fois sans avoir besoin de réécrire le code à chaque utilisation. Les procédures stockées permettent d'encapsuler des logiques de traitement complexes et de simplifier la gestion des requêtes SQL répétitives.

## Avantages des Procédures Stockées

- **Réutilisabilité** : Une fois créée, une procédure stockée peut être appelée plusieurs fois sans répéter le code.
- **Centralisation de la Logique** : Permet de centraliser la logique de traitement dans la base de données, ce qui facilite la gestion et les modifications.
- **Sécurité** : Permet de restreindre l'accès direct aux tables et d'exécuter des requêtes de manière contrôlée.
- **Performance** : Les procédures stockées sont précompilées, ce qui peut améliorer les performances d'exécution.

## Création d'une Procédure Stockée

Voici la syntaxe générale pour créer une procédure stockée dans différentes bases de données SQL :

### MySQL

```sql
DELIMITER //
CREATE PROCEDURE nom_procedure (param1 TYPE, param2 TYPE)
BEGIN
    -- Code SQL à exécuter
END //
DELIMITER ;
```

### SQL Server

```sql
CREATE PROCEDURE nom_procedure
    @param1 TYPE,
    @param2 TYPE
AS
BEGIN
    -- Code SQL à exécuter
END;
```

### Oracle

```sql
CREATE OR REPLACE PROCEDURE nom_procedure (param1 IN TYPE, param2 IN TYPE) 
IS
BEGIN
    -- Code SQL à exécuter
END;
```

## Appel d'une Procédure Stockée

Après avoir créé une procédure stockée, vous pouvez l'appeler en utilisant le nom de la procédure et en passant les paramètres nécessaires.

### MySQL

```sql
CALL nom_procedure(valeur1, valeur2);
```

### SQL Server

```sql
EXEC nom_procedure @param1 = valeur1, @param2 = valeur2;
```

### Oracle

```sql
BEGIN
    nom_procedure(valeur1, valeur2);
END;
```

## Exemples de Procédures Stockées

### Exemple en MySQL

Créer une procédure pour ajouter un nouvel employé :

```sql
DELIMITER //
CREATE PROCEDURE AjouterEmploye (IN nom VARCHAR(50), IN salaire DECIMAL(10, 2))
BEGIN
    INSERT INTO Employes (Nom, Salaire) VALUES (nom, salaire);
END //
DELIMITER ;
```

Appeler la procédure pour ajouter un employé :

```sql
CALL AjouterEmploye('Jean Dupont', 3000.00);
```

### Exemple en SQL Server

Créer une procédure pour obtenir les détails d'un employé :

```sql
CREATE PROCEDURE ObtenirDetailsEmploye
    @emp_id INT
AS
BEGIN
    SELECT * FROM Employes WHERE EmployeID = @emp_id;
END;
```

Appeler la procédure pour obtenir les détails de l'employé avec ID 1 :

```sql
EXEC ObtenirDetailsEmploye @emp_id = 1;
```

### Exemple en Oracle

Créer une procédure pour mettre à jour le salaire d'un employé :

```sql
CREATE OR REPLACE PROCEDURE MettreAJourSalaire (
    emp_id IN NUMBER,
    nouveau_salaire IN NUMBER
) 
IS
BEGIN
    UPDATE Employes SET Salaire = nouveau_salaire WHERE EmployeID = emp_id;
END;
```

Appeler la procédure pour mettre à jour le salaire de l'employé avec ID 2 :

```sql
BEGIN
    MettreAJourSalaire(2, 3500.00);
END;
```