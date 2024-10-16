# Expression CASE et Vérification des Valeurs NULL en SQL

## Expression CASE

L'expression `CASE` en SQL est utilisée pour exécuter des tests conditionnels et renvoyer des valeurs en fonction des résultats. Elle fonctionne de manière similaire à une structure `if-then-else` dans les langages de programmation. Une fois qu'une condition est remplie, l'expression `CASE` renvoie la valeur associée et cesse de vérifier les conditions restantes. Si aucune des conditions n'est vraie et qu'une clause `ELSE` est fournie, elle renvoie la valeur spécifiée dans `ELSE`. Si aucune condition n'est vraie et qu'il n'y a pas de clause `ELSE`, l'expression `CASE` renvoie `NULL`.

### Syntaxe de l'Expression CASE

#### Syntaxe Simple

```sql
CASE
    WHEN condition1 THEN valeur1
    WHEN condition2 THEN valeur2
    ...
    ELSE valeur_defaut
END
```

#### Exemple

```sql
SELECT nom,
       CASE
           WHEN age < 18 THEN 'Mineur'
           WHEN age BETWEEN 18 AND 64 THEN 'Adulte'
           ELSE 'Senior'
       END AS categorie
FROM personnes;
```

Dans cet exemple :

- La colonne `categorie` renvoie "Mineur" si `age` est inférieur à 18.
- Elle renvoie "Adulte" si `age` est compris entre 18 et 64.
- Elle renvoie "Senior" si `age` est 65 ou plus.

## Vérification des Valeurs NULL

Différentes bases de données utilisent des fonctions spécifiques pour vérifier si une expression est nulle. Voici un aperçu des fonctions disponibles :

- **MySQL** : `IFNULL(expression, valeur_de_remplacement)` ou `COALESCE(expression, valeur_de_remplacement)`
- **SQL Server** : `ISNULL(expression, valeur_de_remplacement)` ou `COALESCE(expression, valeur_de_remplacement)`
- **MS Access** : `IsNull(expression)`
- **Oracle** : `NVL(expression, valeur_de_remplacement)` ou `COALESCE(expression, valeur_de_remplacement)`

### Exemples

#### MySQL

```sql
SELECT nom, IFNULL(email, 'Email non fourni') AS email_contact
FROM clients;
```

#### SQL Server

```sql
SELECT nom, ISNULL(email, 'Email non fourni') AS email_contact
FROM clients;
```

#### MS Access

```sql
SELECT nom, IIf(IsNull(email), 'Email non fourni', email) AS email_contact
FROM clients;
```

#### Oracle

```sql
SELECT nom, NVL(email, 'Email non fourni') AS email_contact
FROM clients;
```
